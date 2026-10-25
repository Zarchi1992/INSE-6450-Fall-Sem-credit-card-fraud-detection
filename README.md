# Credit Card Fraud Detection System

**INSE 6450 – Fall 2026 **


GitHub: [(https://github.com/Zarchi1992/INSE-6450-Fall-Sem-credit-card-fraud-detection)]

---

## Project Overview

This project develops an AI/ML-based system for detecting fraudulent credit card transactions. 

The task is formulated as a **binary classification problem**:

- `0` (`is_fraud = 0`) — legitimate transaction
- `1` (`is_fraud = 1`) — fraudulent transaction

The main challenge is **extreme class imbalance**: fraud makes up well under 1% of all transactions, so accuracy alone is misleading. Evaluation focuses on precision, recall, F1 and PR-AUC.

---

## Milestones

### Milestone 1 — Data Selection & Exploration

- Dataset selection and justification
- Exploratory data analysis (EDA)
- Missing value, duplicate and class imbalance analysis
- Initial preprocessing and feature engineering
- **Notebook:** `notebooks/01_data_exploration.ipynb`

### Milestone 2 — Model Selection, Training & Evaluation

- Autoencoder-based anomaly detection model design and justification
- Ablation and comparison study
- Fraud detection performance evaluation
- Efficiency metrics
- **Notebook:** `notebooks/02_model_training.ipynb


---

## Dataset

| Item | Details |
|---|---|
| Name | Credit Card Transactions Fraud Detection Dataset |
| Source | [Kaggle (kartik2112/fraud-detection)](https://www.kaggle.com/datasets/kartik2112/fraud-detection) |
| Type | Simulated transactions generated with the Sparkov tool |
| Period | 1 Jan 2019 – 31 Dec 2020 |
| Train file | `fraudTrain.csv` (≈ 1.3M transactions, Jan 2019 – Jun 2020) |
| Test file | `fraudTest.csv` (≈ 556K transactions, Jun – Dec 2020) |
| Target | `is_fraud` |

### Key fields

- **Transaction:** timestamp, amount (`amt`), merchant, merchant category, transaction ID
- **Customer:** card number, gender, job, date of birth, address, city population, coordinates
- **Merchant location:** `merch_lat`, `merch_long`
- **Label:** `is_fraud`

---

## Repository Structure

```
credit-card-fraud-detection-project/
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   ├── README.md                
│   ├── raw/                     
│   └── processed/               
├── notebooks/
│   └── 01_data_exploration.ipynb
└── outputs/
    └── figures/
        ├── class_distribution.png
        └── correlation_heatmap.png
```

**Outputs**

- `data/processed/train_processed.csv`, `data/processed/test_processed.csv`
- `outputs/figures/*.png`

---

## Data Processing Pipeline

1. **Load** raw train and test CSV files
2. **Clean:** parse timestamps and dates of birth, remove duplicate transactions, check missing values
3. **Engineer features** 
4. **Encode** merchant category using one-hot encoding fit on the training set only
5. **Save** processed datasets and EDA figures


## Citation

Dataset: Shenoy, K. *Credit Card Transactions Fraud Detection Dataset*. Kaggle.
https://www.kaggle.com/datasets/kartik2112/fraud-detection


---

