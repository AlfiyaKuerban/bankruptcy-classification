# Assignment 5 – Results Summary

## Problem Statement
- Predict whether a company will go bankrupt (binary classification).
- Positive class: bankrupt = 1
- Missing a bankrupt company is more costly than a false alarm.

---

## Dataset Summary
- Dataset contains financial features for companies.
- Most features are numeric.
- Data required minimal preprocessing.

---

## Class Imbalance
- Only ~3% of companies are bankrupt.
- Dataset is highly imbalanced.
- Accuracy is not a reliable metric.

---

## Discrimination Metric (PR-AUC)
- PR-AUC is used as the main metric.
- Focuses on performance for the positive (rare) class.
- More informative than ROC-AUC for imbalanced data.

---

## Calibration Metric (Brier Score)
- Brier score measures probability accuracy.
- Lower score = better calibrated predictions.
- Helps evaluate if predicted risks are realistic.

---

## Feature Selection
- Feature Set B created using top 25 important features.
- Reduced complexity and improved interpretability.
- Performance remained similar or slightly improved.

---

## 5-Experiment Results

| Exp | Model                     | PR-AUC (Val) | Brier (Val) | Notes |
|-----|--------------------------|-------------|------------|------|
| 1   | Logistic Regression      | Low         | High       | Weak baseline |
| 2   | XGBoost Baseline         | Medium      | Good       | Strong improvement |
| 3   | XGBoost (Imbalance)      | Medium+     | Good       | Better recall |
| 4   | XGBoost Tuned            | Best        | Best       | Selected model |
| 5   | XGBoost Selected Features| Medium      | Good       | Simpler model |

---

## Winning Model
- XGBoost Tuned (Experiment 4)
- Highest validation PR-AUC
- Best balance between performance and overfitting

---

## Final Test Results
- Test PR-AUC: (your value)
- Test Brier Score: (your value)
- Model generalizes reasonably well

---

## Confusion Matrix
- Model identifies some bankrupt companies correctly
- Still misses some positives due to imbalance
- Precision-recall tradeoff is visible

---

## Calibration Result
- Calibration curve roughly follows diagonal
- Model slightly overconfident in some ranges
- Still useful for ranking risk

---

## Feature Importance
- Top features are financial indicators
- Important variables relate to company financial health
- Results are reasonable and expected

---

## Overfitting Discussion
- Train PR-AUC is much higher than validation PR-AUC
- Some overfitting exists
- Tuning helped reduce overfitting slightly

---

## AI Usage
- AI tools used for coding and debugging support
- Generated reusable functions and structure guidance
- All outputs reviewed and corrected manually