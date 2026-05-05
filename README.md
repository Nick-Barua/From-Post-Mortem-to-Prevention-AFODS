# A Multi-Modal AI System for Detecting Pedestrians Lying on the Road: Simulation-Based Safety and Injury Risk Analysis 🛡️

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20035269.svg)](https://doi.org/10.5281/zenodo.20035269)
[![License: Apache-2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

### **Project Overview**
This repository hosts the **ISO 26262 Safety Framework** and technical implementation for the 2026 research on detecting pedestrians lying on the road. While traditional ADAS systems yield a True Positive Rate (TPR) of only **21.4%** at night for non-upright pedestrians, the AFODS framework achieves **95.6–98.2% TPR** in simulation.

This project formalises the transition from forensic "post-mortem" data to real-time vehicular safety intervention.

---

### **🚀 Key Research Findings (N=100,000 Monte Carlo Analysis)**

* **Baseline Fatality Risk (No ADAS):** 66.2% MC Mean 
* **AFODS Fatality Risk (Night/Rain):** 0.7% MC Mean 
* **Safety Improvement:** >98% reduction in clinical fatality probability ($P(AIS \geq 5)$).
* **ASIL D Compliance:** Formal Hazard Analysis and Risk Assessment (HARA) identifying the pedestrian run-over hazard as **ASIL D**—the highest safety-critical tier.

---

### **📊 Main Manuscript Figures**

* **Figure 1: AFODS Functional Architecture.** Multi-modal sensor fusion (Thermal IR + NIR) with a SHAP-based explainability audit trail.
* **Figure 2: Injury Risk Curve.** Continuous mapping of HIC to fatal injury probability ($P(AIS \geq 5)$) showing the nonlinear safety gains of reduced detection latency.
* **Figure 3: Translational Validation Pipeline.** Strategic roadmap for migrating the framework from simulation to real-world regulatory and hardware integration.

---

### **📦 Technical Supplementary Materials (v1.2.0)**
The following artifacts support the 2026 study and are archived via **Zenodo (DOI: 10.5281/zenodo.20035269)**:

#### **1. Reproducible Notebook**
* **`AFODS_Supplementary_Analysis.ipynb`**: Complete Python notebook containing the Equation 1–3 logic, Monte Carlo uncertainty propagation, and plot-generation scripts.

#### **2. Supplementary Figures**
* **Figure S1 (Monte Carlo Uncertainty):** Histograms of $P(AIS \geq 5)$ distribution showing near-zero fatality risk under effective AFODS detection.
* **Figure S2 (Tornado Plot):** Quantitative one-way sensitivity analysis proving that detection latency ($t_d$) is the dominant driver of injury outcomes.

---

### **🔢 Mathematical Foundation**
The supplementary code implements the three-stage injury-risk model:
1. **Kinematic:** $v_{impact} = \max(0, v_0 - a \cdot (t_{avail} - t_d))$
2. **Biomechanical:** $HIC = k \cdot v_{impact}^{2.5}$
3. **Clinical:** $P(AIS \geq 5) = \frac{1}{1 + \exp(-\alpha + \beta \cdot \ln HIC)}$

---

### **📝 Citations**

**Primary 2026 Study (In Submission):**
> Barua, N., & Hitosugi, M. (2026). *A Multi-Modal AI System for Detecting Pedestrians Lying on the Road: Simulation-Based Safety and Injury Risk Analysis.* Vehicles (In Submission).

**Baseline 2025 Study:**
> Barua, N., & Hitosugi, M. (2025). Advanced Multi-Modal Sensor Fusion System for Detecting Falling Humans. *Vehicles*, 7(4), 149. [https://doi.org/10.3390/vehicles7040149](https://doi.org/10.3390/vehicles7040149).

---
*All simulation data and parameters are derived from the manuscript text. No original human participant data were collected.*
