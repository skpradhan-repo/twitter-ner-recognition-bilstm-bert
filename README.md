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

### Entity-Level (seqeval) Results
- Baseline: **0.05**
- After Augmentation: **0.11** (+120% relative improvement)

## 4. Key Techniques Applied
- Pre-trained **GloVe 100d** embeddings
- Synonym-based **Data Augmentation** for rare entities
- **Class Weighting** (inverse frequency)
- **Focal Loss** implementation

## 5. Next Steps
- Integrate DistilBERT / BERT
- Add CRF layer
- Deploy as web demo

---
*Report auto-generated from notebook outputs.*
