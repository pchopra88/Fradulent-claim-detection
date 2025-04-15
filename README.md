Fraudulent Claim Detection Case Study
Advanced ML Case Study, Data Science C71
Group Members
Parul Chopra
Pavithra Sri S
Sushil Santoshrao Muli

1. Problem Statement
The objective is to build a model to classify insurance claims as either fraudulent or legitimate using historical data. By analyzing features like claim amounts, customer profiles, claim types, and approval times, the goal is to identify potentially fraudulent claims before they are approved.
2. Goals
   -Enhance Global Insure's fraud detection capabilities by leveraging historical data.
   -Identify key indicators that differentiate fraudulent claims.
   -Predict the likelihood of fraud in new claims to enable early intervention and reduce financial loss.

3. Methodology
•	Imported libraries and loaded dataset.
•	Cleaned data: handled missing values, dropped redundant or ID columns, corrected datatypes.
•	Converted date fields and created new date-based features.
•	Target variable: fraud_reported.
•	Performed train-validation split (70:30).
•	Conducted EDA: univariate and bivariate analysis
•	Handled class imbalance using Random OverSampler. (75% non-fraud, 25% fraud initially).
•	Created new features: 
o	Month and year extraction from date columns for better analysis.
o	Binning of the column incident_hour_of_the_day to get useful insight.
o	Log transformation on the column Umbrella_limit as it is highly skewed.
o	Binary mapping on the column insured_sex.
•	Applied one-hot encoding and standardized numerical features.
•	Built Logistic Regression and Random Forest models.
•	Feature selection using RFECV and VIF to remove multicollinearity.
•	Evaluated models using various metrics.
4. Techniques Used
•	Missing Value Imputation: Replaced nulls and '?' with "UNKNOWN".
•	Feature Elimination: Removed high-cardinality or redundant columns.
•	Encoding: One-hot encoding of categorical features.
•	Scaling: StandardScaler for numerical data.
•	Multicollinearity Check: VIF.
•	Feature Selection: RFECV with Logistic Regression.
•	Modeling: Logistic Regression and Random Forest.
•	Cutoff Tuning: Used Precision-Recall curves to set optimal thresholds.
•	Evaluation: Accuracy, Precision, Recall, F1-score, AUC.
•	Visualization: Boxplots, barplots, PR curves, confusion matrices.
5. Model Performance Comparison
Metric	Logistic Regression (Train)	Logistic Regression (Validation)	Random Forest (Train)	Random Forest (Validation)
Accuracy	0.80	0.72	1.00	0.80
Recall (Sensitivity)	0.72	0.59	1.00	0.65
Precision	0.62	0.45	1.00	0.59
Specificity	0.85	0.76	1.00	0.85
F1 Score	0.66	0.51	1.00	0.62
Insights
•	Random Forest (Tuned) performs best on validation data, offering a better F1 score and higher recall.
•	Tuned Random Forest clearly outperforms Logistic Regression across all performance metrics.
•	Recall and F1 Score are especially crucial for fraud detection. A high recall ensures that more fraudulent claims are identified early. The F1 Score balances the trade-off between detecting fraud and minimizing false positives

6. Recommendation
Recommended Model: Random Forest (with hyperparameter tuning)
o	Strong generalization to new data
o	Balanced performance: high recall and precision
o	Better fraud detection capability with fewer false negatives
7. Business Impact
   -Enables early and proactive detection of fraudulent insurance claims.
   -Helps in minimizing financial losses by preventing payouts on suspicious claims.
   -Facilitates efficient, automated, and data-driven claim triaging, reducing manual workload. Early flagging for investigation
   -Empowers the organization to focus investigations on high-risk cases, using the most predictive features identified by the model.


