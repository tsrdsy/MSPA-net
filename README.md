# MSPA-Net: Multi-dimensional Orthogonality-penalized Sharpened Prototype Attention Network

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0%2B-EE4C2C.svg)](https://pytorch.org/)
[![Task](https://img.shields.io/badge/Task-Gait%20Analysis-blue.svg)]()

## ⚠️ Code Availability

**The full source code and training scripts will be released in this repository upon acceptance of the paper.** 

Currently, this repository serves as a placeholder for upcoming release. Stay tuned!

> **Official implementation of paper:** "MSPA-Net: A Multi-dimensional Orthogonality-penalized Sharpened Prototype Attention Network for Complex Pathological Gait Screening and Differentiation"

## Overview

MSPA-Net is a novel deep learning framework for processing multi-cohort gait datasets using wearable sensor data. It performs **21 binary classification tasks** including screening against healthy subjects (HS) and differential diagnosis among six pathologies: hip/knee osteoarthritis (HOA/KOA), stroke (CVA), Parkinson's disease (PD), chemotherapy-induced peripheral neuropathy (CIPN), and radiation-induced leukoencephalopathy (RIL).

## Key Innovations

1. **Sharpened Prototype Attention (SPA):** Integrates a sharpening factor (lambda=2.0) to address attention dilution and capture subtle spatio-temporal gait details
2. **Orthogonality Regularization:** Enforces feature diversity (L_ortho) to prevent homogeneity among prototypes
3. **Multi-dimensional Divide-and-Conquer:** Decomposes gait signals across Spatial (body parts), Spectral (multi-scale conv), and Temporal (attention pooling) dimensions

## Performance

MSPA-Net demonstrates superior performance across pathology screening and differential diagnosis tasks:

- **CVA screening:** AUC-PR of 99.3%, Recall of 98.5%
- **CIPN screening:** Improved AUC-PR from 62.4% (baseline) to 80.9%

## Model Architecture

<p align="center">
  <img src="assets/MSPA-Net.png" alt="MSPA-Net Architecture" width="600">
</p>

*Figure 1: The overall architecture of MSPA-Net. The model adopts a "Divide-and-Conquer, Expert, Orthogonal" strategy, featuring multi-scale convolution, temporal attention pooling, and the proposed Orthogonality-penalized Sharpened Prototype Attention (SPA) mechanism.*

## Project Structure (Coming Soon)

Upon release, the repository will include:

```
MSPA-net/
├── config.py             # Global configuration
├── train.py              # Main training script
├── requirements.txt      # Python dependencies
├── README.md             # Project documentation
├── LICENSE               # MIT License
└── src/
    ├── base.py           # Baseline model
    ├── MSPA_net.py       # MSPA-Net architecture
    └── data_loader.py    # Data loading and preprocessing
```

## Dataset

This project uses the Voisard et al. (2025) clinical gait dataset.

**Download:** https://doi.org/10.1038/s41597-025-05959-w

**Dataset Structure:**
```
datasets/data/
├── healthy/
│   └── HS/           # Healthy Subjects
├── ortho/
│   ├── HOA/          # Hip Osteoarthritis
│   ├── KOA/          # Knee Osteoarthritis
│   └── ACL/          # ACL Injury
└── neuro/
    ├── PD/           # Parkinson's Disease
    ├── CVA/          # Cerebrovascular Accident (Stroke)
    ├── CIPN/         # Chemotherapy-Induced Peripheral Neuropathy
    └── RIL/          # Radiation-Induced Leukoencephalopathy
```

## Usage (Coming Soon)

Upon release, the repository will provide:

- **Training scripts** with comprehensive command-line arguments
- **21 pre-configured tasks** for screening and differential diagnosis
- **Pretrained models** for immediate inference
- **Detailed documentation** for model customization

## Evaluation Metrics

The model is evaluated using comprehensive medical metrics:
- **AUC:** Area Under ROC Curve
- **AUC-PR:** Area Under Precision-Recall Curve
- **Accuracy:** Overall classification accuracy
- **F1 Score:** Harmonic mean of precision and recall
- **Sensitivity (Recall):** True positive rate
- **Specificity:** True negative rate
- **Precision:** Positive predictive value

## Results

Comparative performance on key clinical screening tasks (AUC-PR):

| Task | Baseline | MSPA-Net | Improvement |
|-------|-----------|------------|-------------|
| CVA vs HS | 98.4% | 99.5% | +1.1% |
| CIPN vs HS | 63.5% | 78.0% | +14.5% |
| HOA vs HS | 84.9% | 94.1% | +9.2% |
| PD vs HS | 56.0% | 67.3% | +11.3% |

## Citation

If you use this code or models in your research, please cite:

### 1. MSPA-Net (This Work)
```bibtex
@article{Shen2026MSPANet,
  title={MSPA-Net: A Multi-dimensional Orthogonality-penalized Sharpened Prototype Attention Network for Complex Pathological Gait Screening and Differentiation},
  author={Shen, Aoli and Chen, Xinpeng and Yang, Chaoxiang and Lin, Zhangdi and Xu, Hanlin},
  year={2026}
}
```

### 2. Original Dataset
```bibtex
@article{voisard2025dataset,
  title={A Dataset of Clinical Gait Signals with Wearable Sensors from Healthy, Neurological, and Orthopedic Cohorts},
  author={Voisard, C. and Barrois, R. and l'Escalopier, N. and others},
  journal={Scientific Data},
  volume={12},
  pages={1674},
  year={2025},
  publisher={Nature Publishing Group},
  doi={10.1038/s41597-025-05959-w},
  url={https://doi.org/10.1038/s41597-025-05959-w}
}
```

### 3. Baseline Framework
```bibtex
@article{sadeghsalehi2025dual,
  title={A Dual-Use Framework for Clinical Gait Analysis: Attention-Based Sensor Optimization and Automated Dataset Auditing},
  author={Sadeghsalehi, Hamidreza},
  journal={arXiv preprint arXiv:2511.02047},
  year={2025},
  url={https://doi.org/10.48550/arXiv.2511.02047}
}
```

## License

This project is licensed under the MIT License - see LICENSE file for details.

## Contact

For questions regarding MSPA-Net architecture or implementation, please contact:
- Chaoxiang Yang - tsrdsy@gmail.com
