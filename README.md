# From Post-Mortem to Prevention: Redefining "Invisible" Pedestrians

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![ISO 26262](https://img.shields.io/badge/Standard-ISO_26262-red)](https://www.iso.org/standard/43464.html)
[![AI-Powered](https://img.shields.io/badge/AI-Multi--Modal-green)](#technical-architecture)

This repository contains the conceptual framework and technical architecture for the **Advanced Falling Object Detection System (AFODS)**. The project addresses a critical "classification gap" in current ADAS: the inability of standard monocular architectures to detect fallen or low-profile pedestrians, which currently yields a True Positive Rate (TPR) as low as 21.4% at night.

## 📌 Executive Summary
Pedestrians in non-upright postures—those who have fallen due to medical emergencies, intoxication, or primary collisions—represent a significant yet underserved demographic in automotive safety research. Forensic database analyses demonstrate that prostrate road users are disproportionately implicated in hit-and-run incidents. By integrating **ISO 26262 functional safety standards** and **Multi-Modal AI**, this research demonstrates that detection accuracy for prone individuals can be raised to **98.2% TPR**.



---

## 🛠 Technical Architecture (AFODS)
AFODS integrates four layers to satisfy the redundancy and explainability requirements of **ASIL C/D**:

* **Spatial Detection:** Utilizes **YOLOv7-Tiny**, achieving a **mAP@0.5 of 91.3%** for prone-person detection.
* **Predictive Kinematics:** An **RNN with Kalman-filter** state estimation that generates alerts **0.3–0.8 s** before ground contact.
* **Acoustic Verification:** **MFCC-based classification** distinguishes the acoustic signature of a fall from road noise, reducing false positives.
* **Explainability:** **SHapley Additive explanations (SHAP)** provide a forensic audit trail admissible in post-incident reconstruction.



---

## 📊 Performance Benchmarks
AFODS demonstrates superior performance across various environmental conditions compared to baseline monocular systems:

| Condition | TPR (%) | FPR (%) | mAP@0.5 (%) | Latency (ms) |
| :--- | :---: | :---: | :---: | :---: |
| **Daytime, Clear** | 98.2 | 1.8 | 91.3 | 38 |
| **Night, Dry Road** | 95.6 | 3.1 | 88.7 | 42 |
| **Night, Rain** | 89.4 | 5.2 | 83.1 | 51 |
| *Baseline (Monocular, Night)* | *21.4* | *N/A* | *N/A* | *N/A* |

---

## ⚖️ Functional Safety (ISO 26262)
The detection of fallen pedestrians is a critical safety goal under ISO 26262. The risk assessment for this scenario maps to **ASIL C-D** due to the combination of:

* **Severity (S3):** Life-threatening or fatal injuries.
* **Exposure (E3):** Significant occurrence in urban and night environments.
* **Controllability (C0):** Near-zero ability for a driver to avoid the hazard once it is within the classification gap.

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
