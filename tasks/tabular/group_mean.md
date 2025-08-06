# Group‐mean Threshold

Each row has the form  (`group_id`, `value_0`, `value_1`, `value_2`, `value_3`). All rows sharing the same `group_id` have the same label, which depends only on the within-group mean of the first feature (`value_0`). Groups contain a fixed number of rows ($R = 20$); half of the groups are sampled as class 0 and the other half as class 1.

## Class 0

Every row is sampled from pure noise: $\texttt{value\_0} \sim \mathcal{N}(0, 1), \qquad \texttt{value\_i} \sim \mathcal{N}(0, 1) \;\; (i = 1, 2, 3)$.

## Class 1

60% of `value_0` is sampled as $\texttt{value\_0} \sim \mathcal{N}(6, 1)$, while the remaining 40% are sampled as in class 0: $\texttt{value\_0} \sim \mathcal{N}(0, 1)$. All distractor columns remain pure noise: $\texttt{value\_i} \sim \mathcal{N}(0, 1) \;\; (i = 1, 2, 3)$. The mixture keeps the *group-mean* of `value_0` above the decision threshold $\tau = 3$, yet removes any row-wise shortcut.

## Visual Example

![Channel correlation (easy)](/tasks/tabular/plots/group_mean_example.png)