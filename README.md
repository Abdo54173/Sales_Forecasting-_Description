# 🛒 Walmart Sales Forecasting

Predicting weekly sales for Walmart stores using historical data, store information, and external features like holidays and markdowns. This project implements both **Linear Regression** and **XGBoost** models to forecast future sales and visualize results.  

---

## 📊 Project Overview

- **Goal:** Forecast weekly sales for each store and department.
- **Data Sources:**
  - `train.csv` — Historical sales data.
  - `features.csv` — Weekly store features like temperature, CPI, fuel prices, markdowns, etc.
  - `stores.csv` — Store metadata (type, size, etc.).
- **Techniques Used:**
  - Time-based features (Year, Month, Week, DayOfWeek)
  - Lag features (`Weekly_Sales_lag1`, `Weekly_Sales_lag2`)
  - One-hot encoding for categorical variables (`Type`)
  - Regression models: Linear Regression & XGBoost

---

## ⚡ Features

- 📅 **Date Features:** Year, Month, Week, DayOfWeek
- 🏪 **Store Features:** Type, Size
- 💵 **Economic Indicators:** CPI, Fuel Price, Unemployment
- 💸 **Markdowns:** MarkDown1 → MarkDown5
- ⏳ **Lag Features:** Previous weeks' sales for better prediction
- 🎯 **Target:** `Weekly_Sales`

---

## 🛠 Installation & Usage

```bash
# Clone the repository
git clone https://github.com/Abdo54173/Sales_Forecasting-_Description.git
cd Sales_Forecasting-_Description

# Install dependencies
pip install -r requirements.txt

# Run the forecasting script
python sales_forecasting.py
