# This is Marco's daily open-notebook.

Today is 2024.10.14

## Meeting with Madleina
- [ ] start by creatin a script that is able to fetch phylogeny from lotus and molecules
- [ ] use Cache
- [ ] for species, get full wikidata taxo, then remove all species with their parent that are not in lotus.
- [ ] input should be a node and then it will get all the children of that node : Plantae --> all the children of plantae
- [ ] use that to subset lotus

## Notes
This is the qlever sparql query to get all the mammals and their parent taxa.

```sparql
PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX wd: <http://www.wikidata.org/entity/>

SELECT ?taxon ?taxon_name ?taxon_rank ?taxon_rank_label ?taxon_parent ?parent_name WHERE {
  ?taxon wdt:P225 ?taxon_name;
         wdt:P105 ?taxon_rank;
         wdt:P171* wd:Q7377;      # Recursively fetches all taxa with Mammal as an ancestor
         wdt:P171 ?taxon_parent.

  ?taxon_rank rdfs:label ?taxon_rank_label.
  FILTER (lang(?taxon_rank_label) = "en")
  FILTER (?taxon_rank != wd:Q68947)  # Exclude taxa with rank "subspecies"

  ?taxon_parent wdt:P225 ?parent_name.
}
```

This is a nice query because we can then create a function that will fetch all the children of a node. We will use the Mammal for testing our model as they are not too many. 

What I need to do then is to create a function that given a root node, will return all the children (with the option of filtering the sub-species). It should also be able to not rerun the full function if the query and the output of that query is already in the cache.

This query : 
```sparql
PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX p: <http://www.wikidata.org/prop/>
PREFIX ps: <http://www.wikidata.org/prop/statement/>
PREFIX pr: <http://www.wikidata.org/prop/reference/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX wd: <http://www.wikidata.org/entity/>

PREFIX prov: <http://www.w3.org/ns/prov#>
SELECT DISTINCT ?structure ?structure_inchikey ?taxon ?taxon_name ?reference ?reference_doi ?taxon_rank ?taxon_rank_label ?taxon_parent ?parent_name WHERE {
  ?structure wdt:P235 ?structure_inchikey;  # get the inchikey
    p:P703 ?taxon_statement.                # find the statement node
  
  ?taxon_statement ps:P703 ?taxon.          # get the taxon from the statement node
  ?taxon_statement prov:wasDerivedFrom ?ref_node. # get the reference node from the statement node
  ?ref_node pr:P248 ?reference.             # get the reference item

  ?taxon wdt:P225 ?taxon_name;              # get the taxon scientific name
         wdt:P105 ?taxon_rank;              # get the taxon rank
         wdt:P171* wd:Q21730;                # recursively fetch all taxa with Asterales as an ancestor
         wdt:P171 ?taxon_parent.            # get the taxon's immediate parent

  ?taxon_rank rdfs:label ?taxon_rank_label.
  FILTER (lang(?taxon_rank_label) = "en")
  FILTER (?taxon_rank != wd:Q68947)         # exclude taxa with rank "subspecies"

  ?taxon_parent wdt:P225 ?parent_name.      # get the parent taxon's scientific name
  ?reference wdt:P356 ?reference_doi.       # get the reference DOI
}
```
Will get all the molecules that are associated with any taxon that is a child of Asterales. This is also very useful to quickly get all the molecules associated with a taxon.


## Todo today
- [ ] 

## Doing


## Done
*  


## Todo tomorrow
- [ ]