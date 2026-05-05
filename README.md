# From Post-Mortem to Prevention: Redefining ‘Invisible’ Pedestrians 🛡️

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18824297.svg)](https://doi.org/10.5281/zenodo.18824297)
[![License: Apache-2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)


### **Project Overview**
This repository hosts the **ISO 26262 Safety Framework** and technical implementation for the 2026 research on detecting pedestrians lying on the road. While traditional ADAS systems yield a True Positive Rate (TPR) of only **21.4%** at night for non-upright pedestrians, the AFODS framework achieves **95.6–98.2% TPR** in simulation.

This project formalises the transition from forensic "post-mortem" data to real-time vehicular safety intervention.

---

### **🚀 Key 2026 Research Features**

* **ASIL D Compliance:** Formal Hazard Analysis and Risk Assessment (HARA) identifying the pedestrian run-over hazard as **ASIL D**—the highest safety-critical tier.
* **Three-Stage Injury-Risk Model:** A validated computational pipeline translating detection latency ($t_d$) into **Head Injury Criterion (HIC)** and fatal injury probability ($P(AIS \geq 5)$).
* **Monte Carlo Uncertainty Analysis:** Reproducible results from **$N=100,000$** iterations verifying the robustness of risk reduction (76.5% baseline to 0.4% with AFODS).
* **Forensic Explainability (XAI):** Implementation of **SHAP audit trails** for post-incident reconstruction and medicolegal accountability.

---

### **📦 Technical Supplementary Materials (v1.1.0)**
The following artifacts support the 2026 study and are archived via **Zenodo (DOI: 10.5281/zenodo.18824034)**:

#### **1. Reproducible Notebook**
* **`AFODS_Supplementary_Analysis.ipynb`**: Complete Python notebook containing the Equation 1–3 logic and plot-generation scripts.

#### **2. New Technical Figures**
* **Figure S1 (Monte Carlo Uncertainty):** Histograms of $P(AIS \geq 5)$ distribution showing near-zero fatality risk under effective AFODS detection.
* **Figure S2 (Tornado Plot):** Quantitative one-way sensitivity analysis proving that detection latency is the dominant driver of injury outcomes.
* **Figure S3 (Injury Risk Curve):** Continuous mapping of HIC to fatal injury probability with AFODS operating points overlaid.

---

### **🔢 Mathematical Foundation**
The supplementary code implements the three-stage model:
1. **Kinematic:** $v_{impact} = \max(0, v_0 - a \cdot (t_{avail} - t_d))$
2. **Biomechanical:** $HIC = k \cdot v_{impact}^{2.5}$
3. **Clinical:** $P(AIS \geq 5) = \frac{1}{1 + \exp(-\alpha + \beta \cdot \ln HIC)}$

---

### **📝 Citations**

**Primary 2026 Study (In Preparation):**
> Barua, N., & Hitosugi, M. (2026). *A Multi-Modal AI System for Detecting Pedestrians Lying on the Road: Simulation-Based Safety and Injury Risk Analysis.* Vehicles (In Preparation).

**Baseline 2025 Study:**
> Barua, N., & Hitosugi, M. (2025). Advanced Multi-Modal Sensor Fusion System for Detecting Falling Humans. *Vehicles*, 7(4), 149. [https://doi.org/10.3390/vehicles7040149](https://doi.org/10.3390/vehicles7040149).

---
*All simulation data and parameters are derived from the manuscript text. No original human participant data were collected.*
