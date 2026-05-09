# **AFODS: Advanced Falling Object Detection System** 🛡️
**[Archival Concept DOI: 10.5281/zenodo.20035268]**

### **Project Overview**
This repository hosts the **ISO 26262 Safety Framework** and technical implementation for the 2026 research: *"A Multi-Modal AI System for Detecting Pedestrians Lying on the Road: Simulation-Based Safety and Injury Risk Analysis"*. 

Standard Advanced Driver-Assistance Systems (ADAS) yield a True Positive Rate (TPR) of only **21.4%** for detecting pedestrians lying on the road under night conditions. The AFODS framework addresses this **73.3 percentage-point (pp)** classification gap, achieving **95.6–98.2% TPR** in simulation.

### **🚀 Key Research Findings (N=100,000 Monte Carlo Analysis)**
* **Baseline Fatality Risk (No ADAS):** 66.2% MC Mean (95% CI: 21.6–82.3%).
* **AFODS Fatality Risk (Night/Rain):** 0.7% MC Mean (95% CI: 0.0–3.7%).
* **Mean System Latency:** 46.5 ms (SD 4.1 ms).
* **Safety Gain:** Projected reduction in fatal injury probability from 76.5% (uncontrolled) to <1% under AFODS.
* **ASIL D Compliance:** Hazard Analysis and Risk Assessment (HARA) identifying the pedestrian run-over hazard as **ASIL D** — the highest safety-critical tier.

### **📊 Main Manuscript Figures**
* **Figure 1: AFODS Functional Architecture.** Multi-modal sensor fusion (Thermal IR + NIR + Ultrasonic) with a SHAP-based explainability audit trail.
* **Figure 2: AFODS Translational Validation Pipeline.** Strategic roadmap for migrating the framework from simulation to real-world regulatory integration.
* **Figure S3: Injury Risk Curve.** Continuous mapping of HIC to fatal injury probability (P(AIS ≥ 5)).

### **🔢 Mathematical Foundation**
The repository implements the three-stage injury-risk model:
1. **Kinematics (Eq 1):** v_impact = max(0, v0 - a · (t_avail - t_d))
2. **Biomechanics (Eq 2):** HIC = k · v_impact^2.5 (where k ≈ 4.8)
3. **Clinical Risk (Eq 3):** P(AIS ≥ 5) = 1 / (1 + exp(-α + β · ln HIC))
   * **Parameters (Adult 50th-percentile male): α = -17.72, β = 2.32**

### **📦 Technical Assets (v1.2.0)**
* **AFODS_Supplementary_Analysis.ipynb:** Complete Python notebook containing the Equation 1–3 logic, Monte Carlo uncertainty propagation, and plot-generation scripts.
* **High-Resolution Figures:** Standalone PNG versions of all manuscript and supplementary figures (Figure 1, 2, S1, S2, S3).

### **📝 Citations**
**Primary 2026 Study (In Submission):**
Barua, N., & Hitosugi, M. (2026). *A Multi-Modal AI System for Detecting Pedestrians Lying on the Road: Simulation-Based Safety and Injury Risk Analysis.* Vehicles (In Submission).

**Baseline 2025 Study:**
Barua, N., & Hitosugi, M. (2025). *Advanced Multi-Modal Sensor Fusion System for Detecting Falling Humans.* Vehicles, 7(4), 149. [https://doi.org/10.3390/vehicles7040149](https://doi.org/10.3390/vehicles7040149).

### **⚖️ Patent Disclosure**
AFODS technology is the subject of **Japanese Patent Application No. 2025-167440** (Filing Date: 3 October 2025).
