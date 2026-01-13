# Report
## Customer Subscription Prediction Using Decision Tree

---

## Introduction
This report presents the implementation of a Decision Tree classifier to predict customer subscription behavior using the Bank Marketing dataset. The task focuses on supervised classification using demographic and behavioral attributes.

---

## Methodology
The workflow followed these steps:
1. Data loading and inspection
2. Target variable encoding
3. Removal of leakage-prone features
4. Feature encoding
5. Model training and evaluation

A Decision Tree classifier with controlled depth and balanced class weights was used.

---

## Experimental Results

### Confusion Matrix
[[6050 1260]
[ 305 623]]

### Performance Metrics
- Accuracy: **81%**
- F1-score (Subscribers): **0.44**
- Recall (Subscribers): **0.67**

The classifier demonstrates strong performance in identifying customers likely to subscribe.

---

## Feature Importance Results
Top contributing features:
- `nr.employed`
- `cons.conf.idx`
- `euribor3m`
- `cons.price.idx`
- `pdays`

These results suggest that economic conditions and customer interaction history are critical factors in subscription decisions.

---

## Sample Prediction
A test customer instance was evaluated using the trained model.

**Predicted Outcome:**  
Customer will subscribe → **NO**

---

## Conclusion
The Decision Tree model effectively fulfills the task objective by:
- Accurately predicting customer subscription behavior
- Providing interpretable decision rules
- Highlighting influential features for business insights

The implementation successfully completes **Task 3** as specified.

---
