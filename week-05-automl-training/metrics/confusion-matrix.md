# Model Evaluation: Confusion Matrix

### 3-Class Summary
| Actual \ Predicted | Phishing | Legitimate | Suspicious |
|     :---           |   :---:  |   :---:    |   :---:    |
| **Phishing**       |     4    |     1      |     0      |
| **Legitimate**     |     1    |     4      |     0      |
| **Suspicious**     |     0    |     0      |     0      |

### Calculated Metrics
- **Overall Accuracy:** 80%

### Key Observations
* **Primary Errors:** Most misclassifications occur between the **Phishing** and **Legitimate** categories.
* **Data Gap:** The **Suspicious** class was not effectively evaluated due to limited test samples.
* **Future Improvement:** More training and test data for the suspicious category is needed to improve model performance and help distinguish edge-case scenarios.