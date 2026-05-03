# Presentation Summary

## Title

**Improving Bias Mitigation Through Bias Experts in Natural Language Understanding**

## Short Summary

This presentation explains an EMNLP 2023 paper that proposes a stronger way to detect and reduce dataset bias in Natural Language Understanding models. The key argument is that standard multi-class auxiliary models can fail to identify bias properly because the softmax objective creates competition between classes. The paper replaces this with One-vs-Rest bias experts and uses Product-of-Experts training to reduce reliance on biased patterns.

## Slide-Level Flow

1. **Title Slide**  
   Introduces the paper, authors, venue, and main theme.

2. **Problem Description**  
   Explains dataset bias in NLP and how models exploit spurious correlations.

3. **Why Multi-Class Objective Is Sub-Optimal**  
   Shows that multi-class objectives learn bias attributes more slowly and target attributes faster.

4. **Dataset Description**  
   Covers MNLI, FEVER, QQP, and their OOD challenge datasets.

5. **Method Overview**  
   Introduces the three-step pipeline: OVR, bias experts, and Product-of-Experts.

6. **One-vs-Rest**  
   Explains how each class is converted into a binary classification task.

7. **Bias Amplification Mechanism**  
   Explains how the amplification hyperparameter controls stronger bias learning.

8. **Product-of-Experts**  
   Shows how confident bias experts reduce the main model’s reliance on biased examples.

9. **Main Results**  
   Summarizes OOD improvements on HANS, FEVER Symmetric, and PAWS.

10. **Ablation Study**  
   Shows that removing OVR or amplification reduces performance.

11. **Confidence Analysis**  
   Demonstrates stronger confidence on biased examples and lower confidence on bias-conflicting examples.

12. **Generalization to Vision**  
   Shows that the method also works on BAR and NICO vision datasets.

13. **Critical Evaluation**  
   Summarizes strengths, limitations, and ethical considerations.

14. **Thank You**  
   Closing slide.

## Keywords

- Bias mitigation
- Dataset bias
- Natural Language Understanding
- Debiasing
- Out-of-distribution generalization
- One-vs-Rest training
- Product-of-Experts
- Softmax limitation
- Bias experts
