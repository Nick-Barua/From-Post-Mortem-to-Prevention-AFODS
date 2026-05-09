# **AFODS: Advanced Falling Object Detection System** 🛡️
**[Archival Concept DOI: 10.5281/zenodo.20035268]**

### **Project Overview**
[cite_start]This repository hosts the **ISO 26262 Safety Framework** [cite: 41, 124, 125] [cite_start]and technical implementation for the 2026 research: *"A Multi-Modal AI System for Detecting Pedestrians Lying on the Road: Simulation-Based Safety and Injury Risk Analysis"*. 

[cite_start]Standard Advanced Driver-Assistance Systems (ADAS) yield a True Positive Rate (TPR) of only **21.4%** for detecting pedestrians lying on the road under night conditions[cite: 8, 155]. [cite_start]The AFODS framework addresses this **73.3 percentage-point (pp)** classification gap [cite: 8, 15, 171][cite_start], achieving **95.6–98.2% TPR** in simulation[cite: 12, 153, 154].

### **🚀 Key Research Findings (N=100,000 Monte Carlo Analysis)**
* [cite_start]**Baseline Fatality Risk (No ADAS):** 66.2% MC Mean (95% CI: 21.6–82.3%).
* [cite_start]**AFODS Fatality Risk (Night/Rain):** 0.7% MC Mean (95% CI: 0.0–3.7%)[cite: 185].
* [cite_start]**Mean System Latency:** 46.5 ms (SD 4.1 ms)[cite: 13, 162].
* [cite_start]**Safety Gain:** Projected reduction in fatal injury probability from 76.5% (uncontrolled) to <1% under AFODS[cite: 14, 178].
* [cite_start]**ASIL D Compliance:** Hazard Analysis and Risk Assessment (HARA) identifying the pedestrian run-over hazard as **ASIL D**[cite: 130, 133].

### **📊 Main Manuscript Figures**
* [cite_start]**Figure 1: AFODS Functional Architecture.** Multi-modal sensor fusion (Thermal IR + NIR + Ultrasonic) with a SHAP-based explainability audit trail [cite: 104-110].
* [cite_start]**Figure 2: AFODS Translational Validation Pipeline.** Strategic roadmap for migrating the framework from simulation to real-world regulatory integration[cite: 252].
* [cite_start]**Figure S3: Injury Risk Curve.** Continuous mapping of HIC to fatal injury probability ($P(AIS \geq 5)$)[cite: 207, 215].

### **🔢 Mathematical Foundation**
[cite_start]The repository implements the three-stage injury-risk model [cite: 69-73]:
1. [cite_start]**Kinematics (Eq 1):** $v_{impact} = \max(0, v_0 - a \cdot (t_{avail} - t_d))$ [cite: 75-78].
2. [cite_start]**Biomechanics (Eq 2):** $HIC = k \cdot v_{impact}^{2.5}$ (where $k \approx 4.8$)[cite: 82, 86, 88].
3. [cite_start]**Clinical Risk (Eq 3):** $P(AIS \geq 5) = \frac{1}{1 + \exp(-\alpha + \beta \cdot \ln HIC)}$ [cite: 91-93].
   * [cite_start]*Parameters (Adult 50th-percentile male): $\alpha = -17.72$, $\beta = 2.32$*[cite: 94].

### **📦 Technical Assets (v1.2.0)**
* [cite_start]**AFODS_Supplementary_Analysis.ipynb:** Complete Python notebook containing the Equation 1–3 logic, Monte Carlo uncertainty propagation, and plot-generation scripts[cite: 284].
* [cite_start]**High-Resolution Figures:** Standalone PNG versions of Figure 1, 2, S1, S2, and S3 [cite: 281-283].

### **📝 Citations**
**Primary 2026 Study (In Submission):**
Barua, N., & Hitosugi, M. (2026). [cite_start]*A Multi-Modal AI System for Detecting Pedestrians Lying on the Road: Simulation-Based Safety and Injury Risk Analysis.* Vehicles (In Submission)[cite: 1, 2].

**Baseline 2025 Study:**
Barua, N., & Hitosugi, M. (2025). [cite_start]*Advanced Multi-Modal Sensor Fusion System for Detecting Falling Humans.* Vehicles, 7(4), 149. [https://doi.org/10.3390/vehicles7040149](https://doi.org/10.3390/vehicles7040149)[cite: 6, 313, 314].
