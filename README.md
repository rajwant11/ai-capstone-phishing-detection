# Week 4: Model Comparison

Tested 4 AI models on 5 cybersecurity text samples to evaluate their suitability for the email threat classification and alert severity detection component of our AI-Powered Intrusion Detection System (IDS).

## Models Tested

- HF Sentiment (distilbert-sst-2)
- HF Zero-Shot (bart-large-mnli)
- HF NER (bert-large-NER)
- Groq Llama 3 8B

## Finding

Recommended Groq Llama 3 8B for the email threat classification and alert severity detection component because it gave the most accurate severity labels and clear reasoning. See `report.md` for full analysis.