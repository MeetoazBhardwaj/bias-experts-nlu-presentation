# Improving Bias Mitigation Through Bias Experts in Natural Language Understanding

This repository contains an academic presentation on the EMNLP 2023 paper **“Improving Bias Mitigation through Bias Experts in Natural Language Understanding”** by Eojin Jeon, Mingyu Lee, Juhyeong Park, Yeachan Kim, Wing-Lam Mok, and Sangkeun Lee.

The presentation explains how dataset bias affects Natural Language Understanding (NLU) models and why conventional multi-class auxiliary models may fail to identify biased examples effectively. It focuses on the paper’s central argument: standard softmax-based multi-class objectives can be sub-optimal for bias detection because effective bias detection often requires auxiliary models to strongly learn spurious bias patterns.

## Repository Contents

```text
.
├── README.md
├── presentation/
│   ├── Improving_Bias_Mitigation_Through_Bias_Experts.pdf
│   └── Improving_Bias_Mitigation_Through_Bias_Experts.pptx
├── assets/
│   └── preview.png
├── references/
│   └── paper-notes.md
├── docs/
│   └── presentation-summary.md
├── .gitignore
└── LICENSE
```

> Add your `.pdf` and `.pptx` files inside the `presentation/` folder.

## Presentation Overview

The presentation covers:

- Dataset bias in Natural Language Processing
- Spurious correlations in NLU tasks
- Limitations of multi-class auxiliary models
- Why softmax competition can weaken bias identification
- One-vs-Rest training for bias experts
- Bias amplification mechanism
- Product-of-Experts training
- Out-of-distribution generalization results
- Ablation study findings
- Confidence analysis of bias experts
- Extension of the method to vision datasets
- Strengths, limitations, and ethical considerations

## Key Idea

Many debiasing methods use auxiliary models to identify biased examples. However, these auxiliary models are often trained using standard multi-class objectives. The paper argues that this can be problematic because effective bias detection may require the model to strongly learn or overfit to bias attributes.

The proposed method introduces separate **bias experts** using a One-vs-Rest framework. Each bias expert is trained to focus on biased examples related to a specific target class. These experts are then used with a Product-of-Experts approach to reduce the influence of biased patterns during main model training.

## Method Summary

### 1. One-vs-Rest Dataset Construction

For each class, a binary dataset is created so that each bias expert learns independently.

### 2. Bias Expert Training with Amplification

Bias experts are trained to assign higher confidence to biased examples and lower confidence to bias-conflicting examples.

### 3. Product-of-Experts Training

The trained bias experts are frozen and combined with the main model so that examples confidently identified as biased receive reduced influence.

## Datasets Discussed

| Dataset | Task Type | OOD Evaluation |
|---|---|---|
| MNLI | Natural Language Inference | HANS |
| FEVER | Fact Verification | FEVER Symmetric |
| QQP | Paraphrase Detection | PAWS |

The paper also reports generalization to vision datasets such as BAR and NICO.

## Main Findings

The Bias Experts approach shows consistent out-of-distribution improvements across benchmark datasets. The presentation highlights results on HANS, FEVER Symmetric, and PAWS and compares the method against several debiasing baselines.

The ablation study also shows that both components — One-vs-Rest training and bias amplification — are important for performance.

## Critical Evaluation

### Strengths

- Identifies a structural limitation in standard multi-class bias learning
- Works without requiring explicit bias labels
- Modular and model-agnostic design
- Improves out-of-distribution generalization
- Can be extended beyond NLP to vision tasks

### Limitations

- Memory cost increases with the number of classes
- Requires tuning of the amplification hyperparameter
- May involve a trade-off between in-distribution performance and robustness
- Raises ethical questions around balancing minority robustness and majority performance

## How to View the Presentation

After adding the presentation files, open:

- [`presentation/Improving_Bias_Mitigation_Through_Bias_Experts.pdf`](presentation/Improving_Bias_Mitigation_Through_Bias_Experts.pdf)
- [`presentation/Improving_Bias_Mitigation_Through_Bias_Experts.pptx`](presentation/Improving_Bias_Mitigation_Through_Bias_Experts.pptx)

## Citation

If you use this presentation or refer to the original paper, cite the EMNLP 2023 paper:

```bibtex
@inproceedings{jeon2023improving,
  title={Improving Bias Mitigation through Bias Experts in Natural Language Understanding},
  author={Jeon, Eojin and Lee, Mingyu and Park, Juhyeong and Kim, Yeachan and Mok, Wing-Lam and Lee, Sangkeun},
  booktitle={Proceedings of EMNLP},
  year={2023}
}
```

## Author

Prepared as an academic presentation explaining bias mitigation, dataset bias, and out-of-distribution generalization in Natural Language Understanding.

## License

This repository is intended for academic and educational use.
