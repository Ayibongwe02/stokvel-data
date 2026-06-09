# Stokvel Dashboard & Forecasting System

A comprehensive **Stokvel Management System** built for tracking contributions, withdrawals, balances, anomaly detection, and time-series forecasting for savings groups (Stokvels). Includes Python data pipelines and interactive Power BI dashboards.

## 🚀 Project Overview

**Stokvel** is a traditional South African savings club where members contribute regularly and can withdraw funds as needed. This project provides:

- **Data Generation & Management**: Synthetic datasets for members with different contribution frequencies (Monthly, Weekly, Quarterly).
- **Data Cleaning & Anomaly Detection**: Scripts to clean data, detect sudden drops, spikes, or missing contributions.
- **Time-Series Forecasting**: Holt-Winters and ARIMA models to predict future balances with performance metrics (RMSE, MAE, MAPE).
- **Interactive Dashboards**: Power BI reports for visualization, member insights, and forecasting.

## 📁 Project Structure
Stokvel/
├── .vscode/                  # VS Code configuration
├── dashboards/               # Power BI files
│   ├── Stokvel Dashboard.pbit
│   └── stokvel dashboard.pbix
├── data/                     # Datasets and generators
│   ├── stokvel_dataset.csv
│   ├── forecasting_dashboard.csv
│   ├── generate_stokvel_data.py
│   ├── merge_forecasting_data.py
│   └── stokvel_expanded.csv (if present)
├── scripts/                  # Core Python automation
│   ├── Auto Exp.py           # Dataset generator
│   ├── data_cleaning.py
│   └── forecasting.py        # Main forecasting + anomaly pipeline
├── notebooks/                # Jupyter/testing scripts
└── doc/                      # Documentation (expand as needed)
text## ✨ Key Features

### 1. Data Pipeline
- Generates realistic member contribution data (M001–M005).
- Supports multiple frequencies: Monthly, Weekly, Quarterly.
- Tracks `contribution_amount`, `withdrawal_amount`, and running `balance`.

### 2. Anomaly Detection
- **Sudden Drops**: Large withdrawals relative to contributions.
- **Spikes**: Unusual activity.
- **Missing Months**: Gaps in contribution history.
- Logs anomalies to CSV for review.

### 3. Forecasting Models
- **Holt-Winters Exponential Smoothing** (trend-focused).
- **ARIMA** (AutoRegressive Integrated Moving Average).
- Compares models using RMSE, MAE, MAPE, AIC/BIC.
- Generates 3/6/12-month forecasts per member.

### 4. Power BI Dashboard
- Visualizations of balances over time.
- Member category analysis (Saver/Spender/Irregular).
- Regional insights (Cape Town, Durban, Johannesburg).
- Forecast vs. Actual comparisons.
- Anomaly highlighting.

## 🛠️ Setup & Usage

### Prerequisites
- Python 3.8+
- Required packages:
  ```bash
  pip install pandas numpy matplotlib statsmodels scikit-learn

Power BI Desktop (for .pbix files).

Running the Scripts

Generate Base Dataset:Bashcd scripts
python Auto Exp.py
Data Cleaning:Bashpython data_cleaning.py
Run Forecasting & Dashboard Generation:Bashpython forecasting.py
Outputs: Updated forecasting_dashboard.csv with metrics and anomalies.

Open Power BI:
Open dashboards/stokvel dashboard.pbix.
Refresh data sources if needed.


Customizing Paths
Update hardcoded paths in scripts (e.g., CSV locations) for your environment.
📊 Sample Data

Members: M001 (Monthly $500), M002 (Monthly $300), M003 (Weekly $200), etc.
Date Range: 2024–2026 (extendable).
Metrics: Balance trends, forecast accuracy, anomaly counts.

🧪 Testing
See notebooks/data_testscript.py for basic data validation.
🤝 Contributing

Fork the repo.
Create a feature branch.
Improve forecasting models, add more visualizations, or enhance anomaly logic.
Submit a Pull Request.

📄 License
MIT License (or specify your preference).

Built for better Stokvel management & financial insights! 💰
South African community savings made smarter with data science.
