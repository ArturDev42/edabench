# Channels Correlation (Hard)

## Class 0

Both channels start as independent white-noise walks $\tilde{A}_i,\;\tilde{B}_i \stackrel{\text{iid}}{\sim} \mathcal{N}(0,1)$. Each channel is then transformed by an independent random scale  $s_A, s_B \sim \mathcal{N}(0, 1.5)$ (allowing sign flips), and an independent DC offset $\delta_A, \delta_B \sim \mathcal{N}(0, 3)$:

```math
A_i = s_A\,\tilde{A}_i + \delta_A,\qquad
B_i = s_B\,\tilde{B}_i + \delta_B
```

## Class 1

A smooth random walk $W_i = \sum_{k=1}^{i} \varepsilon_k$, where $\varepsilon_k \sim \mathcal{N}(0, 0.2)$, is shared between the channels. Independent noise $\eta_{A,i}, \eta_{B,i} \sim \mathcal{N}(0, \sigma^2)$ is added, followed by the same scale-plus-offset transformation:

```math
\tilde{A}_i = W_i + \eta_{A,i},\qquad
\tilde{B}_i = W_i + \eta_{B,i},
```
```math
A_i = s_A\,\tilde{A}_i + \delta_A,\qquad
B_i = s_B\,\tilde{B}_i + \delta_B.
```


## Visual Example

![Channel correlation (hard)](/tasks/time-series/plots/channel_corr_hard.png)
