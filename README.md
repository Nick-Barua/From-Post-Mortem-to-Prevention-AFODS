# From Post-Mortem to Prevention: A Multi-Modal AI System for Detecting Pedestrians Lying on the Road

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20035268.svg)](https://doi.org/10.5281/zenodo.20035268)
[![License: Apache-2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Vehicles 2026](https://img.shields.io/badge/Journal-Vehicles%202026-green)](https://www.mdpi.com/journal/vehicles)
[![ASIL D](https://img.shields.io/badge/ISO%2026262-ASIL%20D-red)](https://www.iso.org/standard/68383.html)

**Nick Barua¹ · Masahito Hitosugi¹**

¹ Department of Legal Medicine, Shiga University of Medical Science, Otsu, Shiga, Japan

> **Barua, N., & Hitosugi, M. (2026).** *A Multi-Modal AI System for Detecting Pedestrians Lying on the Road: Simulation-Based Safety and Injury Risk Analysis.* **Vehicles** *(In Submission).* Archival DOI: [10.5281/zenodo.20035268](https://doi.org/10.5281/zenodo.20035268)

---

## Graphical Abstract

![Graphical Abstract](GA.png)

---

## Overview

This repository archives the ISO 26262 safety framework, reproducible analysis notebook, and all manuscript figures for the 2026 *Vehicles* submission listed above.

Pedestrians lying on the road — collapsed through medical emergency, intoxication, or displacement following a prior collision — represent a disproportionately lethal and systematically underdetected category in road traffic safety. Forensic database analyses derived from Japan's national police records document a **fatality rate of 33.0%** for collisions involving pedestrians in this posture, more than double the rate for upright pedestrian collisions. Standard Advanced Driver-Assistance Systems (ADAS) yield a **True Positive Rate (TPR) of only 21.4%** under night conditions for this posture — a classification gap of **73.3 percentage points**.

The **Advanced Falling Object Detection System (AFODS)** addresses this gap through multi-modal sensor fusion, achieving **95.6–98.2% TPR** across environmental conditions in simulation. This repository constitutes the companion code and data archive for the three original contributions of the 2026 paper: a formal ISO 26262 Hazard Analysis and Risk Assessment (HARA), a three-stage quantitative injury-risk model, and a medicolegal SHAP interpretability framework.

---

## Key Findings

| Metric | Value |
|--------|-------|
| Daytime TPR (AFODS) | **98.2%** (95% CI: 97.4–98.8%) |
| Night / dry TPR (AFODS) | **95.6%** (95% CI: 94.3–96.7%) |
| Night / rain TPR (AFODS) | **89.4%** (95% CI: 87.2–91.3%) |
| Improvement vs. monocular RGB baseline | **+76.8 pp** (*p* < 0.001, McNemar's test) |
| AUC | **0.981** (95% CI: 0.976–0.985) |
| Mean end-to-end latency | **46.5 ms** (SD 4.1 ms) |
| ISO 26262 ASIL classification | **ASIL D** (urban night; post-primary collision) |

### Monte Carlo Uncertainty Analysis (*N* = 100,000 iterations)

| Scenario | P(AIS ≥ 5) MC Mean | 95% Credible Interval |
|----------|--------------------|-----------------------|
| No ADAS (full-speed impact, 50 km/h) | **66.2%** | 21.6–82.3% |
| Monocular RGB baseline | **41.6%** | 4.9–78.0% |
| AFODS — worst case (night/rain) | **0.7%** | 0.0–3.7% |
| AFODS — daytime | **≈ 0%** | — |

---

## Three-Stage Injury-Risk Model

The paper introduces an explicit quantitative linkage between system detection latency and clinical outcome via three sequential equations:

**Stage 1 — Kinematics:**

$$v_{\text{impact}} = \max\!\left(0,\; v_0 - a \cdot (t_{\text{avail}} - t_d)\right)$$

**Stage 2 — Biomechanics (THUMS-calibrated):**

$$\text{HIC} = k \cdot v_{\text{impact}}^{2.5} \qquad (k \approx 4.8)$$

**Stage 3 — Clinical Risk (Mertz et al., 1997):**

$$P(\text{AIS} \geq 5) = \frac{1}{1 + \exp(-\alpha + \beta \cdot \ln \text{HIC})}$$

*Parameters (adult 50th-percentile male):* α = −17.72, β = 2.32.

---

## ISO 26262 HARA Summary

| Scenario | S | E | C | ASIL |
|----------|---|---|---|------|
| Urban road, daytime | S3 | E3 | C2 | **C** |
| Urban road, night | S3 | E3 | C3 | **D** |
| High-speed road, night | S3 | E2 | C3 | **C** |
| Post-primary collision, multi-vehicle | S3 | E3 | C3 | **D** |

*S = Severity; E = Exposure; C = Controllability. Determined per ISO 26262-3:2018, Annex B.*

---

## Repository Contents

| File | Description |
|------|-------------|
| `AFODS_Supplementary_Analysis.ipynb` | Reproducible Python notebook: Equations 1–3, Monte Carlo propagation (*N* = 100,000), and all plot-generation scripts |
| `Figure_1.png` | AFODS Multi-Modal Functional Architecture with SHAP feature attribution panel |
| `Figure_2.png` | AFODS Translational Validation Pipeline |
| `Figure_S1.png` | Monte Carlo uncertainty propagation — P(AIS ≥ 5) distributions across four detection scenarios |
| `Figure_S2.png` | Tornado plot — one-way sensitivity of P(AIS ≥ 5) to primary model inputs |
| `Figure_S3.png` | Injury risk curve — continuous P(AIS ≥ 5) as a function of HIC with AFODS operating points overlaid |
| `GA.png` | Graphical abstract |
| `CITATION.cff` | Machine-readable citation metadata |
| `LICENSE` | Apache-2.0 |

---

## Manuscript Figures

### Figure 1 — AFODS Functional Architecture
![Figure 1](Figure_1.png)
*Multi-modal sensor fusion (LWIR thermal + NIR + ultrasonic) across four processing layers. Lower panel: mean SHAP feature contributions across positive detections.*

### Figure 2 — Translational Validation Pipeline
![Figure 2](Figure_2.png)
*Roadmap from current simulation-based feasibility through hardware-in-the-loop testing, instrumented ATD proving-ground validation, and regulatory extension.*

### Figure S3 — Injury Risk Curve
![Figure S3](Figure_S3.png)
*Continuous mapping of HIC to P(AIS ≥ 5) with all four AFODS operating points and 95% Monte Carlo credible-interval error bars overlaid. Standard regulatory HIC thresholds (HIC 1000, HIC 1500) are indicated.*

---

## Archived Supplementary Materials

All supplementary materials are openly archived on Zenodo:

> **DOI: [10.5281/zenodo.20035268](https://doi.org/10.5281/zenodo.20035268)**

Archived assets include: `AFODS_Supplementary_Analysis.ipynb` (Equations 1–3 logic and plot scripts), and high-resolution versions of Figures S1, S2, and S3.

---

## Citation

### Primary 2026 Study *(In Submission)*

Barua, N., & Hitosugi, M. (2026). A Multi-Modal AI System for Detecting
Pedestrians Lying on the Road: Simulation-Based Safety and Injury Risk
Analysis. Vehicles (In Submission).
https://doi.org/10.5281/zenodo.20035268

### Baseline 2025 Study
Barua, N., & Hitosugi, M. (2025). Advanced Multi-Modal Sensor Fusion
System for Detecting Falling Humans: Quantitative Evaluation for Enhanced
Vehicle Safety. Vehicles, 7(4), 149.
https://doi.org/10.3390/vehicles7040149

Or use the `CITATION.cff` file for automatic citation export via GitHub.

---

## Conflict of Interest

N.B. declares a filed patent — Japanese Patent Application No. 2025-167440 (filed 3 October 2025) — on the AFODS technology described in this paper. M.H. declares no conflicts of interest.

---

## License

This repository is released under the [Apache-2.0 License](LICENSE).

All simulation data and parameters are derived from the manuscript text. No original human participant data were collected. All performance figures are simulation-based; prototype validation on real-world hardware is required before deployment claims can be made.
