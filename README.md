# 🌫️ Delhi-NCR AQI Prediction

A machine learning project that predicts Air Quality Index (AQI)
for Delhi-NCR using pollutant and weather sensor readings.

---

## 📌 Problem Statement
The CPCB formula for AQI calculation has practical limitations —
sensor unavailability, no weather intelligence, and no predictive
capability. This project builds an ML regression model as a
flexible, data-driven alternative. At inference time, a user
provides sensor-like pollutant and weather readings, and the
model instantly outputs the predicted AQI.

---

## 📊 Dataset
- **Records:** 201,664 hourly readings (2020–2025)
- **Cities:** Delhi, Noida, Gurugram, Faridabad, Ghaziabad
- **Stations:** 23 monitoring stations
- **Features:** Pollutants (PM2.5, PM10, NO₂, SO₂, CO, O₃) +
  Weather (Temperature, Humidity, Wind Speed, Visibility)
- **Target:** AQI (range: 25–500)

---

## 🔍 Key EDA Findings
- Mean AQI **265.83** — Delhi-NCR averages Poor category
- **Severe** is the most common category (29.8%)
- **Winter (458)** is worst season, **Monsoon (83)** is best
- **November** averages AQI 500 — maximum cap
- **Visibility (-0.86)** is the strongest AQI predictor
- PM2.5 & PM10 are 0.99 correlated — always rise together

---

## ⚙️ Preprocessing & Feature Engineering
- Dropped 5 redundant columns (datetime, date,
  latitude, longitude, aqi_category)
- Outliers capped at 99th percentile (Winsorization)
- Encoded categorical columns (season, day_of_week,
  city, station)
- Added 5 engineered features:
  aqi_lag_1, aqi_lag_2, aqi_lag_3,
  aqi_rolling_mean_4, aqi_rolling_mean_8
- StandardScaler applied for feature scaling
- 80/20 train-test split
  (161,276 training / 40,319 testing samples)

---

## ⚠️ Known Limitations
The dataset contains 45,314 records (22.48%) where AQI is
capped at the maximum value of 500 by the CPCB formula.
This artificial ceiling means different levels of severe
pollution are indistinguishably mapped to the same target
value, potentially reducing model accuracy at extreme
pollution levels. This is an inherent limitation of the
data source rather than the modeling approach.

---

## 🛠️ Tech Stack
Python, Pandas, NumPy, Matplotlib, Seaborn,
Scikit-learn, XGBoost, Flask

---

## 📊 Model Results
*(To be updated after training)*

| Model | RMSE | MAE | R² |
|---|---|---|---|
| Linear Regression | - | - | - |
| Random Forest | - | - | - |
| XGBoost | - | - | - |
| **Best Model** | **-** | **-** | **-** |