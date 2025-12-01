# 📈 NIFTY 50 Financial Market Analysis (2024–2025)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-Analysis-150458)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=power-bi)
![Financial Analysis](https://img.shields.io/badge/Focus-Financial%20Analysis-informational)

## 🚀 Project Overview
This project performs a complete **end-to-end financial data analysis** of the **NIFTY 50 Stock Index** using a hybrid analytical stack: **Python**, **Excel**, and **Power BI**.

The analysis covers a full year of index performance (17 Nov 2024 to 17 Nov 2025). The primary goal is to derive quantitative insights into **market trends, volatility, and risk-return profiles**, making it a perfect portfolio piece for **Data Analyst, Financial Analyst, and Business Analytics** roles.

### Key Analytical Steps:
* **Data Cleaning & Preprocessing**
* **Daily Returns & Risk Metrics Calculation**
* **Exploratory Data Analysis (EDA)**
* **Visualizations & Trend Analysis (MAs)**
* **Interactive Power BI Dashboard**


## 🧼 1. Data Cleaning

Cleaning steps applied:
Converted Date column to proper datetime format
Sorted dataset by Date
Removed missing values
Standardized column names
Created new calculated columns:
Daily Return %
Month
Volatility (20-day rolling)

## 📊 2. Key Calculations

✔ Daily Return % 
Daily Return % = (Close_today - Close_yesterday) / Close_yesterday

✔ Total Return %
Total Return % = (Last Close / First Close - 1) * 100

✔ Total Trading Days
Count of all trading days in dataset.

✔ Max Daily Gain %
Highest single-day % return.

✔ Max Daily Loss %
Lowest single-day % return.

✔ Monthly Average Return %
Average of daily returns grouped by month.

## 🐍 3. Python Analysis Code (Simplified)

```text
import pandas as pd

df = pd.read_csv("NIFTY_50_Analysis.csv")

df['Date'] = pd.to_datetime(df['Date'])
df = df.sort_values('Date')

# Daily Return
df['Daily_Return'] = df['Close'].pct_change()

# Month column
df['Month'] = df['Date'].dt.to_period('M')

# KPIs
total_return = (df['Close'].iloc[-1]/df['Close'].iloc[0] - 1) * 100
max_gain = df['Daily_Return'].max() * 100
max_loss = df['Daily_Return'].min() * 100

# Monthly Average Returns
monthly_avg = df.groupby('Month')['Daily_Return'].mean() * 100
```

## 📊 4. Power BI Dashboard

Dashboard includes:

Closing Price Trend

Daily Volatility

Top Gains & Losses

Monthly Average Returns

Key Metrics Cards (KPIs)

📌 Measures Used (DAX)

### Total Return %

```text
Total Return % =
DIVIDE(
    MAX(NIFTY_50_Analysis[Close]) - MIN(NIFTY_50_Analysis[Close]),
    MIN(NIFTY_50_Analysis[Close])
)
```

### Max Daily Gain %

```text
Max Daily Gain % = MAX(NIFTY_50_Analysis[Daily Return %])
```

### Max Daily Loss %

```text
Max Daily Loss % = MIN(NIFTY_50_Analysis[Daily Return %])
```

### Total Trading Days

```text
Total Trading Days = COUNTROWS(NIFTY_50_Analysis)
```

### Monthly Avg Return %

```text
Monthly Avg Return % =
AVERAGEX(
    VALUES(NIFTY_50_Analysis[Month]),
    AVERAGE(NIFTY_50_Analysis[Daily Return %])
)

```

## 📁 5. Visualizations

The following visual files are included inside /visuals/:

closing_price.png → Closing Price Trend

daily_returns.png → Daily Return Line Chart

moving_averages.png → MA20, MA50, MA200 trend

returns_histogram.png → Daily Returns Distribution

volatility.png → 20-Day Rolling Volatility

## 🧠 6. Insights

Key insights you can highlight:

NIFTY 50 showed consistent growth/declines over the period.

Volatility spikes indicate higher market risk at specific periods.

Daily returns distribution shows the risk-return profile.

Moving averages help identify trend direction.

Monthly returns reveal seasonal market patterns.

🛠 Tools Used

Python → pandas, matplotlib

Excel → cleaning & formula validation

Power BI → interactive dashboard

GitHub → project hosting

## 🎯 Conclusion

This project provides a complete understanding of:

Market performance

Risk analysis

Daily & monthly behavior

Trends & volatility

Perfect for Data Analyst, Financial Analyst, and Business Analytics portfolios.

## 📂 Project Structure
The repository is organized logically to separate data, code, visualizations, and documentation.

```text
NIFTY_50_Analysis/
│
├── data/
│   ├── NIFTY_50.csv              # Raw historical index data
│   ├── NIFTY_50_Analysis.csv     # Data prepared in Excel/pre-processed
│   └── cleaned_nifty.csv         # Final, cleaned dataset used for analysis
│
├── scripts/
│   └── analysis.py               # Python script for all calculations and visualizations
│
├── visuals/
│   ├── closing_price.png         # Long-term price trend
│   ├── daily_returns.png         # Fluctuation and volatility plot
│   ├── moving_averages.png       # MA20, MA50, MA200 for technical analysis 

[Image of a stock price chart with 20, 50, and 200-day moving averages]

│   ├── returns_histogram.png     # Distribution of daily returns (risk profile)
│   └── volatility.png            # Rolling historical volatility chart
│
└── README.md                     # This project documentation file
```

## 📬 Contact Information

Thank you for reviewing this project! I am actively seeking opportunities and would love to connect.

| Channel | Details |
| :--- | :--- |
| **Name** | Jitesh Jangam |
| **Email** | `jangamjitesh1@gmail.com` |
| **LinkedIn** | linkedin.com/in/jitesh-jangam |

