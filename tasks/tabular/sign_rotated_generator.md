# Sign‐rotated Generator

Each row is a 7-dimensional feature vector: (`feat_1`, `feat_2`, ..., `feat_7`). `feat_1` and `feat_2` are sampled i.i.d. from the standard normal: $(\texttt{feat}_1, \texttt{feat}_2) \sim \mathcal{N}(0, 1)$

With a fixed rotation angle $\theta = 30^\circ$, we define the rotated coordinates:

```math
u = \cos\theta \cdot \texttt{feat}_1 + \sin\theta \cdot \texttt{feat}_2
\qquad
v = -\sin\theta\,\texttt{feat}\_1 + \cos\theta\,\texttt{feat}\_2,
\qquad
p = u\,v.
```

## Class 0

Samples where $u \cdot v < -0.10$

## Class 1

Samples where $u \cdot v > 0.10$

We reject sample any sample between $0.10 > u*v > -0.10$

## Visual Example

![Channel correlation (easy)](/tasks/tabular/plots/uv_product_histogram.png)