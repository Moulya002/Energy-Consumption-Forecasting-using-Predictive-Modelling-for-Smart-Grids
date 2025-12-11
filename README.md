# ⚡ Energy Consumption Forecasting using Predictive Modeling  
### *20-year Smart Grid Energy Load Forecasting using Advanced Machine Learning*

## 📌 Overview  
This project builds a predictive modeling pipeline to forecast hourly **energy consumption** for a smart-grid facility using 20 years of historical load, weather, and operational data. It covers end-to-end data processing, feature engineering, exploratory analysis, modeling, and insights.  
LightGBM delivered the best performance with the lowest MAE/RMSE.

---

## 🎯 Objectives  
- Forecast hourly electric load using ML and deep learning models  
- Build a scalable data pipeline for merging multi-folder time-series data  
- Engineer time-based, weather-based, and trend-based features  
- Evaluate models using MAE, RMSE, and R²  
- Provide actionable recommendations for grid optimization

---

## 🗂️ Data Source  
- 20 years of hourly smart-grid energy data  
- Multiple distributed subfolders grouped by metric  
- Merged using custom functions: `merge_paths`, `data_merger`, `data_refiner`  
- Final dataset: **187,728 rows × 34 features**

---

## 🧹 Data Cleaning & Preparation  
- Combined all groups using outer joins on `Date`  
- Removed redundant & unclear columns (`Unnamed`, Cooling Load)  
- Standardized column names (e.g., `PV_Generation_kW`)  
- KNN Imputer (k=5) for missing values  
- Outlier capping using IQR (99th percentile)  
- Target variable defined as:  
  **TARGET_Total_Electric_Load_kW = Load_A + Load_B**

---

## 🧠 Feature Engineering  
- Time Features: Hour, Day, Month, Weekday  
- **Cyclical Encoding:** Sine/Cosine for hour and weekday  
- Weather Stress Indicators: Heating/Cooling Degree Days (HDD/CDD)  
- Lag Features: 1-hour and 24-hour lag  
- Rolling Window Stats: 24h & 48h rolling mean/std  
- Rate-of-change features  
- Holiday indicator  
- Removed features causing data leakage

---

## 🔍 Exploratory Data Analysis Highlights  
- Clear daily & weekly consumption patterns  
- Afternoon peaks driven by outdoor temperature  
- Total load is right-skewed with occasional demand spikes  
- Grid import strongly correlated with total load  
- Energy usage shows nonlinear seasonality

---

## 🤖 Models Evaluated  
- Linear Regression  
- Ridge Regression  
- Random Forest  
- XGBoost  
- LightGBM  
- HistGradientBoosting  
- AdaBoost  
- Artificial Neural Network (ANN)

### 📈 Best Model: **LightGBM**
**MAE:** 66.03  
**RMSE:** 94.33  
**R²:** 0.9691  
LightGBM achieved the highest accuracy, strongest generalization, and best handling of nonlinear patterns.

---

## 📊 Evaluation Metrics  
- **MAE** – Measures average prediction error  
- **RMSE** – Penalizes large errors  
- **R²** – Variance explained by the model  

MAE was emphasized because it gives direct, interpretable error in kW.

---

## 📌 Insights & Recommendations  
- Strong daily & weekly seasonal energy patterns  
- Afternoon peaks driven by high temperatures  
- Prior day's consumption strongly influences next-day load  
- **Recommendations:**  
  - Load shifting  
  - Predictive HVAC optimization  
  - Battery storage for peak shaving  

These strategies flatten the load curve, reduce costs, improve operational reliability, and support sustainability.

---

## 🚀 Deployment  
The model is deployed on Streamlit:  
🔗 https://energyconsumptiontimeseriesforecasting-hnshvkhbjnhr8zssvhwqvb.streamlit.app/

GitHub (team repo reference):  
🔗 https://github.com/cezanekarki/Energy-Consumption-Analysis.git

---

## 👥 Team   
- Bimala Joshi  
- Cezane Karki  
- **Moulya Reddygari Bhupal**  
- Amey Tillu

---

## 📬 Contact  
**Moulya Reddygari Bhupal**  
📧 Email: moulyarb02@gmail.com  
🔗 GitHub: https://github.com/Moulya002  
🔗 LinkedIn: https://www.linkedin.com/in/moulyarb/

