# Paper Notes

## Paper

**Improving Bias Mitigation through Bias Experts in Natural Language Understanding**  
EMNLP 2023

## Core Problem

Natural Language Understanding models often perform well on in-distribution data but fail on out-of-distribution examples because they learn spurious correlations.

Examples discussed in the presentation:

- Negation may be incorrectly associated with contradiction.
- Lexical overlap may be incorrectly associated with entailment.

## Limitation of Existing Debiasing

Existing debiasing methods often use a multi-class auxiliary model to identify biased examples. However, the paper argues that multi-class objectives can be sub-optimal because softmax forces competition between classes.

Bias detection requires the auxiliary model to strongly learn biased patterns, but a standard multi-class objective may prevent this.

## Proposed Solution

The paper proposes using separate bias experts trained through a One-vs-Rest setup.

Each expert focuses on detecting bias for one specific class.

## Pipeline

1. Train an auxiliary model.
2. Construct binary datasets for each class.
3. Train class-specific bias experts.
4. Freeze the bias experts.
5. Train the main model using Product-of-Experts.

## Important Components

### One-vs-Rest Training

Instead of one multi-class auxiliary model, the method creates one binary expert per class.

### Bias Amplification

A hyperparameter controls how strongly the bias expert learns biased examples.

### Product-of-Experts

The main model is trained together with the frozen bias expert outputs. If the bias expert is highly confident, the main model reduces reliance on that biased signal.

## Datasets Mentioned

- MNLI → HANS
- FEVER → FEVER Symmetric
- QQP → PAWS
- BAR and NICO for vision generalization

## Key Takeaway

The main contribution of the paper is that the problem is not only dataset bias itself, but also the way bias-detecting auxiliary models are trained.
