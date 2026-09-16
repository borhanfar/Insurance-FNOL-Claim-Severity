# Project
Explores whether motor claim ultimate severity (Capped Incurred) can be meaningfully predicted from First Notification of Loss (FNOL) characteristics.
# Dataset
First Notification of Loss dataset(7,691 rows × 46 features)
# Methodology & Pipeline
### Data Quality & Cleansing
1) Standardized unformatted missing placeholders (n/k, -, #) to true NaNs.
2) Filtered out negative/invalid anomalies.
### Feature Engineering & Reduction
1) Aggregated high-cardinality region, third-party type, and injury severity flags.
2) Reduced feature set from 46 to 23 modeling features.
### Modeling Architecture
#### Two-Stage Approach
XGBoost Classification (payout probability) + XGBoost Regression (severity on paid claims).
#### One-Stage Approach
Direct XGBoost Regression on all claims.
### Hyperparameter Tuning & Validation
5-fold cross-validation tracked via MLflow.
### Performance Evaluation
Evaluated via PR-AUC, F1-Score, RMSE, MAE, and average error distribution across claim value tiers.
### Practical Considerations
Inflation indexing (adjusting historical claims to current RPI) for real-world deployment.
