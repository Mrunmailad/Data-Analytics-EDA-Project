# Project 1 — Advanced EDA & Feature Engineering

Data Science Industrial Training Kit (DecodeLabs, Batch 2026)

## Overview
This project takes a raw, 1,200-row e-commerce orders dataset and turns it into a
mathematically clean dataset ready for machine learning. It covers:

- Statistical handling of missing values
- Outlier detection and neutralization (Z-Score & IQR)
- Engineering 6 new predictive features
- One-hot encoding of categorical variables
- A multicollinearity / correlation check

## Files
- `Project1_Advanced_EDA_Feature_Engineering.ipynb` — the full, executed notebook
- `Dataset_for_Data_Analytics.xlsx` — raw input data
- `cleaned_dataset.csv` — output of the pipeline
- `requirements.txt` — Python dependencies

## How to run

### Option A — Jupyter Notebook (local)
```bash
git clone <your-repo-url>
cd <your-repo-folder>
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```
Open `Project1_Advanced_EDA_Feature_Engineering.ipynb` and run all cells
(the dataset file is already in the folder, so no upload step is needed).

### Option B — Google Colab
1. Go to https://colab.research.google.com
2. File → Upload notebook → select `Project1_Advanced_EDA_Feature_Engineering.ipynb`
   (or open it directly from GitHub via File → Open notebook → GitHub tab and
   paste your repo URL)
3. Run the first code cell under **"0. Setup — Colab only"** — it will prompt you
   to upload `Dataset_for_Data_Analytics.xlsx` from your computer
4. Run the remaining cells top to bottom (Runtime → Run all)

## Key results
- `CouponCode` was ~25.75% missing → recoded as an explicit `"No Coupon"` category
  rather than numerically imputed, since a blank value means no coupon was used
- Outliers in `Quantity`, `UnitPrice`, `ItemsInCart`, `TotalPrice` were checked with
  both Z-Score and IQR methods, then capped (Winsorized) at the IQR bounds to avoid
  losing rows
- New features: `OrderMonth`, `OrderDayOfWeek`, `IsWeekend`, `AvgItemPrice`,
  `CartUtilization`, `HasCoupon`

## Author
DecodeLabs — Data Science Industrial Training Kit, Batch 2026
