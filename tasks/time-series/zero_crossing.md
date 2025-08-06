# Zero-crossing Count

A single-channel signal of fixed length $N = 1000$ samples is simulated at a sampling frequency $f_{\mathrm{s}} = 100\,\text{Hz}$, with the goal of distinguishing signals based on their zero-crossing rate (ZCR) — the frequency at which the signal changes sign.

Each trace is a noisy sinusoid

```math
  x_i \;=\; \sin\!\bigl(2\pi f\,t_i + \phi\bigr) \;+\; n_i,
  \qquad
  t_i \;=\; \frac{i}{f_{\mathrm{s}}},\; i = 0,\dots,N-1,
```

where the carrier frequency \(f\) and the additive noise \(n_i\) are
drawn as follows:

- A random phase $\phi \sim \mathcal{U}(0, 2\pi)$ is chosen once per signal.

- The frequency $f$ is sampled *uniformly* from a low- or high-frequency band, depending on the class.

- Independent Gaussian noise $n_i^{\ast} \sim \mathcal{N}(0, \sigma^2)$ with $\sigma = 0.5$ is generated and then **clipped** so that it can never reverse the sign of the clean sinusoid:
```math
n_i =
\mathrm{clip}\!\Bigl(
    n_i^{\ast},
    -0.99\,\bigl|\sin(2\pi f t_i+\phi)\bigr|,
    +0.99\,\bigl|\sin(2\pi f t_i+\phi)\bigr|
\Bigr)
```
Consequently every perturbed sample retains the original sign, ensuring that no spurious zero-crossings are introduced.

## Class 0 (High ZCR)

The carrier lies in the *high* band $f \in [10,\,20]\,\text{Hz}$, producing roughly $2fT \approx 200\!-\!400$ sign changes over the interval ($T = N / f_{\mathrm{s}} = 10\,\text{s}$).

## Class 1 (Low ZCR)
The carrier lies in the *low* band $f \in [3,\,8]\,\text{Hz}$, yielding only $2fT \approx 60\!-\!160$ zero-crossings for the same $T$.

## Visual Example

![Synchronous Spikes](/tasks/time-series/plots/zero_crossing.png)