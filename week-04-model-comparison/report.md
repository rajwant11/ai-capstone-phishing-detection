Model Comparison Report — Week 4

Name: Rajwant Kaur
Date: March 19, 2026
Capstone Project: AI-Powered Intrusion Detection System (IDS)
My Component: Email threat classification and alert severity detection

Test Setup

Input dataset: 5 cybersecurity text samples covering:

2 clearly concerning/high-severity records

1 ambiguous/edge case record

2 routine/benign records

Models tested:

distilbert-base-uncased-finetuned-sst-2-english (sentiment)

facebook/bart-large-mnli (zero-shot classification)

dslim/bert-large-NER (named entity recognition)

Groq Llama 3 8B (LLM classification)

Evaluation criteria: label accuracy, confidence score, speed, ease of integration in n8n

Results Summary
Record	  Sentiment	          Zero-Shot	    NER Entitie         Groq
1	 NEGATIVE (0.9983)	possible anomaly	[]	     HIGH
2	 NEGATIVE (0.9928)	possible anomaly	[]	     INFORMATIONAL
3	 NEGATIVE (0.9978)	possible anomaly	[]	     CRITICAL
4	 NEGATIVE (0.9987)	possible anomaly	[]	     HIGH
5	 NEGATIVE (0.9253)	routine activity	[]	     INFORMATIONAL
Analysis

Where models agreed: The models agreed that the newsletter is normal and that phishing and suspicious emails are concerning.

Where models disagreed: The models differed in how detailed their classifications were. The sentiment model marked everything as negative, so it could not distinguish between threats and routine messages. The zero-shot model was more useful but still too general, since it mostly labeled records as possible anomaly. The Groq model provided clearer severity levels and explanations.

Most accurate model overall: Groq Llama 3 8B gave the most sensible results because it correctly identified severity levels and explained its reasoning.

Fastest/most practical: The Hugging Face models are faster and easier to use, but they provide more basic results.

Recommended Models for My Capstone Component

Component: Email threat classification and alert severity detection

Primary model: Groq Llama 3 8B — It provides clear severity classification with reasoning, which is useful for security decisions.

Secondary model (if applicable): facebook/bart-large-mnli — It can be used for quick initial filtering of suspicious activity.

Rejected models and why:

distilbert-base-uncased-finetuned-sst-2-english: It labels everything as negative and cannot distinguish between normal and malicious activity.

dslim/bert-large-NER: It did not return useful entities for this dataset.

Failure Cases and Limitations

One failure case was that the zero-shot model labeled most records as possible anomaly even when some were clearly high risk. This shows that the model is not precise enough for security classification and may require better labels or tuning.

Next Steps

If I had more time, I would test more records with different types of alerts and try different labels for the zero-shot model or use a model trained specifically for cybersecurity.