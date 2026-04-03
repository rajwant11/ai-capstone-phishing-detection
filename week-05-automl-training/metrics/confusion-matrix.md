# Model Evaluation: Confusion Matrix

### 3-Class Summary
| Actual \ Predicted | Phishing | Legitimate | Suspicious |
|     :---           |   :---:  |   :---:    |   :---:    |
| **Phishing**       |     4    |     1      |     0      |
| **Legitimate**     |     0    |     5      |     0      |
| **Suspicious**     |     2    |     0      |     3      |

### Calculated Metrics

Overall Accuracy: 80%

### Key Observations

- Most errors occur between Phishing and Legitimate classes.
- The Suspicious class has more misclassifications and needs more training data.
- Additional data will improve model performance for edge-case detection.