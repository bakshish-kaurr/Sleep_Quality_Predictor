# Sleep Quality Predictor

## Overview

This project predicts a user's sleep quality based on their late-night smartphone usage patterns.  
It uses machine learning models trained on phone behavior data such as screen time, app usage, phone unlocks, and screen brightness.




## How the System Works

The complete working of the project is divided into clear stages:



## 1. Data Generation / Collection

The system works on phone behavior data collected during late-night hours (10 PM to 6 AM).

Each record represents one user-day and contains:

- Late-night screen time
- Social media usage hours
- Gaming app usage hours
- Educational app usage hours
- Work-related app usage hours
- Number of phone unlocks after 11 PM
- Average screen brightness at night
- Accelerometer movement (restlessness indicator)
- Time to first phone unlock in the morning
- Day of the week

The target value is:
- **Sleep Quality Score (1–10)**

Synthetic data is generated with realistic correlations to simulate real-world behavior.



## 2. Data Preprocessing

Before training the model, the following preprocessing steps are applied:

- Handling missing values (if any)
- Converting categorical features (day of week) into numerical form
- Feature scaling where required
- Splitting data into:
  - Training set
  - Testing set

This ensures the model learns patterns correctly and is evaluated fairly.



## 3. Feature Engineering

New meaningful features are created from raw data to improve prediction accuracy:

- Total screen time
- Late-night activity ratio
- Productive app ratio (educational + work apps)
- Engagement score (screen time × night unlocks)
- Weekend indicator

These engineered features help the model capture deeper behavior patterns.



## 4. Model Training

Multiple machine learning models are trained and compared:

### Models Used
- Linear Regression
- Random Forest Regressor
- Gradient Boosting Regressor

Each model learns the relationship between phone behavior features and sleep quality score.



## 5. Model Evaluation

Models are evaluated using standard regression metrics:

- R² Score (accuracy of prediction)
- RMSE (Root Mean Squared Error)
- MAE (Mean Absolute Error)

The **Random Forest model** performs best and is selected as the final model because it:
- Handles non-linear relationships well
- Reduces overfitting
- Provides feature importance values



## 6. Prediction Process

For a new user:

1. Phone behavior data is provided as input
2. The same preprocessing and feature engineering steps are applied
3. The trained Random Forest model predicts:
   - Sleep quality score (1–10)

This prediction represents how good or poor the user's sleep is likely to be based on their phone usage.



## 7. Feature Importance Analysis

The model ranks features based on their impact on sleep quality prediction.

Key findings:
- Late-night screen time has the strongest negative impact
- Social media usage significantly reduces sleep quality
- Frequent phone unlocks worsen sleep
- Educational and work app usage slightly improve sleep quality

This explains *why* the model gives a particular prediction.



## 8. Output

The final output of the system includes:

- Predicted sleep quality score
- Contribution of major features affecting sleep
- Interpretation of phone behavior impact

No external services or APIs are required.  
All predictions are computed locally using the trained model.



## Conclusion

The working of this project follows a simple pipeline:

Data Collection  
→ Preprocessing  
→ Feature Engineering  
→ Model Training  
→ Evaluation  
→ Prediction  

This makes the system easy to understand, reproducible, and suitable for academic and learning purposes.
