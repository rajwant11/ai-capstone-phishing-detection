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

| #  | Actual Class | Predicted Class | Confidence | Correct? |
| -- | ------------ | --------------- | ---------- | -------- |
| 1  | Phishing     | Phishing        | 0.95       | Yes      |
| 2  | Phishing     | Phishing        | 0.92       | Yes      |
| 3  | Phishing     | Legitimate      | 0.60       | No       |
| 4  | Phishing     | Phishing        | 0.88       | Yes      |
| 5  | Phishing     | Phishing        | 0.91       | Yes      |
| 6  | Legitimate   | Legitimate      | 0.96       | Yes      |
| 7  | Legitimate   | Legitimate      | 0.93       | Yes      |
| 8  | Legitimate   | Phishing        | 0.55       | No       |
| 9  | Legitimate   | Legitimate      | 0.90       | Yes      |
| 10 | Legitimate   | Legitimate      | 0.94       | Yes      |

---

### Confusion Matrix (3-Class Summary)

| Actual \ Predicted | Phishing | Legitimate | Suspicious |
| ------------------ | -------- | ---------- | ---------- |
| **Phishing**       | 4        | 1          | 0          |
| **Legitimate**     | 1        | 4          | 0          |
| **Suspicious**     | 0        | 0          | 0          |

---

### Calculated Metrics

* **Accuracy:** 80%

(Precision, Recall, and F1 Score are not calculated per class due to limited test samples for all three categories.)

---

### Interpretation

The model performs well for phishing and legitimate classifications but does not yet effectively evaluate the suspicious class due to limited testing data. Most errors occur between phishing and legitimate categories. The incorrect prediction where a phishing email was classified as legitimate with high confidence highlights a key limitation. Increasing training and test samples, especially for the suspicious category, would improve model reliability and performance.

---

## Part B: Generic vs Fine-Tuned Model Comparison

### Models Tested

1. **Generic:** distilbert-base-uncased-finetuned-sst-2-english (sentiment)
2. **Fine-Tuned A:** mrm8488/bert-tiny-finetuned-sms-spam-detection — spam detection classifier
3. **Fine-Tuned B:** dima806/email-spam-detection-roberta — spam vs non-spam classification

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

**Generic model strengths:**
The generic model consistently produces high-confidence predictions and performs well for general sentiment classification.

**Generic model weaknesses:**
It cannot detect spam or security threats since it only identifies sentiment (positive or negative), which is not relevant for intrusion detection tasks.

**Fine-tuned model advantage:**
Fine-tuned models are specifically trained for spam detection tasks, allowing them to produce meaningful and interpretable outputs such as “Spam” or “No spam.” They are more suitable for cybersecurity applications.

**Biggest surprise:**
Despite very high confidence scores, the generic model failed to provide useful classifications for spam detection, demonstrating that high confidence does not always mean task relevance.

---

### Recommended Model for My Capstone Component

**Component:** Automated Threat Detection / Spam Classification

**Primary model:** Fine-Tuned B — because it provides accurate, interpretable labels and high-confidence predictions for spam detection

**Confidence threshold:** 0.80 — ensures only reliable predictions are considered

**Priority metric:** Recall — because missing a malicious or spam message is more dangerous than incorrectly flagging a safe message

---

## Limitations & Next Steps

The current models rely on limited datasets and pre-trained configurations. The suspicious class was not sufficiently evaluated due to limited test data. With more time, I would fine-tune a custom model using cybersecurity-specific datasets and expand testing across all classes. I would also explore additional models and increase dataset diversity to improve robustness and real-world performance.
