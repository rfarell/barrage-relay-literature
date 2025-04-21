# Controlled Barrage Regions: Stochastic Modeling, Analysis, and Optimization

## Summary

This paper formulates unicast delivery inside Barrage Relay Networks (BRNs) as a Markov-driven stochastic process over "controlled barrage regions" (CBRs), derives a closed-form Rayleigh-fading outage expression, couples it with a Viterbi-like iterative update to capture intra-CBR interference, and uses the resulting analysis to jointly optimize code-rate $R$, relay count $N$, and frame length $F$ for maximum transport-capacity.

## Key Contributions

- Provides an exact yet tractable performance model for a unicast CBR including fading, path-loss and co-channel interference
- Develops closed-form analytics that remove the Monte-Carlo over fading, cutting complexity orders-of-magnitude
- Demonstrates that accurate interference accounting allows aggressive spatial reuse (smaller $F$) without sacrificing reliability
- Shows transport-capacity-optimal design balances relay density (diversity) against interference (pipelining) and code-rate

## Mathematics

Key equations from the paper:

$$P(x) = \lambda e^{-\lambda x} \mathbf{1}_{x \geq 0}$$

Where $\lambda$ is the density parameter of the PPP (Poisson Point Process).

The transport capacity metric is defined as:

$$A = d_{\mathrm{CBR}}\,(1-\varepsilon_{\mathrm{CBR}})\,R/F$$

Where $d_{\mathrm{CBR}}$ is the CBR distance, $\varepsilon_{\mathrm{CBR}}$ is the Markov-derived outage probability, $R$ is the code rate, and $F$ is the frame length.

The SINR expression includes fully-correlated interference:

$$\gamma^{(t)}_{j,n} = \frac{\sum_{i \in \mathcal{G}_{j,n}^{(t)}} \alpha_{i,j}^2 \Omega_{i,j}}{\sigma^2 + \sum_{i \in \mathcal{I}_{j,n}^{(t)}} \alpha_{i,j}^2 \Omega_{i,j}}$$

Where $\mathcal{G}_{j,n}^{(t)}$ is the cooperative transmit set and $\mathcal{I}_{j,n}^{(t)}$ is the interference set.