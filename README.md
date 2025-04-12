# Fraudulent_Claim_Detection

Global Insure, a leading insurance company, processes thousands of claims annually. However, a significant percentage of these claims turn out to be fraudulent, resulting in considerable financial losses. The company’s current process for identifying fraudulent claims involves manual inspections, which is time-consuming and inefficient. Fraudulent claims are often detected too late in the process, after the company has already paid out significant amounts. Global Insure wants to improve its fraud detection process using data-driven insights to classify claims as fraudulent or legitimate early in the approval process. This would minimise financial losses and optimise the overall claims handling process.

Business Objective
Global Insure wants to build a model to classify insurance claims as either fraudulent or legitimate based on historical claim details and customer profiles. By using features like claim amounts, customer profiles and claim types, the company aims to predict which claims are likely to be fraudulent before they are approved.

Based on this assignment, you have to answer the following questions:

● How can we analyse historical claim data to detect patterns that indicate fraudulent claims?

● Which features are most predictive of fraudulent behaviour?

● Can we predict the likelihood of fraud for an incoming claim, based on past data?

● What insights can be drawn from the model that can help in improving the fraud detection process?


The objective is to build a model to classify insurance claims as either fraudulent or legitimate based on historical claim details and customer profiles. By using features such as claim amounts, customer profiles, claim types and approval times, the company aims to predict the claims that are likely to be fraudulent before they are approved.


---

# 🚨 Insurance Fraud Detection – Evaluation & Conclusion

## 📋 Overview

This section summarizes the evaluation metrics and final conclusion drawn from building predictive models for detecting insurance fraud at **Global Insure**.

---

## 🧹 Data Preparation

- 🧾 **Imbalanced Data Handling**: Resolved using **Random Over Sampler** to ensure balanced class representation.
- ⚖️ **Feature Scaling**: Applied **StandardScaler** (chosen over MinMaxScaler) to standardize data for better model performance, especially for Logistic Regression.

---

## 🧠 Feature Selection Insights

Using **Recursive Feature Elimination with Cross-Validation (RFECV)**, key predictors were identified:

```
✅ insured_hobbies_chess  
✅ insured_hobbies_cross-fit  
✅ incident_severity_Minor Damage  
✅ incident_severity_Total Loss  
✅ incident_severity_Trivial Damage
```

📌 All selected features had **VIF < 5**, indicating:
- No significant multicollinearity
- Reliable coefficients
- Minimal risk of overfitting

---

## 📈 Model Evaluation Summary

### 🔹 Logistic Regression (Threshold = 0.2)

| Metric       | Train Set | Test Set |
|--------------|-----------|----------|
| 🎯 Recall     | 0.9011    | 0.8649   |
| ✅ Specificity| 0.8498    | 0.8319   |
| 🎯 Precision  | 0.8571    | 0.6275   |
| ⚖️ F1 Score   | 0.8786    | 0.7273   |

---

### 🔹 Random Forest

| Metric       | Train Set | Test Set |
|--------------|-----------|----------|
| 🎯 Recall     | 0.8574    | 0.7568   |
| ✅ Specificity| 0.8536    | 0.8407   |
| 🎯 Precision  | 0.8542    | 0.6087   |
| ⚖️ F1 Score   | 0.8558    | 0.6747   |

---

## 📊 Interpretation

- **Recall (Sensitivity)**:  
  Logistic Regression identifies a higher percentage of fraudulent claims (**0.8649**) compared to Random Forest (**0.7568**).

- **Precision**:  
  Logistic Regression is also more accurate when predicting fraud (**0.6275** vs **0.6087**).

- **Specificity**:  
  Random Forest slightly edges out in identifying legitimate claims, but in fraud detection, **recall is more critical**.

- **F1 Score**:  
  Logistic Regression has the edge with a higher F1 score on the test set (**0.7273** vs **0.6747**), showing a better balance between precision and recall.

---

## ✅ Final Conclusion

🚀 **Logistic Regression is the best-performing model** for this fraud detection task due to:

- High **Recall** – effectively identifies fraud
- Better **F1 Score** – balanced performance
- Robust **feature reliability** – no multicollinearity
- Simple and interpretable for business deployment

🛠️ **Recommended Deployment Strategy**:
- Use **Logistic Regression** with a **threshold of 0.2** to flag high-risk claims.
- Continuously monitor model performance and update features with new data patterns.

---

Let me know if you want me to include badges, GitHub repo structure, or links to notebooks and code sections too!
