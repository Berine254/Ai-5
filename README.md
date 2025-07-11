# Ai-5
Part 1:

1. Problem Definition 

Hypothetical AI Problem:
Predicting student mental health crisis risk using academic performance, behavior, and social media data.

Objectives:

1. Identify students at high risk for mental health issues early.


2. Provide timely alerts to counselors and parents.


3. Reduce mental health-related dropouts by 25% annually.



Stakeholders:

1. University administration


2. On-campus mental health counselors



Key Performance Indicator (KPI):
Percentage of high-risk students accurately identified (True Positive Rate)




2. Data Collection & Preprocessing (8 points)

Two Data Sources:

1. Academic records (grades, attendance, disciplinary data)


2. Social media activity (public posts, sentiment analysis)



One Potential Bias:
Students who are less active online may be underrepresented in social media data, leading to skewed risk predictions.

Three Preprocessing Steps:

1. Handle missing values using imputation for incomplete academic records.


2. Normalize numerical features like GPA and attendance rates.


3. Use NLP techniques (tokenization, sentiment scoring) to preprocess social media text.




3. Model Development 

Chosen Model:
Random Forest — good balance between performance and interpretability, handles missing values, and reduces overfitting through ensembling.

Data Split Strategy:
70% training, 15% validation, 15% test split using stratified sampling to preserve class distribution.

Two Hyperparameters to Tune:

1. max_depth — controls the depth of each tree and prevents overfitting.


2. n_estimators — number of trees in the forest, affects performance and accuracy.




4. Evaluation & Deployment

Two Evaluation Metrics:

1. Precision — Important to minimize false positives so resources aren’t misused.


2. Recall — Vital to ensure most high-risk students are caught.



What is Concept Drift?
When the statistical properties of input data change over time, leading to model degradation.

Monitoring Method: Use model retraining triggers when prediction accuracy falls below a threshold or use drift detection tools like DDM or ADWIN.


One Technical Challenge:
Scalability — Handling real-time predictions for thousands of students across departments.



Part 2: 

Scenario: A hospital wants an AI system to predict patient readmission within 30 days of discharge.

1. Problem Scope (5 points)

Problem Statement:
Predict which patients are likely to be readmitted within 30 days post-discharge to allocate preventive care and reduce hospital burden.

Objectives:

1. Reduce readmission rates by 20%.


2. Allocate resources for follow-up care effectively.


3. Improve patient outcomes through early intervention.



Stakeholders:

Hospital administrators

Healthcare providers (doctors, nurses)





2. Data Strategy 

Data Sources:

1. Electronic Health Records (EHRs)


2. Patient demographics and discharge summaries



Two Ethical Concerns:

1. Patient Privacy — risk of exposing sensitive health data.


2. Algorithmic Bias — model may favor or disadvantage certain patient groups based on race, age, or insurance type.



Preprocessing Pipeline:

Step 1: Clean data by removing duplicates and handling missing lab test results.

Step 2: Feature engineering — e.g., number of previous admissions, chronic illnesses, medication types.

Step 3: Normalize continuous features and one-hot encode categorical data like diagnosis codes.




3. Model Development 

Selected Model:
XGBoost — powerful for tabular medical data, handles missing values, and provides high performance with interpretability (via SHAP values).

Hypothetical Confusion Matrix:

	Predicted Yes	Predicted No

Actual Yes (Positive)	75	25
Actual No (Negative)	20	80


Precision: 75 / (75 + 20) = 0.789

Recall: 75 / (75 + 25) = 0.75




4. Deployment

Integration Steps:

1. Deploy model as a REST API service.


2. Integrate with the hospital’s EHR system.


3. Train staff to interpret predictions and alerts.


4. Monitor and retrain the model periodically.



Healthcare Compliance (HIPAA):

Encrypt patient data in storage and transit.

Restrict access through role-based permissions.

Log all access and prediction records for audits.




5. Optimization 

Method to Address Overfitting:
Use cross-validation during training and regularization techniques (e.g., L1/L2 penalties in logistic regression or max_depth in tree models).




Part 3: 

1. Ethics & Bias 

Impact of Bias:
If training data overrepresents one demographic (e.g., urban patients), the model may underpredict risk for rural or minority patients, worsening healthcare disparities.

Mitigation Strategy:
Use re-sampling techniques to balance data and fairness-aware algorithms that evaluate performance across subgroups.




2. Trade-offs 

Interpretability vs Accuracy:
High-accuracy models (like deep neural networks) may be black boxes, while interpretable models (like logistic regression) may sacrifice accuracy. In healthcare, interpretability is often more important for clinician trust.

Limited Computational Resources:
The hospital may prefer logistic regression or decision trees over resource-heavy models like XGBoost or neural networks to ensure fast, real-time deployment.



Part 4: 

1. Reflection 

Most Challenging Part:
Designing a fair, ethical model that balances performance and interpretability was hardest due to data privacy and bias concerns.

Improvement Strategy:
With more time, I’d run extensive subgroup fairness evaluations and collect more diverse patient datasets to enhance generalizability.




2. Diagram 

Here's a simple AI workflow flowchart (you can draw or digitally sketch this):

[Problem Definition]
        ↓
[Data Collection]
        ↓
[Data Preprocessing]
        ↓
[Model Development]
        ↓
[Evaluation]
        ↓
[Deployment]
        ↓
[Monitoring & Feedback]

