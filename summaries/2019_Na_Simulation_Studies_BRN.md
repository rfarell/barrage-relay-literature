**Precise takeaway → The paper develops and validates detailed OPNET models—network, node, and finite‑state‑process—to simulate Barrage Relay Networks (BRN) and their Controlled Barrage Region (CBR) application, filling the gap between prior analytical work and practical evaluation.citeturn0file0  

---

### 1  Problem Statement  
- **Operational need.** BRN underpins U.S. Soldier Radio Waveform for tactical MANETs but had *only* analytical performance studies; no open, reusable simulation framework existed.  
- **Specific gaps.**  
  1. End‑to‑end TDMA access mechanism of BRN (autonomous cooperative flooding) lacked packet‑level models.  
  2. CBR—an application that enables multiple simultaneous unicast flows via sector‑based buffering—had no simulation to test node‑role assignment (internal / buffer / external) and timing.citeturn0file0  

### 2  Methodology  
#### 2.1 BRN Modeling  
- **Network model:** 1 source, 1 sink, 11 relays; hop length 1.25 km, radio range 2 km (multi‑hop).  
- **Node stack:** Antenna → radio → *TDMA* module → APP module.  
- **TDMA finite‑state machine:** `INIT → Tick → Send‑PK | Rec‑PK` implements slot‑synchronous flooding; every received packet is forwarded in the next slot. (Fig. 3, p. 2).  

#### 2.2 CBR Modeling  
- **Three node roles** set during a *Contention Logic Channel (CLC)* phase using an RTS/CTS/BUF handshake:  
  $$\text{Node is buffer} \;\Longleftrightarrow\; d_{\text{src}}+d_{\text{sink}} > d_{\text{src–sink}}+N$$
  else *internal*; non‑participants become *external*.citeturn0file0  
- **Timing parameters** computed as  
  $$k_1=\max(0,N-1),\qquad k_2=\max(1,N)+2,\qquad k_3=N$$
  controlling when BUF/CTS messages are emitted (Table I, eqs. 1–3, p. 5).  
- **DLC phase:** periodic data transmission every $M>3$ slots to prevent collision; internal nodes forward, buffers drop, externals absorb.  

#### 2.3 Simulation Experiments  
- **BRN test:** 0.1 s slot, 10 min run ⇒ zero packet loss; constant delay ≈ 0.400 s, matching 4‑slot hop count analytical estimate.  
- **CBR test:** 10 km × 10 km field with two unicast pairs correctly classifies buffer/internal/external nodes (IDs 9‑11,17,19‑21 buffer; 22 external).citeturn0file0  

### 3  Key Contributions  
1. **First open OPNET implementation** of BRN/CBR including TDMA MAC, cooperative flooding, and sector‑based buffering.  
2. **Reusable models** (network, node, FSM) enabling academic/industrial what‑if studies without rewriting lower‑layer code.  
3. **Validation** that simulated packet delivery and delays align with closed‑form expectations, demonstrating model fidelity.  

### 4  Limitations & Future Work (author's)  
- Only static topology for delay study; mobile scenarios require periodic CBR refresh every *CYCLE* seconds.  
- Future extensions: richer physical‑layer effects, mobile topology dynamics, larger‑scale capacity analysis.citeturn0file0