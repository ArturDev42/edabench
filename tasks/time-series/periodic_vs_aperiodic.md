# Periodic Presence

## Class 0 (Periodic)

A single sine component with random frequency $f \in \{0.05,\,0.08,\,0.12\}\,\text{Hz}$ and random amplitude $A \sim \mathcal{U}(0.8, 1.5)$ is embedded in white noise:

```math
X_i = A\,\sin\bigl(2\pi f t_i + \phi\bigr) + \varepsilon_i,
\qquad
\varepsilon_i \sim \mathcal{N}\!\left(0, \sigma^2\right)
```

followed by a rescaling to *unit variance*:  $X_i \leftarrow X_i / \hat{\sigma}_X$.

## Class 1 (Aperiodic)

Coloured noise is produced by low-pass filtering white noise via a cumulative sum (pink–like spectrum):

```math
Y_i = \frac{1}{\sqrt{N}} \sum_{k=1}^{i} \eta_k,
\qquad
\eta_k \sim \mathcal{N}\!\left(0, \sigma^2\right)
```

and likewise normalised to *unit variance*:  $Y_i \leftarrow Y_i / \hat{\sigma}_Y$.

## Visual Example

![Channel correlation (easy)](/tasks/time-series/plots/periodic_vs_aperiodic_train.png)


