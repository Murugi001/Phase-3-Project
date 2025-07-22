### Project Overview:
###  Customer Churn Prediction for SyriaTel

## 1. Business Understanding

SyriaTel, like many telecom providers, operates in a highly competitive industry where retaining existing customers is often more cost-effective than acquiring new ones. Customer churn — when subscribers stop using the service — directly impacts revenue and long-term profitability.

The challenge is that churn doesn't usually happen randomly. It can result from dissatisfaction with service quality, pricing, customer support, or competitors' offers. If SyriaTel can predict which customers are likely to churn, it can act proactively to retain them through targeted interventions.

### 2. Business Goal
To reduce customer churn and increase customer lifetime value (CLTV) by identifying subscribers who are most likely to leave soon.

Specifically:

i)  Build a Predictive Model for Churn

ii) Gain Insight into Churn Drivers

iii) Provide Strategic Recommendations

## 3 Intended Audience

a. Telecom Business Executives: Need insights into churn trends, retention ROI, and how churn relates to product pricing.

b. Marketing & Customer Retention Teams: Need a list of high-risk customers for proactive targeting.

c. Customer Experience/Call Center Managers: Want to understand which service areas such customer service calls correlate with churn.

### Data Source
This study utilized the Churn in Telecoms dataset from Kaggle, which comprises 3,333 entries across 21 columns with no missing values, as confirmed by the .info() function. The dataset includes a mix of categorical variables such as state, international plan, voice mail plan, and churn, alongside numerical variables like total day minutes, customer service calls, and account length.

### Data Exploration

At this stage of the analysis, several preprocessing steps were undertaken to prepare the data for modeling. First, columns with low predictive value—such as the phone number—were dropped. This was followed by descriptive analysis of numerical features to understand their distribution and central tendencies.

Next, the dataset was evaluated for class imbalance to determine whether one outcome (churn or no churn) significantly outweighed the other, which could bias the model. To ensure the data was ready for machine learning algorithms, categorical variables were converted into numeric form. One-hot encoding was specifically applied to variables like international plan and voice mail plan.

The preprocessing phase concluded with a correlation analysis between the churn variable and other features—both numerical and categorical—to assess potential relationships and identify multicollinearity concerns.

### Modelling

Before training the models, the dataset was split into training and testing sets to enable the model to learn patterns from historical data and evaluate performance on unseen data. Standard scaling was then applied to numerical columns in the training set. 

To address the class imbalance observed in the target variable, the SMOTE technique was used. After resampling, the training dataset became perfectly balanced, with 50% of the samples representing customers who did not churn and 50% representing those who did.

After applying SMOTE, the resampled training data was initially fitted into a logistic regression model. The model was then used for prediction and evaluated using metrics such as accuracy, precision, recall, confusion matrix, and ROC curves. 

Two additional models—Random Forest and Decision Tree—were also trained on the same dataset and evaluated using the same metrics. To enhance performance, both models were further subjected to hyperparameter tuning to assess whether the evaluation metrics would improve.

### Evaluation