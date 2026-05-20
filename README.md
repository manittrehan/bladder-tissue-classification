# Multi-Stage Bladder Tissue Classification and Cancer Localization

An end-to-end medical deep learning pipeline designed to classify endoscopic bladder tissue images and visually locate severe cancerous regions. By leveraging hierarchical classification, optimized image preprocessing, data augmentation, and explainable AI (XAI) gradients, this system replicates clinical workflows to assist urologists in diagnostic decision-making.

---

## 🚀 How It Works (Workflow Pipeline)

The project processes clinical bladder cystoscopy images through a structured four-stage intelligence pipeline:

```text
 🖼️ Raw Image (Zenodo) 
         │
         ▼
 🌓 Preprocessing (Contrast Adjustment)
         │
         ▼
 🔄 Data Augmentation (20° Angle Rotations)
         │
         ▼
 🛑 Stage 1: Binary Classification ──► [Non-Cancerous] vs. [Cancerous]
                                                  │
                                                  ▼
                                 🧠 Stage 2: EfficientNet-B0 Multiclass
                                      ├── High-Grade Cancer
                                      ├── Low-Grade Cancer
                                      ├── Non-Suspicious Tissue
                                      └── Non-Tumorous Lesions (NTL)
                                                  │
                                                  ▼
                                 🗺️ Explainable AI (Grad-CAM Visualization)
                                      └── Radar-style gradient heatmap locating tumor severity
