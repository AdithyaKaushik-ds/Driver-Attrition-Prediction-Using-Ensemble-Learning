# Driver-Attrition-Prediction-Using-Ensemble-Learning

The aim of this project is to build a predictive model to identify which drivers are likely to leave the platform using historical performance and demographic data. Accurate churn prediction is vital for reducing attrition costs and improving retention strategies.

📊 Dataset Overview

Records: ~19,100 monthly logs across ~2,380 unique drivers

Time Span: Jan 2019 – Dec 2020 (700 days)

Attributes: Age, gender, city, education level, income, joining details, business value, quarterly ratings, etc.

Target Variable: target (1 if driver left, 0 otherwise), derived from LastWorkingDate

🔍 Exploratory Data Analysis (EDA)

Univariate and Bivariate Visualizations: Analyzed distribution and relationships of key attributes (e.g., Grade vs Income, Rating vs Business Value)

Key Insights:

Most drivers have education level 1 or 2.

97.3% did not get a raise, while 54.6% were promoted.

Business value and ratings show decline after age 45.

City-wise distribution revealed driver concentration in a few locations.

🧪 Feature Engineering

Created binary flags for:
    
    - Negative / Zero Business Value
    
    - Increased/decreased Quarterly Rating, Income, and Grade

Derived features:

   - Ratio of Total Business Value to Income (TBV2Inc)
    
   - Year of joining, rank composite

Label encoding for city and standardization of features

⚙️ Model Development

Data Handling:

Missing values imputed

Features scaled using StandardScaler

Train-Test split: 80-20

Addressed class imbalance using stratified sampling and class weights

Models Built:

Random Forest (Val Acc: ~85.7%)

LightGBM (Val Acc: ~86.6%)

XGBoost (Val Acc: ~86.1%)

Gradient Boosting (Val Acc: ~87.2%)

AdaBoost (Val Acc: ~88.0%)

Voting Classifier (Val Acc: ~88.0%, best ensemble)

📈 Evaluation Metrics

Metric	Best Value (VotingClassifier)
Accuracy	88.0%
Precision	91% (class 1)
Recall	92% (class 1)
F1 Score	91% (class 1)
ROC AUC Score	~86%

📌 Recommendations

Focus retention efforts on drivers with declining quarterly ratings and zero/negative business value

Create training and incentive programs for newer drivers

Use adaptive models to regularly re-evaluate churn behavior based on fresh data

