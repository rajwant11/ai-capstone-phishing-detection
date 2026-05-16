# Lab 9 – Confidence-Based Routing

## Routing Scenario

The AI Core workflow was tested using the Alert Classifier output. The classifier returned a confidence score of 0.9.

## Routing Logic

An IF node was added after the Alert Classifier node to check the AI confidence result.

Condition used:

```text
{{ $json.text }} contains "confidence": 0.9
