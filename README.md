# Predicting Marketing & Product Performance Using Supervised Learning

**Student:** Nikhilesh Krishnamurthy Iyer | **Matriculation ID:** 52900545

## Project Overview

This project applies supervised learning models to predict `Units_Sold` from the [Marketing and Product Performance Dataset](https://www.kaggle.com/datasets/imranalishahh/marketing-and-product-performance-dataset) (10,000 rows × 17 columns). Seven research questions (RQs) are addressed, each answered by a dedicated Kaggle-ready Jupyter notebook.

---

## Repository Structure

```
├── RQ1_Baseline_Performance.ipynb                    # Linear Regression, Decision Tree, K-NN
├── RQ2_Model_Comparison.ipynb                        # All 6 models compared
├── RQ3_Preprocessing_Impact.ipynb                    # Scaling strategies compared
├── RQ4_Feature_Importance.ipynb                      # Random Forest feature importances
├── RQ5_Sensitivity_to_Evaluation_Metrics.ipynb       # Ranking across MAE / RMSE / R²
├── RQ6_Robustness_and_Generalization.ipynb           # CV folds & train-test split sensitivity
├── RQ7_Final_Model.ipynb                             # Full summary & final model choice
├── README.md
└── requirements.txt
```

---

## 🔬 Research Questions

| # | Research Question | Notebook |
|---|-------------------|----------|
| RQ1 | How effectively do baseline models (Linear Regression, Decision Tree, K-NN) solve the prediction problem? | `RQ1_Baseline_Performance.ipynb` |
| RQ2 | Which model achieves the best predictive performance? | `RQ2_Model_Comparison.ipynb` |
| RQ3 | How do preprocessing strategies (no scaling, StandardScaler, MinMaxScaler) affect performance? | `RQ3_Preprocessing_Impact.ipynb` |
| RQ4 | Which features contribute most to predicting Units Sold? | `RQ4_Feature_Importance.ipynb` |
| RQ5 | How does model ranking change across different evaluation metrics? | `RQ5_Sensitivity_to_Evaluation_Metrics.ipynb` |
| RQ6 | How robust is the best model across different CV settings and train-test splits? | `RQ6_Robustness_and_Generalization.ipynb` |
| RQ7 | What is the most practically useful, interpretable, and reliable model? | `RQ7_Final_Model.ipynb` |

---

## Dataset

- **Name:** Marketing and Product Performance Dataset
- **Source:** [Kaggle](https://www.kaggle.com/datasets/imranalishahh/marketing-and-product-performance-dataset)
- **Rows:** 10,000 | **Columns:** 17
- **Target Variable:** `Units_Sold` (regression)
- **Key Features:** Budget, Clicks, Conversions, Revenue_Generated, ROI, Discount_Level, Bundle_Price, Subscription_Tier, etc.

---

## How to Run on Kaggle

1. Go to [Kaggle](https://www.kaggle.com) and create a new Notebook.
2. Add the dataset: **imranalishahh/marketing-and-product-performance-dataset**.
3. Upload the desired `.ipynb` file (e.g., `RQ1_Baseline_Performance.ipynb`).
4. Click **Run All**. Each notebook:
   - Reads the raw CSV from `/kaggle/input/marketing-and-product-performance-dataset/`
   - Saves a **PDF figure** and a **CSV results table** as outputs.

---

## Models Used

| Model | Type |
|-------|------|
| Linear Regression | Baseline |
| Decision Tree | Baseline |
| K-Nearest Neighbours (K-NN) | Baseline |
| Random Forest | Ensemble |
| Gradient Boosting (XGBoost proxy) | Boosting |
| Support Vector Machine (SVR) | Kernel-based |

---

## Key Results Summary

| Model | Test MAE | Test RMSE | Test R² | Interpretable |
|-------|----------|-----------|---------|---------------|
| **Linear Regression**  | 48.03 | 55.95 | −0.0035 | Yes |
| XGBoost (GB) | 48.10 | 56.10 | −0.0090 | Partial |
| SVR | 48.21 | 56.10 | −0.0091 | No |
| Random Forest | 48.55 | 56.72 | −0.0315 | Partial |
| K-NN | 51.75 | 61.87 | −0.2270 | No |
| Decision Tree | 64.35 | 79.19 | −1.0107 | Yes |

> **Note:** Near-zero/negative R² values indicate that `Units_Sold` has low predictability from the available features — this is itself a meaningful finding suggesting the target may be driven by factors not captured in the dataset.

**Final Recommendation:** Linear Regression — lowest MAE, fully interpretable, and most stable across CV settings.

---

## Evaluation Metrics

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score
- 5-Fold Cross-Validation R²

---

## Author

**Nikhilesh Krishnamurthy Iyer** — Matriculation ID: 52900545
