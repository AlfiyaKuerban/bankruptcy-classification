# Assignment 5 Summary

## Problem Statement

* Predict whether a company will go bankrupt (binary classification)
* Positive class = bankrupt (1)
* Business goal: identify high-risk companies early

---

## Dataset Summary

* Financial dataset with company-level features
* Target variable: bankruptcy (0 / 1)
* Mostly numerical features

---

## Class Imbalance

* Only ~3% of companies are bankrupt
* Dataset is highly imbalanced
* Accuracy is not a suitable metric

---

## Discrimination Metric (PR-AUC)

* PR-AUC used as primary metric
* Focuses on performance for rare positive class
* Measures ability to rank high-risk companies

---

## Calibration Metric (Brier Score)

* Brier score evaluates probability quality
* Lower Brier score = better calibrated predictions

---

## Feature Selection

* Feature Set A: all available features after cleaning
* Feature Set B: top selected features (reduced set)
* Purpose: test whether fewer features improve generalization

---

## 5-Row Experiment Table

* 5 models compared:

  1. Logistic Regression (baseline)
  2. XGBoost baseline
  3. XGBoost with imbalance handling
  4. XGBoost tuned
  5. XGBoost with selected features
* Compared using validation PR-AUC and Brier score


| exp_id | model                     | feature_set | main_settings    | train_pr_auc | val_pr_auc | overfit_gap | val_roc_auc | val_brier | threshold | val_precision | val_recall | val_f1 | selected_finalist | notes              |
| ------ | ------------------------- | ----------- | ---------------- | ------------ | ---------- | ----------- | ----------- | --------- | --------- | ------------- | ---------- | ------ | ----------------- | ------------------ |
| 1      | Logistic Regression       | A           | default          | 0.06         | 0.04       | 0.02        | 0.59        | 0.043     | 0.5       | 0.00          | 0.00       | 0.00   | No                | weak baseline      |
| 2      | XGBoost Baseline          | A           | default          | 1.00         | 0.49       | 0.51        | 0.95        | 0.024     | 0.5       | 0.63          | 0.30       | 0.41   | No                | strong but overfit |
| 3      | XGBoost Imbalance         | A           | scale_pos_weight | 1.00         | 0.49       | 0.51        | 0.96        | 0.024     | 0.5       | 0.55          | 0.36       | 0.44   | No                | better recall      |
| 4      | XGBoost Tuned             | A           | tuned params     | 1.00         | 0.60       | 0.40        | 0.96        | 0.020     | 0.5       | 0.69          | 0.27       | 0.39   | Yes               | best overall       |
| 5      | XGBoost Selected Features | B           | top features     | 0.99         | 0.46       | 0.53        | 0.95        | 0.022     | 0.5       | 0.60          | 0.36       | 0.45   | No                | simpler model      |


---

## Winning Model

* XGBoost tuned model selected
* Highest validation PR-AUC
* Good Brier score (reasonable calibration)
* Better balance between performance and overfitting

---

## Final Test Results

* Test PR-AUC consistent with validation
* Brier score remains low
* Model generalizes reasonably well

---

## Confusion Matrix

* Model detects some bankrupt companies
* Still misses some positives due to class imbalance
* Trade-off between precision and recall

---

## Calibration Result

* Calibration curve close to diagonal
* Slight overconfidence at higher probability ranges
* Overall probabilities are reasonably reliable

---

## Feature Importance

* Financial indicators are most important features
* Top features align with business intuition
* Model relies on meaningful variables

---

## Overfitting Discussion

* Training PR-AUC higher than validation PR-AUC
* Moderate overfitting observed
* Controlled through tuning and validation selection

---

## AI Usage

* Used Codex to help generate evaluation function
* Assisted with experiment structure and code organization
* All outputs reviewed and verified manually
