**Barrage Relay Network (BRN) routing remains reliable only under ideal graph‑level models; once realistic fading and dense‑node effects are added, hop‑count geometry breaks down and node utilization explodes.**

---

### Problem  
- Ultra‑dense, infrastructure‑free wireless deployments (e.g., disaster relief, IoBT) need **lightweight, decentralized unicast routing**.  
- The BRN protocol forms a *controlled barrage region* (CBR) via hop‑count logic  
  $$h_{\text{RTS}}+h_{\text{CTS}}\le h_{SD}+w$$
  but prior work assumed a *connected‑graph model (CGM)* that ignores fading and cooperative broadcast effects.  
- **Goal:** Quantify how *channel physics* (fading, path‑loss, constructive interference) and *node density* beyond the connectivity threshold affect (i) CBR formation probability ("reliability") and (ii) total relay + buffer nodes used ("utilization"). citeturn0file0  

### Methods  
| Aspect | Choice | Rationale |  
|---|---|---|  
| **Topology** | Square of side $L=30d_0$; 4000 geometric‑random networks per setting | Ensemble stats for variability |  
| **Node density** | $\rho\in\{1,2,3,4,6,8,10\}$ nodes / $d_0^2$ | Push well beyond connectivity threshold |  
| **Channel models** | CGM (ideal), DCM (deterministic path‑loss, cooperative sum), RCM (Rayleigh fading + cooper. sum) | Isolate impact of fading vs. mere power aggregation |  
| **Distances** | Source–dest separations $D\in\{3d_0,10d_0\}$ | Short vs. long routes |  
| **Protocol params** | Excess width $w\in\{0,\dots,4\}$ | Controls CBR breadth |  
| **Metrics** | Reliability $P_{\text{CBR}}$; Utilization $U$ | Service quality vs. resource cost |  

Simulation is a discrete‑event BRN implementation with TDMA; $d_0$ chosen so a single‑node link meets SNR $\beta$. citeturn0file0  

### Key Findings  
- **Reliability:**  
  * CGM appears near‑perfect once $\rho\ge 2$.  
  * RCM/DCM need **larger $w$** to maintain reliability; for dense networks cooperative broadcasts "overshoot," mis‑registering hop counts and stalling CTS propagation (Fig. 2, p. 4).  
- **Utilization:**  
  * CGM shows mild super‑linear $U\propto\rho^{1+}$.  
  * RCM/DCM escalate **super‑linearly**; at $\rho=10$ and $w=3$ median $U/\rho$ is $>\!150\%$ of CGM (Figs. 4–5).  
  * Variance is highest under fading (RCM), demanding worst‑case provisioning.  
- **Trade‑off:** Raising $w$ rescues reliability but further inflates $U$; thus BRN faces a **reliability–throughput tension** in dense settings.  
citeturn0file0  

### Implications & Recommendations  
1. **Graph‑only analysis is optimistic**; channel‑aware models are mandatory when extrapolating BRN to IoBT‑scale densities.  
2. Introduce *position or range awareness* so off‑path nodes self‑suppress, trimming CBR width.  
3. Adapt **transmit power (hence effective $d_0$)** to bound cooperative‑broadcast radius, keeping $U$ sub‑linear.  
4. Explore dynamic $w$ or hop‑distance metrics that account for aggregate‑SNR growth.  
5. Future work: analytic geometry of hop‑count distortion; power‑aware BRN variants with localization cues. citeturn0file0