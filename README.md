# Match Prediction in Speed Dating Using Ensemble Learning

![Python](https://img.shields.io/badge/Python-3.12-blue)
![XGBoost](https://img.shields.io/badge/XGBoost-2.0%2B-green)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.4%2B-orange)


## 📌 Project Overview
This project applies machine learning techniques to predict romantic compatibility based on the **Columbia Speed Dating Dataset**. As Part 1 of the larger "Speed Dating Analysis" group project, this module focuses on the binary classification problem: **Can we predict if a couple will match based on observable features?**

[]The study compares **Random Forest** and **XGBoost** algorithms, specifically addressing the challenge of class imbalance in dating data[cite: 14, 86, 94].

## 🎯 Objectives
* **Binary Classification:** Predict the target variable `match` (0 or 1).
* **Model Comparison:** Evaluate Random Forest vs. XGBoost performance.
* []**Handling Imbalance:** Address the severe imbalance (16.8% match rate) using stratified sampling and class weighting[cite: 234, 401].
* **Interpretability:** Analyze feature importance to understand factors driving romantic matches.

---

## ⚙️ Methodology

### 1. Data Preprocessing
* []**Feature Selection:** Reduced 195 original features to **27 key features**, focusing on demographics, interest correlations, and hobby ratings[cite: 250, 258].
* []**Imputation:** Used median imputation for missing numerical values to handle outliers[cite: 279].
* []**Stratification:** Utilized an 80/20 train-test split with stratification to maintain the 16.8% match rate distribution[cite: 287, 295].

### 2. Algorithms Used
* []**Random Forest:** Selected for its robustness to overfitting and ability to handle mixed feature types (Categorical/Numerical)[cite: 154].
* []**XGBoost (Extreme Gradient Boosting):** Selected for its handling of class imbalance via the `scale_pos_weight` parameter and superior AUC optimization[cite: 182, 185].

---

## 📊 Key Results

### Classification Performance
XGBoost outperformed Random Forest, demonstrating better discrimination ability (AUC) and Recall, which is critical for identifying potential matches.

| Metric | Random Forest | XGBoost |
| :--- | :--- | :--- |
| **AUC-ROC** | 0.6240 | **0.6454** |
| **Accuracy** | 0.8289 | 0.8245 |
| **Recall** | 0.0399 | **0.1286** |
| **F1-Score** | 0.0728 | **0.1934** |

> []*Data Source: Table 6, Experimental Evaluation [cite: 442]*

### Feature Importance
Feature importance analysis revealed that shared interests and age are the strongest predictors of compatibility:
1.  []**Interest Correlation (`int_corr`):** The top predictor for both models, supporting the "similarity breeds attraction" hypothesis[cite: 525, 539].
2.  []**Partner's Age (`age_o`):** Consistently significant across models[cite: 527].
3.  []**Lifestyle Interests:** Specific hobbies like **Clubbing**, **Yoga**, and **Reading** showed high predictive power in XGBoost[cite: 528, 530].

---

## 🛠️ Tech Stack & Environment
* []**Platform:** Google Colab (GPU Runtime) [cite: 300]
* **Libraries:**
    * `pandas` & `numpy` for data manipulation.
    * `scikit-learn` for Random Forest and metrics.
    * `xgboost` for Gradient Boosting.
    * `matplotlib` & `seaborn` for visualization (ROC Curves, Confusion Matrices).

---

## 🚀 Conclusion
The analysis showed that while human behavior in dating is noisy, machine learning can extract meaningful patterns. []**XGBoost** proved superior to Random Forest for this imbalanced dataset, achieving a **5.2% relative improvement in AUC**[cite: 609]. The high importance of "Interest Correlation" confirms that shared preferences are a fundamental driver of romantic matches.
