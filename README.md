### Rebecca Tio
**B.S. Computer Science & B.A. Business Economics @ UC Irvine** · Regents’ Scholar · Class of 2027  
**Interests:** Reinforcement Learning Environments · Reward Shaping & Automated Grading · Model Failure Analysis · End-to-End AI Systems

---

### Featured Reinforcement Learning & AI Engineering Work

#### 1. [Power of 2 — Reinforcement Learning & Failure-Mode Analysis for 2048 Optimization](https://github.com/OWNER-USERNAME/POWER-OF-2-REPO)
*RL Modeling & Experimentation Lead (CS 175) · Stack: `Python`, `PyTorch`, `PPO`, `CNN + MLP`, `GAE`*

Designed an RL agent to navigate high-dimensional, stochastic grid states where minor early sub-optimality compounds into terminal board locks. Rather than tuning a single architecture blindly, I ran structured ablations across four paradigms to isolate exact model and reward failure modes:

| Iteration | Approach | Peak / Avg Metric | Diagnosed Failure Mode |
| :--- | :--- | :--- | :--- |
| **1** | Imitation Learning (human play logs) | Max tile: `512` | Covariate shift & compounding error propagation out-of-distribution |
| **2** | Human-in-the-Loop Feedback | Max tile: `128` | Cumulative unseen states caused severe policy hesitation / action freezing |
| **3** | Rule-Based Heuristic Baseline | Max tile: `256` | Static corner/monotonicity weights failed under stochastic tile spawns |
| **4** | Standalone Spatial CNN | Plateaued early | Captured local board patterns but lacked global long-horizon value estimation |
| **Final** | **Dual-Path PPO (CNN + MLP)** | **Avg: `1024` · Win: `10%` (`2048`)** | **Solved local + global state decoupling; `512` floor, `~1.5s/game` execution** |

* **Reward & State Engineering:** Built normalized $\log_2$ state encodings ($\log_2(t)/17$), Generalized Advantage Estimation ($\gamma = 0.997, \lambda = 0.95$), and scale-invariant reward shaping (corner anchoring, empty-cell preservation, monotonicity penalties) to prevent reward hacking over **23M training steps**.

---

#### 2. Domain Generalization for Cancer Histopathology (CS 172B)
*Co-Developer — GNN & Feature Pipeline (CS 172B) · Stack: `Python`, `PyTorch Geometric`, `Phikon (DINOv2)`, `GatConv`, `ABMIL`*

Evaluated out-of-distribution generalization across cross-hospital distribution shifts (`LC25000` $\rightarrow$ `LungHist700`), comparing spatial graph aggregation against set-based attention pooling under tight compute constraints:
* **Compute-Efficient Feature Pipeline:** Froze a domain-pretrained **DINOv2 Phikon** vision encoder with `3x3` patch tiling and stain augmentations to pre-extract `768-dim` feature bags—eliminating backbone retraining overhead and achieving the fastest iteration cycle in the research group.
* **Graph vs. Set Benchmarking:** Implemented a custom **3-layer `GatConv` GNN** combining spatial adjacency and feature-similarity edges (**153K parameters**, **4.38ms inference**), benchmarking generalization and latency against an **ABMIL** baseline (`61.1%` internal accuracy).

---
#### 3. [Kotoba — AI Japanese Language Learning App](https://github.com/YOUR-USERNAME/YOUR-KOTOBA-REPO)
*Project Lead & Product/Systems Designer (48-Hour Hackathon) · Tools: `Lucidchart`, `System Design`, `Technical Documentation`*

Initiated and led a 5-person team during a 48-hour hackathon to prototype an AI-powered Japanese learning application, owning product architecture, data-flow design, and delivery execution:
* **End-to-End System Flow & Latency-Aware UX:** Mapped the full user journey and data-parsing pipeline in **Lucidchart**, proposing **YouTube playlist/lyric scraping** and **incremental API fetching** so users could interact with lessons immediately without blocking on full-batch loads.
* **Technical Specification & Team Triage:** Authored the centralized spec defining the app's data economy and integration boundaries, matched deliverables to teammates' strengths, and re-scoped non-critical features on the fly when half of teammates dropped out mid-sprint.
---

#### 4. High-Throughput Information Retrieval Engine (CS 121)
*Indexing & Pipeline Optimization (CS 121) · Stack: `Python`, `Inverted Indexing`, `Porter Stemming`, `TF-IDF / Ranking`*

* Refactored document tokenization, stemming, and disk-batched inverted index construction to eliminate memory/I/O bottlenecks across large document corpora while preserving retrieval precision.

---

### Technical Stack
* **RL & ML:** `PyTorch`, `PPO`, `Actor-Critic`, `Reward Shaping`, `PyTorch Geometric (GNNs)`, `DINOv2`, `LIME`, `scikit-learn`
* **Languages & Data:** `Python`, `C++`, `SQL`, `NumPy`, `Pandas`
* **Systems & Tooling:** `Git`, `Linux`, `Lucidchart`, `System & Data-Flow Design`

---

> *Note: Selected coursework repositories (`CS 172B`,`CS 121`) are kept private in accordance with UC Irvine academic integrity policies; code samples and architectural walkthroughs are available upon request.*
