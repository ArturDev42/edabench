# Row Max Abs

Each row is a 12-dimensional feature vector: (`feat_1`, `feat_2`, ..., `feat_12`). The binary label is determined solely by the *row-wise* maximum absolute feature value: $m(x) = \max_{i = 1, \dots, 12} \bigl| \texttt{feat}_i \bigr|$

A row is assigned to class 1 **iff** $m(x) > \tau$, with the decision threshold fixed at $\tau = 4$; otherwise it is labelled as class 0.

## Class 0

All features are sampled independently from the standard normal distribution, and the sample is rejected until no entry crosses $\tau$: $\texttt{feat}_i \sim \mathcal{N}(0, 1) \quad (i = 1, \dots, 12)$


## Class 1

Starting from the same base distribution, we choose one feature at random and inject a large spike so that the threshold is exceeded: $\texttt{feat}_j \leftarrow \texttt{feat}_j + \delta,\qquad \delta \sim \mathcal{U}(5, 8)\,s,\; s \in \{-1, 1\}$. All remaining features stay pure noise, ensuring $m(x) > \tau$ for every class-1 row.

## Visual Example

![Channel correlation (easy)](/tasks/tabular/plots/maxabs_combined.png)


