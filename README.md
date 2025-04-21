# Barrage Relay Networks (BRN) Literature Collection

This repository curates primary publications on barrage relay networks—co‑operative, multi‑hop waveforms designed for reliable communication in contested or cluttered radio environments.

---

## Directory Layout
```
tree
.
├── README.md        ← this file
├── papers/          ← PDF archive of cited works
│   └── *.pdf
├── papers.rtf       ← one‑page reference list (rich text)
├── references.bib   ← BibTeX entries matching the PDFs
└── summaries/       ← Markdown summaries of papers
    └── *.md
```

---

## Papers

| Year | Title&nbsp;·&nbsp;PDF | Authors† | Venue / Journal | Topical Note | Summary |
|------|-----------------------|----------|-----------------|--------------|---------|
| 2010 | *[Barrage Relay Networks: System & Protocol Design](papers/2010_Halford_BRN_System_Protocol_Design.pdf)* | Halford TR, Chugg KM, Polydoros A | IEEE PIMRC 2010 | Foundational BRN architecture and medium‑access protocol. | [Summary](summaries/2010_Halford_BRN_System_Protocol_Design.md) |
| 2014 | *[Unicast Barrage Relay Networks: Outage Analysis & Optimization](papers/2014_Talarico_Unicast_BRN_Outage_Analysis.pdf)* | Talarico S, Valenti MC, Halford TR | IEEE MILCOM 2014 | Closed‑form outage probability for unicast BRN links. | [Summary](summaries/2014_Talarico_Unicast_BRN_Outage_Analysis.md) |
| 2016 | *[Controlled Barrage Regions: Stochastic Modeling, Analysis, and Optimization](papers/2016_Talarico_Controlled_Barrage_Regions.pdf)* | Talarico S, Valenti MC, Halford TR | IEEE MILCOM 2016 | Spatial partitioning and stochastic optimisation of relay regions. | [Summary](summaries/2016_Talarico_Controlled_Barrage_Regions.md) |
| 2019 | *[Simulation Studies on Barrage Relay Networks](papers/2019_Na_Simulation_Studies_BRN.pdf)* | Na Q, Wang X, Liu Y | CAA YAC 2019 | ns‑3‑based performance evaluation across traffic loads. | [Summary](summaries/2019_Na_Simulation_Studies_BRN.md) |
| 2021 | *[Geometry‑Informed Transmission Strength Scaling in Barrage Relay Networks](papers/2021_Kraczek_Geometry_Informed_Transmission.pdf)* | Kraczek B, Woolsey N | IEEE MILCOM 2021 | Link‑distance–aware transmit‑power adaptation. | [Summary](summaries/2021_Kraczek_Geometry_Informed_Transmission.md) |
| 2021 | *[Predicting Needs in Future Decentralized Networks Through Analysis of Barrage Relay Networks](papers/2021_Woolsey_Predicting_Future_Network_Needs.pdf)* | Woolsey N, Ji M, Kraczek B | IEEE WCNC 2021 | Forecasting topology stressors in tactical BRNs. | [Summary](summaries/2021_Woolsey_Predicting_Future_Network_Needs.md) |
| 2023 | *[Distributed Space‑Time Block Coding for Barrage Relay Networks](papers/2023_Lee_Distributed_Space_Time_Block_Coding.pdf)* | Lee K‑H, Lee H, Choi J, Park S, Jung BC | IEEE MILCOM 2023 | Cooperative STBC scheme tailored to barrage relays. | [Summary](summaries/2023_Lee_Distributed_Space_Time_Block_Coding.md) |

† Author list truncated to first few names for brevity; see PDFs or `references.bib` for full author roles.

---

## Math Support

The paper summaries use LaTeX-style math notation which is rendered correctly on GitHub:

- Inline math: $E = mc^2$
- Display math: 
$$P_{\text{outage}} = \mathbb{P}(C < R)$$

Where $C$ is channel capacity and $R$ is the transmission rate.