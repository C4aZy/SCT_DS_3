# Analysis
## Bank Marketing Decision Tree Classifier

---

## Objective
To analyze customer demographic and behavioral data and build a Decision Tree model capable of predicting whether a customer will subscribe to a bank product or service.

---

## Dataset Description
- Source: UCI Machine Learning Repository (Bank Marketing Dataset)
- Records: 41,188
- Features: 20 input features + 1 target variable
- Target Variable: `y`
  - 1 → Subscription (Yes)
  - 0 → No Subscription

---

## Data Characteristics
- The dataset is highly imbalanced.
  - Non-subscribers: ~88.7%
  - Subscribers: ~11.3%
- Both categorical and numerical attributes are present.
- Some features, such as `duration`, can cause data leakage if not handled properly.

---

## Data Preparation
- Target variable converted from categorical to binary format.
- `duration` column removed to avoid post-event bias.
- Categorical variables encoded using One-Hot Encoding.
- Final feature space expanded to 196 encoded features.
- Stratified train-test split (80/20) used to preserve class balance.

---

## Model Selection
A **Decision Tree Classifier** was selected due to:
- Interpretability
- Ability to handle non-linear relationships
- Support for feature importance extraction

Model constraints:
- Maximum depth limited to prevent overfitting
- Class weights balanced to address class imbalance

---

## Evaluation Summary
- Accuracy: 81%
- Recall for subscribers: 67%
- Precision for subscribers: 33%

The model favors recall for the minority class, which is suitable for marketing campaigns where identifying potential subscribers is more important than avoiding false positives.

---

## Feature Importance Insights
The most influential features include:
- Employment indicators (`nr.employed`)
- Economic indicators (`cons.conf.idx`, `euribor3m`)
- Campaign history (`pdays`, `campaign`)

This indicates that both macroeconomic conditions and prior interactions strongly influence customer decisions.

---

## Key Observations
- Decision Trees provide clear decision logic.
- Class imbalance significantly affects prediction outcomes.
- Feature importance offers actionable business insights.

---
