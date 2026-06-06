# Twitter NER Project - Final Report
**Generated on:** 2026-06-06

## 1. Project Overview
End-to-end Named Entity Recognition system for noisy Twitter data (WNUT-2016) using BiLSTM + GloVe embeddings with advanced imbalance handling.

## 2. Dataset Statistics
- Training Sentences: **2394**
- Test Sentences: **3850**
- Total Tokens: **108,375**
- Vocabulary Size: **25,384**
- Unique Tags: **22**
- Padding Length: **29**

## 3. Model Performance

### Token-Level Results
| Experiment              | Accuracy | Macro F1 | Notes |
|-------------------------|----------|----------|-------|
| Baseline (GloVe BiLSTM) | 0.90     | 0.07    | Strong `O` bias |
| + Data Augmentation     | 0.88     | 0.12    | Improved recall |
| + BERT                  | _        | 0.22    | Strong transformer baseline |
| + Tuned BERT-base       | —        | 0.4418  | Best overall model after Optuna tuning |

### Entity-Level (seqeval) Results
- Baseline: **0.05**
- After Augmentation: **0.11** (+120% relative improvement)

## 4. Key Techniques Applied
- Pre-trained **GloVe 100d** embeddings
- Synonym-based **Data Augmentation** for rare entities
- **Class Weighting** (inverse frequency)
- **Focal Loss** implementation

