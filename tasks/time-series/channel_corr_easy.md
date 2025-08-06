# Channels Correlation Easy

## Class 0:

Both channels are independent white-noise walks:  $A_i,\;B_i \stackrel{\text{iid}}{\sim} \mathcal{N}(0,1)$, followed by independent Direct Current offsets $\delta_A,\delta_B\sim\mathcal{N}(0,3)$:

```math
A_i = \tilde{A}_i + \delta_A,\qquad
B_i = \tilde{B}_i + \delta_B.
```

## Class 1

A smooth random walk $W_i = \sum_{k=1}^{i}\varepsilon_k,\;\varepsilon_k\sim\mathcal{N}(0,0.2)$ is shared between the channels; independent noise and the same offset mechanism are then applied:

```math
A_i = W_i + \eta_{A,i} + \delta_A,\qquad
B_i = W_i + \eta_{B,i} + \delta_B,\quad
\eta_{A,i},\eta_{B,i}\sim\mathcal{N}(0,\sigma^2)
```

## Visual Example

![Channel correlation (easy)](/tasks/time-series/plots/channel_corr_easy.png)

