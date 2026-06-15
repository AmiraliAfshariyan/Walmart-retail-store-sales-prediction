# 🛒 Walmart Retail Store Sales Prediction

A data-driven predictive analytics solution designed to **forecast weekly retail sales across Walmart stores**. By evaluating historical sales patterns alongside macroeconomic factors and environmental metrics (such as temperature, fuel prices, and CPI), this project provides actionable insights to optimize inventory management, supply chain logistics, and revenue forecasting.

---

## 🎯 Key Features
- **Exploratory Data Analysis (EDA):** Comprehensive visualization of sales trends, seasonal fluctuations, and the impact of holidays on consumer behavior.
- **Advanced Temporal Feature Engineering:** Extraction of discrete time-series components (`Year`, `Month`, `Week`) from raw dates to capture seasonal variations.
- **Multi-Scaler Preprocessing Pipeline:** Evaluation of `StandardScaler`, `RobustScaler`, and `QuantileTransformer` techniques to handle differing economic metrics and outliers.
- **Robust Predictive Regressor:** Implements optimized regression architectures tailored to continuous financial and operational forecasting.

---

## 📊 Dataset Structure
The system processes a structured transactional dataset (`Walmart_Sales.csv`) containing historical retail records with the following core features:
- `Store`: The specific store identifier number.
- `Date`: The historical sales week stamp.
- `Weekly_Sales`: **Target Variable** representing the total sales revenue for the given store.
- `Holiday_Flag`: Binary indicator (`1` if the week includes a major holiday, `0` otherwise).
- `Temperature`: Ambient temperature in the store's region (°F).
- `Fuel_Price`: Regional cost of fuel per gallon.
- `CPI`: Consumer Price Index (inflation measurement metric).
- `Unemployment`: Prevailing regional unemployment rates.
- **Engineered Metrics:** `Year`, `Month`, and `Week` derived to capture precise seasonal timelines.

---

## 🛠️ Data Pipeline & Preprocessing

### 1. Feature Engineering & Time Extraction
To allow standard machine learning models to comprehend temporal dependencies, the raw `Date` dimension is successfully decomposed into explicit numerical features (`Year`, `Month`, `Week`). This prevents temporal data loss and emphasizes peak shopping cycles.

### 2. Multi-Scaler Benchmarking
Given that economic features operate on fundamentally distinct scales (e.g., CPI indices vs. holiday binary flags), the numerical vectors are benchmarked across three major scalers:
- **StandardScaler:** Normalizes features to align with a zero mean and unit variance.
- **RobustScaler:** Minimizes distortion from extreme weather variations or sharp economic shifts using Interquartile Ranges (IQR).
- **QuantileTransformer:** Smooths highly skewed distributions by mapping continuous financial trends into a balanced normal distribution.

### 3. Validation Framework
The records are split into independent training and validation datasets via `train_test_split` to ensure realistic testing conditions and prevent data leakage between historical sequences.

---

## 🤖 Modeling & Evaluation

The core regression engine models the complex interplay between pricing dynamics, regional climate conditions, special seasonal holidays, and continuous sales outputs.

### 📈 Core Metrics Covered
To ensure maximum financial reliability and accurate inventory estimations, the pipeline monitors rigorous regression performance benchmarks:
- **$R^2$ Score (Coefficient of Determination):** Evaluates the exact proportion of sales variance captured by the model features.
- **MSE (Mean Squared Error):** Quantifies squared residual variances to strictly penalize large prediction errors.
- **RMSE (Root Mean Squared Error):** Provides the standard deviation of residuals, expressing error rates directly in standard currency values for easy business evaluation.

---

## 🚀 Installation & Usage

### Prerequisites
Make sure you have Python installed on your system. Install the required analytical data-science dependencies via pip:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
