# Credit Card Transaction Fraud Detection (PySpark)

This project analyzes a dataset of credit card transactions using PySpark to uncover fraud patterns and generate meaningful insights through data transformation and visualization.

---

## Dataset

- Source: https://www.kaggle.com/datasets/e47f88e5e8ce59c9598475a107d9a80ebc363a83859a59facb069b13a9001773
- Format: Nested JSON with embedded personal details and timestamps
- Size: ~160K records, real-world-like structure

---

## Data Transformation Overview

### Handling PII
- `cc_num`: Masked using SHA-256 hashing
- `person_name`: Split into `first` and `last` using regex, discarding noisy parts

### Data Cleaning
- Parsed and flattened nested JSON fields (`personal_detail`, `address`)
- Converted dirty string types (e.g. `amt`) into floats
- Normalized timestamps (`trans_date_trans_time`, `merch_eff_time`, `merch_last_update_time`) to UTC+8 in `YYYY-MM-DD HH:MM:SS.SSSSSS Z` format
- Removed nulls and handled inconsistent naming formats

---

## Visualizations

All visualizations were created using Spark aggregation + Pandas/Seaborn for rendering.

- ** Fraud Count by Merchant Category**
- ** Monthly Fraud Trends**
- ** Top 15 States with Most Fraud Cases**
- ** Avg Fraud Amount by Gender**
- ** Top 10 Fraudulent Merchants**
- ** Fraud Rate by Job Title**

---

## 🛠 How to Run

1. Clone the repo  
   ```bash
   git https://github.com/datomnurdin/paynet-de-etl-cc
   cd paynet-de-etl-cc
   git lfs install
   python3 -m jupyterlab
