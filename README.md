# Bank Marketing – Decision Tree Classifier

## 📌 Task Objective
The goal of this task is to build a **Decision Tree classifier** to predict whether a customer will subscribe to a product or service based on their **demographic and behavioral data**, using the **Bank Marketing dataset** from the UCI Machine Learning Repository.

---

## 📂 Dataset Description
- **Dataset**: Bank Marketing (bank-additional-full.csv)
- **Total Records**: 41,188
- **Total Features**: 20 input features + 1 target
- **Target Variable**:
  - `y = 1` → Customer subscribes
  - `y = 0` → Customer does not subscribe

### Target Class Distribution
The dataset is **highly imbalanced**:
- No subscription (0): **88.7%**
- Subscription (1): **11.3%**

This imbalance was handled using class weighting in the model.

---

## 🧹 Data Preprocessing
The following preprocessing steps were performed:

1. **Target Encoding**
   - Converted `y` from `yes/no` to `1/0`.

2. **Data Leakage Removal**
   - The feature `duration` was removed because it is only known *after* a marketing call and would unrealistically inflate model performance.

3. **Feature Encoding**
   - Categorical variables were converted using **One-Hot Encoding**.
   - Final encoded feature space size: **196 features**.

4. **Train-Test Split**
   - 80% training data
   - 20% testing data
   - Stratified split to preserve class distribution

---

## 🌳 Model Used
**Decision Tree Classifier**

**Model configuration:**
- `max_depth = 6`
- `class_weight = "balanced"`
- `random_state = 42`

Class weighting was applied to address class imbalance and improve recall for the minority class.

---

## 📊 Model Evaluation

### Confusion Matrix
[[6050 1260]
[ 305 623]]


- True Negatives: 6050
- False Positives: 1260
- False Negatives: 305
- True Positives: 623

---

### Classification Report
| Class | Precision | Recall | F1-Score |
|-----|----------|--------|----------|
| 0 (No) | 0.95 | 0.83 | 0.89 |
| 1 (Yes) | 0.33 | 0.67 | 0.44 |

- **Accuracy**: 81%
- The model achieves **high recall (67%)** for customers who subscribe, which is important in marketing use cases where missing potential subscribers is costly.

---

## 🔍 Feature Importance Analysis
The Decision Tree model provides interpretable feature importance scores.

### Top 10 Important Features
1. `nr.employed`
2. `cons.conf.idx`
3. `euribor3m`
4. `cons.price.idx`
5. `pdays`
6. `month_oct`
7. `campaign`
8. `default_unknown`
9. `job_retired`
10. `contact_telephone`

These features indicate that **macroeconomic indicators** and **previous campaign behavior** strongly influence customer subscription decisions.

A bar chart visualization of the top 10 features was generated for better interpretability.

---

## 🔮 Sample Prediction
A sample customer from the dataset was tested:

**Prediction:**  
> Customer will subscribe: **NO**

This demonstrates how the trained Decision Tree model can be used for real-time customer predictions.

---

## ✅ Conclusion
- A **Decision Tree classifier** was successfully built and evaluated.
- Proper preprocessing and data leakage prevention were applied.
- The model provides **interpretable results** and meaningful feature importance insights.
- The task requirements were fully satisfied without unnecessary complexity.

**Task Status: COMPLETED ✔**

---

## 📌 Tools & Libraries Used
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
