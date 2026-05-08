# Uber Fare Prediction using Spatiotemporal Modeling

This project builds an end-to-end machine learning pipeline to predict Uber ride fares using spatial and temporal features. Beyond prediction, the goal is to understand the main factors that drive pricing behavior and validate whether these patterns generalize to a real-world dataset.

---

## Project Objectives

- Predict ride fares using machine learning models  
- Understand how spatial and temporal variables influence pricing  
- Compare linear and nonlinear models  
- Validate learned patterns using a separate NYC Taxi dataset  

---

## Datasets

### Uber (Kaggle)
Used as the primary dataset for training and modeling.

Features include:
- Pickup and dropoff coordinates  
- Fare amount  
- Passenger count  
- Pickup datetime  

### NYC Yellow Taxi (Validation only)
Used exclusively for pattern validation, not model training.

---

## Data Processing

The data pipeline includes:

- Removal of missing and invalid values  
- Filtering unrealistic fares and coordinates  
- Geographic filtering for NYC region  
- Outlier removal (99.5th percentile)  
- Feature engineering for spatial and temporal signals  

---

## Feature Engineering

### Temporal Features
- Hour of day  
- Day of week  
- Weekend indicator  
- Rush hour indicator  

### Spatial Features
- Trip distance (Haversine formula)  
- Pickup and dropoff coordinates  

### Interaction Features
- Distance × rush hour  
- Distance × weekend  

---

## Models

Three models were evaluated:

- Linear Regression (baseline)  
- Random Forest Regressor  
- XGBoost Regressor  

The dataset was split into training and test sets using a reproducible sample for computational efficiency.

---

## Evaluation

Performance was measured using:

- MAE (Mean Absolute Error)  
- RMSE (Root Mean Squared Error)  

### Best Model Performance
- XGBoost achieved the lowest MAE (~$1.96)  
- Improvement of ~$0.22 over Linear Regression baseline  

---

## Key Insights

- Trip distance is the strongest predictor of fare  
- Temporal factors (hour, weekend, rush hour) have secondary influence  
- Nonlinear models outperform linear regression, but gains are moderate  
- Patterns remain consistent across Uber and NYC Taxi datasets  

---

## Cross-Dataset Validation

To test generalization, patterns were compared with NYC Taxi data:

- Strong consistency in fare–distance relationship  
- Temporal effects exist but are less stable across datasets  
- Reinforces that spatial structure is the main pricing driver  

---

## Conclusion

This project demonstrates that Uber fare prediction is primarily driven by spatial distance, with temporal variables providing secondary adjustments. While advanced models improve accuracy slightly, the most important value lies in understanding the underlying pricing structure.

---

## Tech Stack

- Python  
- Pandas / NumPy  
- Scikit-learn  
- XGBoost  
- Seaborn / Matplotlib  

---

