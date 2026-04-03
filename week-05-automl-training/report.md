# Week 5 Report: AutoML Training & Fine-Tuned Model Evaluation

**Name:** Rajwant Kaur
**Date:** April 2, 2026
**Capstone Project:** AI-Powered Intrusion Detection System (IDS)
**My Component:** Automated Threat Detection / Spam Classification

---

## Part A: Teachable Machine Training

### Training Setup

* **Task:** Phishing vs Legitimate vs Suspicious email screenshot classification
* **Training images per class:** 16–17
* **Test images per class:** 5
* **Total training time:** ~30 seconds

---

### Test Results

The model was tested using 15 images across three classes.

| File Name     | Actual Class | Predicted Class | Confidence |
| ------------- | ------------ | --------------- | ---------- |
| test_phish_01 | Phishing     | Phishing        | 86%        |
| test_phish_02 | Phishing     | Phishing        | 96%        |
| test_phish_03 | Phishing     | Legitimate      | 98%        |
| test_phish_04 | Phishing     | Phishing        | 97%        |
| test_phish_05 | Phishing     | Phishing        | 98%        |
| test_legit_01 | Legitimate   | Legitimate      | 100%       |
| test_legit_02 | Legitimate   | Legitimate      | 100%       |
| test_legit_03 | Legitimate   | Legitimate      | 99%        |
| test_legit_04 | Legitimate   | Legitimate      | 100%       |
| test_legit_05 | Legitimate   | Legitimate      | 100%       |
| test_susp_01  | Suspicious   | Phishing        | 52%        |
| test_susp_02  | Suspicious   | Suspicious      | 100%       |
| test_susp_03  | Suspicious   | Suspicious      | 78%        |
| test_susp_04  | Suspicious   | Suspicious      | 78%        |
| test_susp_05  | Suspicious   | Phishing        | 100%       |

---

### Confusion Matrix (3-Class Summary)

| Actual \ Predicted | Phishing | Legitimate | Suspicious |
| ------------------ | -------- | ---------- | ---------- |
| Phishing           | 4        | 1          | 0          |
| Legitimate         | 0        | 5          | 0          |
| Suspicious         | 2        | 0          | 3          |

---

### Calculated Metrics

* **Accuracy:** 80%

---

### Interpretation

The model performs very well on legitimate emails, correctly classifying all test samples. It also performs strongly on phishing detection, with only one misclassification. However, the suspicious class shows more errors, with some samples incorrectly classified as phishing. This indicates that the model has difficulty distinguishing ambiguous or edge-case inputs. Increasing the number and diversity of training samples, especially for the suspicious category, would improve overall model performance.

---

## Part B: Generic vs Fine-Tuned Model Comparison

### Models Tested

1. **Generic:** distilbert-base-uncased-finetuned-sst-2-english
2. **Fine-Tuned A:** mrm8488/bert-tiny-finetuned-sms-spam-detection
3. **Fine-Tuned B:** dima806/email-spam-detection-roberta

---

### Results

| Input    | Generic Label (Score) | Fine-Tuned A Label (Score) | Fine-Tuned B Label (Score) | Best Model   |
| -------- | --------------------- | -------------------------- | -------------------------- | ------------ |
| Record 1 | NEGATIVE (0.996)      | LABEL_0 (0.704)            | No spam (0.997)            | Fine-Tuned B |
| Record 2 | NEGATIVE (0.998)      | LABEL_1 (0.537)            | No spam (0.999)            | Fine-Tuned B |
| Record 3 | NEGATIVE (0.995)      | LABEL_0 (0.741)            | Spam (0.999)               | Fine-Tuned B |
| Record 4 | NEGATIVE (0.999)      | LABEL_1 (0.571)            | No spam (0.678)            | Fine-Tuned B |
| Record 5 | NEGATIVE (0.988)      | LABEL_0 (0.838)            | No spam (0.998)            | Fine-Tuned B |

---

### Analysis

The generic model produces high-confidence predictions but is not useful for cybersecurity tasks because it only detects sentiment. It cannot identify spam or malicious content.

The fine-tuned models are trained specifically for spam detection, making them much more effective. They provide meaningful labels such as "Spam" or "No spam," which are directly useful for intrusion detection systems.

---

### Recommended Model for My Capstone Component

* **Primary model:** Fine-Tuned B
* **Reason:** Provides accurate and interpretable classifications with high confidence
* **Confidence threshold:** 0.80
* **Priority metric:** Recall

---

## Limitations & Next Steps

The current model performs well overall but struggles with the suspicious category due to limited training data. Future improvements include increasing dataset size, especially for edge cases, and fine-tuning models using cybersecurity-specific datasets to improve real-world performance.
