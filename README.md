# ⚡ Smart Home Energy Analysis & Prediction

## 📌 Overview

Here we focused on **data preparation, feature engineering, regression modeling, statistical analysis, and time series forecasting** for a smart home energy dataset.

The goal is to:

* Clean and preprocess raw energy data
* Engineer meaningful features
* Build predictive models for energy consumption
* Perform statistical validation
* Forecast future energy demand

---

## 📂 Dataset - https://www.kaggle.com/datasets/mexwell/smart-home-energy-consumption

The dataset contains smart home energy-related attributes such as:

* Household details (occupants, ID)
* Environmental factors (temperature, humidity)
* Energy usage (appliances, AC, heater)
* Solar energy generation
* Electricity pricing
* Peak hour usage

---

## 🧹 Data Preprocessing

### Key Steps:

* Replaced invalid values (`?`) with `NaN`
* Converted data types:

  * `date` → datetime
  * categorical columns → category
* Converted numerical columns using `to_numeric()`
* Handled missing values:

  * **Median** for numeric columns (robust to outliers)
  * **Forward fill** for date
  * **Mode** for categorical features

---

## 📊 Outlier Detection & Treatment

* Visualized outliers using **boxplots**
* Applied **IQR method** to cap extreme values
* Columns treated:

  * `appliance_usage_hours`
  * `ac_usage_hours`
  * `energy_consumption_kwh`

---

## ⚙️ Feature Engineering

New features created:

1. **Total Usage Hours**

   * Captures total device usage
   * `appliance + AC + heater`

2. **Temperature Effect**

   * Measures heat stress above 22°C baseline

3. **Net Energy Usage**

   * `consumption - solar generation`
   * Represents grid dependency

---

## 🤖 Regression Modeling

### Models Used:

* Linear Regression
* Decision Tree Regressor
* Random Forest Regressor

### Workflow:

* Train-test split (80-20)
* Model training and prediction
* Performance evaluation using:

  * MAE (Mean Absolute Error)
  * RMSE (Root Mean Squared Error)
  * R² Score

### Output:

* Comparison of all models
* Best model selected based on highest R²

---

## 📈 Statistical Analysis

### Hypothesis Testing

* Test: **Pearson Correlation**
* Hypothesis:

  * H₀: Temperature has no effect on energy consumption
  * H₁: Temperature affects energy consumption

### Confidence Interval

* Calculated **95% CI** for average energy consumption

### Correlation Analysis

* Examined relationships between:

  * Temperature
  * Appliance usage
  * Energy consumption

---

## ⚠️ Model Behavior Concepts

### Overfitting

* Model memorizes training data
* High train accuracy, low test accuracy

### Underfitting

* Model too simple
* Poor performance on both train and test

---

## ⏳ Time Series Forecasting

### Steps:

1. Resampled data to **daily energy consumption**
2. Checked stationarity using **ADF Test**
3. Applied differencing if needed
4. Trained **ARIMA(1,1,1)** model

### Evaluation:

* MAE
* RMSE

### Output:

* Forecasted next **10 days of energy consumption**

---

## 💡 Business Impact

This project helps in:

* 🔋 Predicting future energy demand
* 💰 Optimizing electricity pricing strategies
* ⚡ Efficient energy distribution
* 🚫 Preventing grid overload and power outages

---

## 🛠️ Tech Stack

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn
* SciPy
* Statsmodels

---

## 🚀 How to Run

```bash
# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn scipy statsmodels

# Run the notebook
jupyter notebook
```

---

## 📌 Conclusion

This project demonstrates a complete **end-to-end data science workflow**, from raw data preprocessing to advanced forecasting, making it highly relevant for real-world energy analytics and decision-making systems.

---
