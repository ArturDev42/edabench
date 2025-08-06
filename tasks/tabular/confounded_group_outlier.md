# Confounded‐group Outlier

Each row has the form `(group_id, signal, noise_1, noise_2)`.

All rows that share the same `group_id` belong to one group and therefore receive the same label. Groups contain a fixed number of rows ($R = 50$).

The label depends solely on the *within-group* proportion of extreme values in the `signal` column: a group is labelled as class 1 **iff** at least $\rho^\star = 8\%$ of its rows satisfy $|\texttt{signal}| > 3$; otherwise it is labelled as class 0.

## Class 0

Every row is sampled from pure noise, so the probability of an extreme value is governed only by the tails of the normal distribution: $\texttt{signal} \sim \mathcal{N}(0, 1), \qquad \texttt{noise}_j \sim \mathcal{N}(0, 1) \;\; (j = 1, 2)$.
Consequently, the empirical outlier ratio of a class-0 group rarely exceeds $\rho^\star$.

## Class 1

Starting from the same base distribution as class 0, we randomly select between $10\%$ and $15\%$ of the rows in the group and corrupt their `signal` values with a large additive shift of either $-6$ or $+6$: $\texttt{signal} \sim \mathcal{N}(0,1) + \delta,\qquad \delta \in \{-6, 6\}$. The remaining rows — and all distractor columns `noise_j` — are generated exactly as in class 0.

Note that the task is complicated by the *color* column, which is strongly correlated with the label in the training set but not in the test set.

## Visual Example

![Channel correlation (easy)](/tasks/tabular/plots/ratio_distribution.png)