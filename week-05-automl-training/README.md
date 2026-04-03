# Week 5: AutoML & No-Code Model Training

This project involved training a custom 3-class image classifier (Phishing, Legitimate, Suspicious) and comparing generic vs. fine-tuned Hugging Face models for the **Automated Threat Detection** component of our **AI-Powered Intrusion Detection System (IDS)**.

## Custom Model Training
- **Task:** 3-class classification of email screenshots.
- **Accuracy:** 80% on 10 test images.
- **Key Finding:** The model struggled with the 'Suspicious' class due to low data volume, highlighting the need for balanced datasets.

## Fine-Tuned Model Comparison
Tested 3 models on 5 security-themed text records:
1. **Generic:** distilbert-sst-2 (Sentiment)
2. **Fine-Tuned A:** bert-tiny-sms-spam (Spam detection)
3. **Fine-Tuned B:** roberta-email-spam (Spam vs Non-spam)

## Recommendation
I recommend **Fine-Tuned B (RoBERTa)** for my capstone because it provided the most accurate "Spam" vs "No spam" labels with high confidence (>99% on most records).

*Full details in `report.md`.*
