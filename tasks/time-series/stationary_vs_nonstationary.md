# Predict TS Stationarity

A time series is an autoregressive (AR) process given by $x_t = \sum_{i=1}^{p} \phi_i x_{t-i} + \varepsilon_t$, where $\varepsilon_t \sim \mathcal{N}(0, \sigma^2)$ is white noise and $\phi_1, \dots, \phi_p$ are autoregressive parameters.


## Class 0 (Stationary)

The time series is *stationary*, which means it has constant mean and variance over time, given by the condition that all roots of $1 - \sum_{i=1}^{p} \phi_i z^i = 0$ satisfy $|z| > 1$.


## Class 1 (Non-stationary)

The time series is *non-stationary* and represents a random walk, given by $x_t = x_{t-1} + \varepsilon_t$, which corresponds to an AR($p = 1$) process with $\phi_1 = 1$, where the characteristic root lies on the unit circle. As a result, the process has no constant mean or variance and is said to have a *unit root*.

All time series are scaled to unit variance, i.e., standardized such that mean is $0$ and variance is $1$. This ensures that no simple magnitude-based feature (such as mean or variance) can be used to infer the class label. Any discriminative information must come from temporal structure or autocorrelation.

## Visual Example

![Channel correlation (easy)](/tasks/time-series/plots/stationary_vs_nonstationary_train.png)