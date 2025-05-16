---
id: gae0xo7vv1ohog3hm1camut
title: Branch Lengths
desc: ''
updated: 1747382279864
created: 1747316579771
---

## Changes in the branch lengths binning
Previously we had that the total sum of the branch length was equal to 1. Now we have changed the binning so that the average branch length is equal to 1.

We define $m$ as the middle point of each bin so that we have $m_0$ the middle point of bin $0$. Now, the branch length of one has to be a middle point of the bins. We have as lower bound 0, and we want as many bins on the right side as on the left side of $1$.


For example, if we have 7 bins, we want to have 3.5 bins on the right side of 1 and 3.5 on the left side. We define $K$ as the number of bins on one side of 1 *i.e.* 3.5. $\delta$ which is the interval of each bin is thus equal to 

$$
\delta = \frac{1}{K+\frac{1}{2}} = \frac{2}{2K+1}
$$

if $K=\frac{N}{2}$ and $N$ is the total number of bins we can simplify to 

$$
\delta = \frac{2}{N+1}
$$

For each bin $i$ where $i = (0, ..., N-1)$ the middle point $m_i$, the lower bound $l_i$ and the upper bound $u_i$ are equal to 

$$
\begin{align}
m_i &= \delta (i + \frac{1}{2}) \\
l_i &= \delta i \\
u_i &= \delta (i+1)\\
\end{align}
$$

## Formulation
As previously, let us define $N$ the total number of bins and $B$ the total number of branch length in the tree. We want to constrain the tree in order to have an average branch length in the tree of 1.

We thus have 

$$
\frac{1}{B} \sum_{b=0}^{B-1}{m_{i_{(b)}}} = 1
$$
As defined before, $m_i = \delta (i + \frac{1}{2})$ and $\delta = \frac{2}{N+1}$ so we have 

$$
\begin{align}
    1 &= \frac{1}{B}\sum_b \delta(i_{b} + \frac{1}{2}) \\
    B &= \sum_b \delta (i_b + \frac{1}{2}) \\
    B &= \frac{2}{N+1} \sum_b (i_b+\frac{1}{2}) \\
    B \frac{N+1}{2} &= \sum_b i_b + \frac{B}{2} \\
    B (\frac{N+1}{2} - \frac{1}{2}) &= \sum_b i_b \\
    \frac{BN}{2} &= \sum_b i_b
\end{align}
$$

### Example
If we have $N=100$ and $B=50$, and let us set all branches to a length of 1 (in order to have an average of 1). Then the index of the bin where the branch length is one, is at 50. We thus have $\frac{50 \cdot 100}{2} = 2500$ and we have $50$ branches with a bin index of $50$ which is also equal to $2500$.