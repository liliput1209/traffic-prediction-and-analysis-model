

# 🚦 Traffic Data Analysis and Prediction Using Asroga and Bara Toll Plaza Data

## 📌 Project Overview

This project focuses on analyzing and predicting traffic vehicle distribution using real-world data collected from two toll plazas: **Asroga** and **Bara**. The goal is to forecast the count of different vehicle types based on features such as total vehicle volume, date, month, and day of the week. Accurate traffic prediction supports better planning, toll management, and congestion mitigation.

Two machine learning models — **Random Forest Regressor** and **XGBoost Regressor** — were employed. Bayesian optimization using **Optuna** was applied to fine-tune hyperparameters for better accuracy.

---

## 🧠 Methodology

* **Dataset:** Traffic vehicle data categorized by vehicle type, date, location (Asroga or Bara), and total count.
* **Feature Engineering:**

  * Extracted `Month` and `DayOfWeek` from the `Date` column.
  * Used `Total Vehicles`, `Month`, and `DayOfWeek` as input features.
* **Target Variables:**

  * Car/Jeep/Van
  * Light Commercial Vehicle
  * 2-Axle Trucks
  * 3-Axle Trucks
  * Multi-Axle (HCM/EME) Vehicles
  * Oversized Vehicles (7+ axles)
* **Models Used:**

  * Random Forest Regressor (multi-output)
  * XGBoost Regressor (multi-output)
* **Optimization:**

  * Bayesian tuning with Optuna for selecting best model parameters
* **Evaluation Metrics:**

  * R² Score
  * Mean Absolute Error (MAE)

---

## 📊 Results Summary

After training and testing both models on the data from Asroga and Bara Toll Plazas:

* **Random Forest** consistently achieved **higher R² scores** and **lower MAE** compared to XGBoost, indicating better generalization and predictive accuracy for this dataset.
* Predicted vehicle counts showed similar trends to actual values but had some variance for less frequent vehicle categories like oversized vehicles or multi-axle machinery.

---

## ⚠️ Limitations

Despite the promising results, there are several limitations that impacted model performance:

1. **Data Size and Quality:**

   * Limited number of samples, especially for rare vehicle categories, led to skewed learning.
   * Missing or inconsistent entries may have introduced noise.

2. **Feature Simplicity:**

   * Only basic temporal features (`Month`, `DayOfWeek`) were used.
   * Additional external factors like weather, holidays, or local events could significantly improve model performance but were not included.

3. **Station-Specific Models:**

   * The models were trained separately for Asroga and Bara, which may not generalize well across different toll plazas with different traffic dynamics.

4. **No Time-Series Modeling:**

   * This project used static regression models instead of time-series approaches like ARIMA, LSTM, or Prophet, which may better capture temporal trends and seasonal effects.

---

## ✅ Future Improvements

* Incorporate **external variables** such as weather data, accident reports, and road conditions.
* Use **time-series forecasting models** to account for traffic seasonality and temporal dependencies.
* Expand the dataset to include more locations and a wider time range for improved generalization.
* Build a **live web application** for real-time traffic prediction and visualization.

---

