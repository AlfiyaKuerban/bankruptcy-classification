# Bankruptcy Classification Project

## Quick Links
* [Results Summary](./Assignment5-Summary.md)

## Overview

This project builds machine learning models to predict whether a company will go bankrupt using financial data.
Multiple models are compared, and the final model is selected based on validation performance.

---

## Repository Structure

* `notebook/` → main Jupyter notebook with full workflow
* `data/` → dataset used for modeling (`data.csv`)
* `Assignment5-Summary.md` → results summary (jot notes) 
* `README.md` → project instructions and summary

---

## How to Run

### 1. Clone the repository

```bash
git clone https://github.com/AlfiyaKuerban/bankruptcy-classification.git
cd bankruptcy-classification
```

### 2. Create and activate virtual environment (optional)

```bash
python -m venv venv
venv\Scripts\activate   # Windows
```

### 3. Install required packages

```bash
pip install pandas numpy scikit-learn xgboost matplotlib seaborn
```

### 4. Run the notebook

* Open the notebook in VS Code or Jupyter
* Run all cells from top to bottom

---

## Notes

* The notebook is fully reproducible and runs from start to finish.
* The dataset is already included in the repository.
* Results may vary slightly if random seeds are not fixed.

---
