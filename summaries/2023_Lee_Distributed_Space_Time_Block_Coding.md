**TL;DR** Lee *et al.* replace phase‑rotation cooperation in barrage‑relay networks with a **fully‑distributed space‑time block code (FD‑STBC)**, derive a closed‑form upper‑bound on end‑to‑end outage, and show ≳10 dB reliability gains at $10^{-3}$ outage without any inter‑node coordination. citeturn0file0  

---

### Problem being solved  
- **Barrage Relay Networks (BRNs)**—TDMA‑based flooding MANETs for tactical use—currently exploit **random phase rotations (PR)** when multiple relays rebroadcast a packet, but PR offers no spatial‑diversity gain.  
- Applying classical distributed STC is considered infeasible because it needs centralized coordination and CSI exchange, violating BRN design goals. citeturn0file0  

### Proposed method  
1. **Fully‑Distributed STBC (FD‑STBC)**  
   - Each relay that correctly decodes in slot $t-1$ transmits in slot $t$ the **Alamouti block**  
     $$\mathbf B(\mathbf x)=\begin{bmatrix}x_1 & x_2\\ -x_2^{\!*} & x_1^{\!*}\end{bmatrix},
     $$  
     right‑multiplied by its own **randomization vector** $\mathbf r_i=\bigl[r_{i,1},\,r_{i,2}\bigr]^{\!\top}$ drawn uniformly from the surface of a complex unit hypersphere, i.e.  
     $\mathbf r_i=\frac{\tilde{\mathbf r}_i}{\|\tilde{\mathbf r}_i\|_2},\;\tilde{\mathbf r}_i\sim\mathcal N_{\mathbb C}(\mathbf 0,\mathbf I)$.  
   - No pilot exchange of $\mathbf r_i$ or relay count is required; the destination estimates only the **equivalent channel** $\mathbf h^{\text{eff}}_j=\mathbf R^{(t)}\mathbf h^{(t)}_j$. citeturn0file0  

2. **Network model**  
   - Four‑node *controlled barrage region* (CBR): source S, two relays $R_1,R_2$, destination D (see Fig. 1, p. 2). Time‑slot limit = 3. Decode‑and‑forward protocol, block‑Rayleigh fading, path‑loss exponent $\alpha$. citeturn0file0  

### Analytical contributions  
- Derived **instantaneous SNRs**  
  $$\rho^{(2)}_D=\rho_0\lVert\mathbf R^{(2)}\mathbf h^{(2)}_D\rVert_2^{2},
  $$  
  and showed they stochastically dominate PR when both relays are active.  
- Obtained **closed‑form outage probability** for each slot; for the two‑relay slot they upper‑bound  
  $$\Pr\!\Bigl[\!\sum_{k=1}^{2}\!\lambda_k^{2}|\hat h_k|^{2}\!<\!\tfrac{\rho_{\text{th}}}{\rho_0}\Bigr],
  $$  
  where $\lambda_k^2$ are eigenvalues of $\Sigma^{1/2}\mathbf R^{\rm H}\mathbf R\Sigma^{1/2}$.  
- Combined via total‑probability theorem to yield an **end‑to‑end outage upper bound** (eq. 17). citeturn0file0  

### Key results (Fig. 2–3)  
| Scenario | Target $P_\text{out}$ | Gain over PR | Notes |
|----------|-----------------------|--------------|-------|
| Line CBR | $10^{-3}$ | ~10 dB SNR | FD‑STBC ≈ centralized STC |
| Diamond CBR | $10^{-4}$ | 8–9 dB | Robust across topology | citeturn0file0  

### Significance  
- **Practicality:** retains BRN's "no‑coordination" ethos; each relay acts independently.  
- **Efficiency:** meets the same reliability with far lower transmit power or fewer relays.  
- **Scalability:** framework extendable to $N$-relay BRNs; authors plan to generalize. citeturn0file0  

### Limitations / future work  
- Current analysis limited to 2‑relay CBR; diversity order capped at 2.  
- Assumes perfect slot‑level sync and ideal channel estimation of $\mathbf h^{\text{eff}}$.  
- Extending to arbitrary topologies and mobility, and integrating with power control, left open. citeturn0file0