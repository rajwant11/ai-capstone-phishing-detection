# Week 7: RAG Security Knowledge Assistant — Evaluation Report

## 1. Setup Summary

- **LLM:** llama-3.1-8b-instant via Groq  
- **Embeddings:** sentence-transformers/all-MiniLM-L6-v2 via HuggingFace  
- **Vector Store:** In-Memory Vector Store  
- **Documents loaded:**  
  - MITRE Credential Access techniques  
  - MITRE Initial Access (Phishing)  
  - MITRE Lateral Movement  
  - Additional MITRE ATT&CK technique descriptions  

---

## 2. Test Results

| # | Question | Used Documents? | Quality | Notes |
|---|----------|----------------|---------|-------|
| 1 | What are common techniques for credential access according to MITRE? | Yes | Good | Correctly mentioned credential dumping and brute force |
| 2 | How does phishing relate to initial access in the ATT&CK framework? | Yes | Good | Explained phishing as an initial access technique |
| 3 | What is lateral movement and what techniques do attackers use? | Yes | Good | Included SMB, RDP, and attacker behavior |
| 4 | What does the NIST framework recommend for the Detect function? | No | Wrong | NIST was not in uploaded documents |
| 5 | What is the difference between spearphishing attachment and spearphishing link? | Yes | Good | Clearly explained both methods |

---

## 3. Edge Case Observations

- **Unrelated question:**  
  When asked “What is the weather like today?”, the chatbot responded with “I’m not sure.” This shows correct behavior and no hallucination.

- **Topic not in documents:**  
  When asked about CVEs from 2026 and zero trust architecture, the chatbot responded with “I’m not sure.” This shows the system only uses available documents.

---

## 4. Settings Experiments (if completed)

- **Temperature change:**  
  Lower temperature gave more accurate answers.

- **Chunk size change:**  
  Smaller chunks improved precision.

- **Top K change:**  
  Higher Top K added more context but sometimes less relevant.

---

## 5. Reflection

- **What surprised you about how RAG works?**  
  The chatbot only answers from documents and avoids hallucination.

- **How could you improve this chatbot for real-world use?**  
  Add more documents and use a persistent database.

- **How might you use RAG in your capstone project?**  
  Build an AI intrusion detection assistant using cybersecurity data.

---

## Chatbot Link

https://cloud.flowiseai.com/chatbot/be7a5d73-63c4-4217-83c7-ab05fee88305
