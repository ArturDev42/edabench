# Dominant Feature

Each row is a vector $(\texttt{feat}_1,\, \texttt{feat}_2,\, \texttt{feat}_3,\, \texttt{feat}_4,\, \texttt{feat}_5,\, \texttt{feat}_6)$.


## Class 0

Each feature is sampled independently from a normal distribution, e.g., $\mathrm{feat}_i \sim \mathcal{N}(0, 1)$ for $i = 1, \dots, 6$.


## Class 1

$\mathrm{feat}_3$ is sampled as $\max\{\mathrm{feat}_1, \mathrm{feat}_2\} + \mathrm{gap}$, where $\mathrm{gap} \sim \mathcal{N}(0.5, 1.5)$. All other features are sampled as in class 0:  $\mathrm{feat}_i \sim \mathcal{N}(0, 1)$ for $i \in \{1, 2, 4, 5, 6\}$.

## Visual Example

![Channel correlation (easy)](/tasks/tabular/plots/dominant_feature.png)