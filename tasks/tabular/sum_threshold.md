# Sum Threshold

Each row is a 6-dimensional feature vector: (`feat_1`, `feat_2`, ..., `feat_6`). All six features are sampled i.i.d. from a low-variance Gaussian: $\texttt{feat}_i \sim \mathcal{N}\!\bigl(0,\, 0.3^2\bigr), \qquad i = 1, \dots, 6$. Let $s(x) = \texttt{feat}_1 + \texttt{feat}_2 + \texttt{feat}_3$

## Class 0

$s(x)$ is for all labels lower than 0. We achieve that by subtracting an independent offset $\delta_j \sim \mathcal{U}(0.3, 0.6)$ from each of the first three features,

```math
\texttt{feat}_j = \texttt{feat}_j - \delta_j, \quad j = 1, 2, 3
```
which deterministically keeps the sum below the threshold.

## Class 1

$s(x)$ is for all labels above 0. We achieve that by

```math
\texttt{feat}_j = \texttt{feat}_j + \delta_j, \quad j = 1,2,3.
```
The distractor features $(j = 4,5,6)$ remain unchanged Gaussian noise.

## Visual Example

![Channel correlation (easy)](/tasks/tabular/plots/sum_combined.png)