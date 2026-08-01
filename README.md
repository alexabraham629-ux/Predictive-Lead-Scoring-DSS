# Predictive-Lead-Scoring-DSS.
A machine learning decision support system to predict B2C lead conversion.
# Predictive Lead Scoring & Decision Support System (DSS)

## 📌 Business Challenge
Organizations generate thousands of leads daily, but sales teams waste approximately 60% of their effort on leads that will never convert. This project solves that inefficiency by developing an ML-based Decision Support System (DSS) that predicts conversion probability and prioritizes leads mathematically.

## 📊 Dataset & Preprocessing
* **Dataset:** X Education Lead Scoring (9,240 rows × 37 cols).
* **Preprocessing:** Addressed missing values via median/mode imputation, removed high-missing columns (>40%), and applied IQR clipping for outliers.
* **Feature Engineering:** Created a custom **Engagement Score** by aggregating normalized website activity signals (Time on Website, Total Visits, Page Views).

## 🤖 Machine Learning Framework
* **Champion Model:** Random Forest Classifier (300 trees, class-weight balanced).
* **Baseline Model:** Logistic Regression.
* **Performance:** Achieved an **ROC-AUC of 0.884** and an **Accuracy of 81.3%**.

## 💡 Business Impact & ROI
* **Projected Conversion Lift:** 38.5% → 70%+ by concentrating on 'HOT' leads.
* **Efficiency:** 50-60% reduction in wasted sales outreach.

## 🚀 How to Run the Pipeline
1. Clone the repository.
2. Ensure the dataset is in the root directory.
3. Run the python script to generate the models and launch the interactive ipywidgets DSS dashboard.
