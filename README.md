# Heart Failure Survival Prediction: Machine Learning Analysis 🩺

## Project Overview
This project uses clinical data from 299 patients to predict mortality risk from heart failure. The primary goal was to compare a **Linear Model (Logistic Regression)** with a **Non-Linear Ensemble Model (XGBoost)** to see which better identifies high-risk patients.

## Key Clinical Features
Based on the Feature Importance analysis, the top predictors used by the models were:
* **Serum Creatinine**: High levels (indicating kidney stress) were the top risk factor.
* **Ejection Fraction**: Lower heart pumping efficiency significantly increased mortality risk.
* **Age**: Increased age was a steady predictor of higher risk.

## Methodology
1. **Preprocessing**: Scaled numerical features using `StandardScaler` to normalize data for the Logistic Regression weights.
2. **Logistic Regression**: Used as a baseline. It provided high interpretability and clear "Risk vs. Protective" factor visualization.
3. **XGBoost**: Used to capture complex, non-linear relationships. I intentionally set `max_depth=3` to prevent overfitting to the small dataset.
4. **Comparison**: Evaluated both models using Confusion Matrices to analyze the trade-off between overall accuracy and clinical safety (Recall).

## Performance Comparison
| Metric | Logistic Regression | XGBoost |
| :--- | :--- | :--- |
| **Accuracy** | 80.00% | 76.67% |
| **Recall (Deaths Caught)** | 0.56 | **0.64** |
| **False Negatives (Misses)** | 11 | **9** |



## Final Conclusion
While Logistic Regression achieved a higher overall accuracy, **XGBoost is the superior model for clinical application.** In a medical context, a "False Negative" (failing to identify a patient who will die) is much more dangerous than a "False Positive" (a false alarm). XGBoost reduced the number of misses from 11 to 9, demonstrating better sensitivity for high-risk cases.

## Tools Used
* **Python**: Core programming language.
* **Pandas/NumPy**: Data manipulation.
* **Scikit-Learn**: Scaling and Logistic Regression.
* **XGBoost**: Gradient Boosted Decision Trees.
* **Seaborn/Matplotlib**: Professional data visualization.
