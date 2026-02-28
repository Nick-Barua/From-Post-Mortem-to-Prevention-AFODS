# From Post-Mortem to Prevention: Redefining "Invisible" Pedestrians

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![ISO 26262](https://img.shields.io/badge/Standard-ISO_26262-red)](https://www.iso.org/standard/43464.html)
[![AI-Powered](https://img.shields.io/badge/AI-Multi--Modal-green)](#technical-architecture)

[cite_start]This repository contains the conceptual framework and technical architecture for the **Advanced Falling Object Detection System (AFODS)**[cite: 12]. [cite_start]The project addresses a critical "classification gap" in current ADAS: the inability of standard monocular systems to detect fallen or low-profile pedestrians, which yields a True Positive Rate (TPR) as low as 21.4% at night[cite: 10, 22].

## 📌 Executive Summary
[cite_start]Pedestrians in non-upright postures—those who have fallen due to medical emergencies, intoxication, or primary collisions—represent a significant yet underserved demographic in automotive safety[cite: 8]. [cite_start]Forensic database analyses demonstrate that prostrate road users are disproportionately implicated in hit-and-run incidents[cite: 9, 64]. [cite_start]By integrating **ISO 26262 functional safety standards** and **Multi-Modal AI**, this research demonstrates that detection accuracy for prone individuals can be raised to **98.2% TPR**[cite: 11, 12].



---

## 🛠 Technical Architecture (AFODS)
[cite_start]AFODS integrates four distinct layers to satisfy the redundancy and explainability requirements of **ASIL C/D**[cite: 43]:

* [cite_start]**Spatial Detection:** Utilizes **YOLOv7-Tiny**, achieving a **mAP@0.5 of 91.3%** specifically for prone-person detection[cite: 46].
* [cite_start]**Predictive Kinematics:** An **RNN with Kalman-filter** state estimation that generates alerts **0.3–0.8 seconds before** ground contact[cite: 47].
* [cite_start]**Acoustic Verification:** **MFCC-based classification** distinguishes the acoustic signature of a fall from ambient road noise to reduce false positives[cite: 48].
* [cite_start]**Explainability:** Integrated **SHAP (SHapley Additive explanations)** to provide a forensic audit trail admissible in post-incident reconstruction[cite: 49].

---

## 📊 Performance Benchmarks
[cite_start]AFODS demonstrates superior performance across various environmental conditions compared to baseline monocular systems[cite: 51]:

| Condition | TPR (%) | FPR (%) | mAP@0.5 (%) | Latency (ms) |
| :--- | :---: | :---: | :---: | :---: |
| **Daytime, Clear** | 98.2 | 1.8 | 91.3 | 38 |
| **Night, Dry Road** | 95.6 | 3.1 | 88.7 | 42 |
| **Night, Rain** | 89.4 | 5.2 | 83.1 | 51 |
| *Baseline (Monocular, Night)* | *21.4* | *N/A* | *N/A* | *N/A* |

---

## ⚖️ Functional Safety (ISO 26262)
[cite_start]The detection of fallen pedestrians is classified as a critical safety goal under ISO 26262[cite: 32]. [cite_start]The risk assessment for this scenario maps to **ASIL C-D** based on the following Hazard Analysis and Risk Assessment (HARA)[cite: 33]:

* [cite_start]**Severity (S3):** Life-threatening or fatal injuries[cite: 33, 41].
* [cite_start]**Exposure (E3):** Frequent occurrence in urban/night environments[cite: 33, 41].
* [cite_start]**Controllability (C0/C1):** Near-zero ability for a driver to avoid the hazard once it is within the classification gap[cite: 33, 41].



---

## 📂 Related Repositories
* **[sensor-fusion-fall-detection](https://github.com/Nick-Barua/sensor-fusion-fall-detection)** – Core implementation of multi-modal sensor fusion for human fall detection.
* **[AFODS-Operational-Sequence](https://github.com/Nick-Barua/AFODS-Operational-Sequence)** – Detailed data processing pipelines for the AFODS architecture.

## 📝 Citation
If you use this research or architecture in your work, please cite the original paper:

```bibtex
@article{barua2025postmortem,
  title={From Post-Mortem to Prevention: Redefining "Invisible" Pedestrians through ISO 26262 and Multi-Modal AI},
  author={Barua, Nick},
  journal={SSRN Working Paper},
  year={2025},
  publisher={AN Holdings Co.}
}
