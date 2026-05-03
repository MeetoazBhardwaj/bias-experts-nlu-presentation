# bias-experts-nlu-presentation
Academic presentation on EMNLP 2023 paper “Improving Bias Mitigation through Bias Experts in Natural Language Understanding”, covering dataset bias, softmax limitations, one-vs-rest bias experts, bias amplification, Product-of-Experts training, and OOD generalization.


# Improving Bias Mitigation Through Bias Experts in Natural Language Understanding

This repository contains an academic presentation on the EMNLP 2023 paper **“Improving Bias Mitigation through Bias Experts in Natural Language Understanding”** by Eojin Jeon, Mingyu Lee, Juhyeong Park, Yeachan Kim, Wing-Lam Mok, and Sangkeun Lee.

The presentation explains how dataset bias affects Natural Language Understanding models and why conventional multi-class auxiliary models may fail to properly identify biased examples. It focuses on the paper’s key argument that the standard softmax-based multi-class objective can be sub-optimal for bias detection because it prevents auxiliary models from sufficiently overfitting to spurious bias patterns.

## Repository Contents

```text
.
├── README.md
├── presentation/
│   └── Improving_Bias_Mitigation_Through_Bias_Experts.pdf
└── references/
    └── paper-notes.md
