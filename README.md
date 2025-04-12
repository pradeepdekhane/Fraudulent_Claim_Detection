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

📊 Evaluation and Conclusion
🧪 Data Preparation and Preprocessing
The dataset was imbalanced and addressed using Random Over Sampler to ensure equal representation of fraud and non-fraud cases.

Features were scaled using StandardScaler (chosen over MinMaxScaler) due to compatibility with Logistic Regression.

🔍 Feature Selection Insights (via RFECV)
The following features were identified as the most predictive:

insured_hobbies_chess

insured_hobbies_cross-fit

incident_severity_Minor Damage

incident_severity_Total Loss

incident_severity_Trivial Damage

These top features exhibited VIF < 5, confirming:

No significant multicollinearity.

Stable coefficients and trustworthy feature importance.

Better generalization by avoiding overfitting from redundant features.

📈 Model Evaluation Summary
Logistic Regression (Threshold = 0.2)
Metric	Train Set	Test Set
Recall	0.9011	0.8649
Specificity	0.8498	0.8319
Precision	0.8571	0.6275
F1 Score	0.8786	0.7273
Random Forest
Metric	Train Set	Test Set
Recall	0.8574	0.7568
Specificity	0.8536	0.8407
Precision	0.8542	0.6087
F1 Score	0.8558	0.6747
📌 Analysis & Interpretation
Recall (Sensitivity):
Logistic Regression performed better on the test set with a recall of 0.8649, compared to Random Forest's 0.7568, making it more effective in identifying fraudulent claims.

Precision:
Logistic Regression also showed slightly better precision (0.6275) than Random Forest (0.6087), indicating higher accuracy in positive predictions.

Specificity:
Random Forest slightly outperformed Logistic Regression in identifying non-fraudulent claims (0.8407 vs 0.8319), but this is less critical than recall for fraud detection tasks.

F1 Score:
Logistic Regression achieved a higher F1 Score (0.7273), balancing precision and recall more effectively on unseen data.

✅ Conclusion
Logistic Regression was found to be the best model for this fraud detection project due to:

High Recall: Captures more fraudulent transactions.

Better Generalization: Lower risk of overfitting.

Balanced Performance: Optimal F1 score and interpretability.

Recommendation:
Deploy Logistic Regression with a decision threshold of 0.2 for proactive fraud flagging, enabling early detection and reducing financial losses.
