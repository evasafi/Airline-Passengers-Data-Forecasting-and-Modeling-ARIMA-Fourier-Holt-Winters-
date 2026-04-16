# IE 333: Data Science and Analytics — Time Series Forecasting Project

## Overview

This project applies Exploratory Data Analysis (EDA) and classical time series modeling to forecast **monthly international airline passenger numbers** from 1949 to 1960. We implement three forecasting models, compare their performance, and discuss the results.

## Dataset

- **Source:** Box, Jenkins, and Reinsel (1976) — *Time Series Analysis, Forecasting and Control*
- **Size:** 144 monthly observations (January 1949 – December 1960)
- **Variable:** Number of international airline passengers (in thousands)

## Models Implemented

| Model | Description |
|-------|-------------|
| **SARIMA** | Seasonal ARIMA with automatic parameter selection via `auto_arima` |
| **Polynomial + Fourier Regression** | Quadratic trend + Fourier sine/cosine terms for seasonality |
| **Holt-Winters** | Triple Exponential Smoothing with multiplicative trend and seasonality |

## Results

| Model | RMSE | MAPE | R² |
|-------|------|------|-----|
| SARIMA (1,1,0)(0,1,0,12) | 35.08 | 6.12% | 0.798 |
| Poly + Fourier Regression | 44.07 | 9.14% | 0.682 |
| **Holt-Winters (Multiplicative)** | **21.34** | **4.26%** | **0.925** |

Holt-Winters outperformed both other models due to its ability to directly model the multiplicative seasonality present in the data.

## Repository Contents

```
├── airline-passengers.csv                  # Dataset
├── IE333_Airline_Passengers_Project.ipynb   # Jupyter Notebook (code + outputs)
├── IE333_Code_Explanation.docx             # Detailed explanation of the code
└── README.md
```

## How to Run

1. Clone the repository:
   ```
   git clone https://github.com/YOUR-USERNAME/IE333-Time-Series-Project.git
   ```
2. Install dependencies:
   ```
   pip install pandas numpy matplotlib seaborn statsmodels pmdarima scikit-learn scipy
   ```
3. Open the notebook:
   ```
   jupyter notebook IE333_Airline_Passengers_Project.ipynb
   ```
4. Run all cells from top to bottom.

## Key Findings

- The data shows a clear upward trend with strong 12-month seasonality
- Seasonal amplitude grows over time, confirming a multiplicative pattern
- Holt-Winters is the best fit for this type of data because it directly models multiplicative seasonality
- SARIMA performs well but handles the growing seasonal swings less directly
- Regression captures the overall shape but cannot adapt to changing patterns over time

## Tools Used

Python, Pandas, NumPy, Matplotlib, Seaborn, Statsmodels, Pmdarima, Scikit-learn
