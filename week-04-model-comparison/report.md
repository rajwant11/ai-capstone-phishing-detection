# Model Comparison Report — Week 4

**Name:** Rajwant Kaur  
**Date:** March 19, 2026  
**Capstone Project:** AI-Powered Intrusion Detection System (IDS)  
**Component:** Email threat classification and alert severity detection  

---

## Test Setup

**Input dataset:** 5 cybersecurity text samples:
- 2 high-severity (clearly concerning)
- 1 ambiguous / edge case
- 2 routine / benign

---

## Models Tested

- `distilbert-base-uncased-finetuned-sst-2-english` (Sentiment)
- `facebook/bart-large-mnli` (Zero-shot classification)
- `dslim/bert-large-NER` (Named Entity Recognition)
- **Groq LLaMA 3 8B** (LLM classification)

---

## Evaluation Criteria

- Label accuracy  
- Confidence score  
- Speed  
- Ease of integration in n8n  

---

## Results Summary

| Record |   Sentiment      | Zero-Shot Label   | NER |   Groq Classification |
|---|-----------------------|-------------------|-----|-----------------------|
| 1 |     NEGATIVE (0.9983) | Possible anomaly   | — |         HIGH           |
| 2 |     NEGATIVE (0.9928) | Possible anomaly   | — |         INFORMATIONAL  |
| 3 |     NEGATIVE (0.9978) | Possible anomaly   | — |         CRITICAL       |
| 4 |     NEGATIVE (0.9987) | Possible anomaly   | — |         HIGH           |
| 5 |     NEGATIVE (0.9253) | Routine activity   | — |         INFORMATIONAL  |

---

## Analysis

### Where models agreed
All models correctly identified:
- Newsletter → normal  
- Phishing / suspicious emails → concerning  

---

### Where models disagreed
- **Sentiment model:**  
  Marked everything as negative → cannot distinguish threats vs normal  

- **Zero-shot model:**  
  Better, but too general → labeled most records as "possible anomaly"  

- **Groq model:**  
  Provided **clear severity levels + reasoning** → most useful  

---

## Best Model

The most accurate model overall was **Groq LLaMA 3 8B**, as it correctly identified severity levels and provided clear explanations.

The fastest and most practical models were the Hugging Face models, which were easier to integrate and faster to run, but produced more basic results.

---

## Recommended Models (Capstone)

**Component:** Email threat classification & alert severity  

- **Primary model:** Groq LLaMA 3 8B — Best for security decision-making  
- **Secondary model:** facebook/bart-large-mnli — Useful for quick filtering  

---

## Rejected Models

- **distilbert (sentiment):**  
  Labels everything as negative → not useful  

- **bert-large-NER:**  
  Did not return useful entities  

---

## Failure Case

The zero-shot model labeled most records as "possible anomaly," even when some were clearly high risk. This indicates that the model is not precise enough for security classification tasks.

---

## Next Steps

If more time was available, I would test more records, experiment with better labels for the zero-shot model, and explore models specifically trained for cybersecurity tasks.
