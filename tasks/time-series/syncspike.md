# Synchronous Spikes

Two noisy channels of equal length are generated. Both start with independent Gaussian noise $\varepsilon^{(a)}_{i},\;\varepsilon^{(b)}_{i} \stackrel{\text{iid}}{\sim} \mathcal{N}(0, \sigma^2$, with $\sigma = 0.4$, and an independent DC offset $\delta_a, \delta_b \sim \mathcal{U}(-5, 5)$ that erases any mean-based cue:

```math
A_i = \varepsilon^{(a)}_{i} + \delta_{a},\qquad
B_i = \varepsilon^{(b)}_{i} + \delta_{b}.
```

## Spikes

Exactly $n_{\text{spk}} = 3$ spike centres $t_k \sim \mathcal{U}\{20, \dotsc, N - 21\}$ are drawn without replacement. Each spike adds a Gaussian pulse of random amplitude $A_k \sim \mathcal{U}(8, 12)$ at (or near) its centre.

## Class 0 (Synchronous)

Channel B receives (approximately) the *same* spike indices as channel A, i.e.

```math
B_{t_{k}} \; \leftarrow \; B_{t_{k}} + A_k + \eta_k,
\quad
\eta_k\sim\mathcal N(0,0.3^{2}),
```

so at least one spike is coincident in the two channels (within $\pm2$ samples).

## Class 1 (Independent)

Channel B’s spikes are relocated by a random offset $\Delta_k \sim \{5, \dotsc, 29\}$:

```math
B_{(t_k + \Delta_k) \bmod N} \leftarrow
B_{(t_k + \Delta_k) \bmod N} + A_k
```

ensuring no pair of spikes is closer than two samples.

## Visual Example

![Synchronous Spikes](/tasks/time-series/plots/syncspike_dataset_example.png)