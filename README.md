# 🌞 **Solar Radiation Prediction Dashboard – Week 3**

This repository contains the **Week-3 deliverable** of the Solar Energy Prediction project.
After cleaning the SolarPrediction dataset in earlier weeks and training ML models, this week focuses on:

✅ Building an **interactive Streamlit dashboard**
✅ Adding **EDA visualizations**
✅ Training **Random Forest & XGBoost**
✅ Hosting the dashboard online using **ngrok + Google Colab**

---

# 🚀 **Project Overview**

This project predicts **solar radiation (W/m²)** based on meteorological features from the *SolarPrediction* dataset.
The workflow includes:

* Dataset loading & sampling
* Feature selection & cleaning
* Model training (Random Forest & XGBoost)
* Saving the best model as `solar_model.pkl`
* Frontend UI built using Streamlit
* Deployment through ngrok
* Multi-tab dashboard with Prediction, EDA, and About sections

---

# 📊 **Features Used for Prediction**

The ML model predicts solar radiation using:

* 🌡️ **Temperature**
* 🌫️ **Pressure**
* 💧 **Humidity**
* 🧭 **Wind Direction**
* 💨 **Wind Speed**

These features were chosen based on Week-2 ML experiments that showed highest correlation with Radiation.

---

# 🧠 **Machine Learning Models**

Two models were trained and evaluated:

### 🟩 **Random Forest Regressor**

* Fast
* Stable
* Handles non-linearities well

### 🟦 **XGBoost Regressor**

* Boosted trees
* Strong generalization
* Excellent performance even with limited features

### 🔥 **Model Comparison**

| Model             | MAE    | R² Score | Notes                           |
| ----------------- | ------ | -------- | ------------------------------- |
| **Random Forest** | 101.57 | 0.70     | Best performer on small dataset |
| **XGBoost**       | 104.38 | 0.68     | Slightly lower accuracy         |

➡️ **Random Forest was selected as the final model** and saved as:

```
solar_model.pkl
```

---

# 📁 **Dataset**

To ensure fast dashboard loading, a smaller dataset was created:

```
solar_small.csv
```

This contains **35000 rows** randomly sampled from the cleaned dataset.

The large original dataset (SolarPrediction_cleaned.csv) was processed in earlier weeks.

---

# 🎨 **Streamlit Dashboard (Frontend)**

The dashboard contains **3 interactive tabs**:

---

## 🔮 **1. Prediction Tab**

Users input weather conditions:

* Temperature
* Pressure
* Humidity
* Wind Direction
* Wind Speed

The model instantly predicts:

### ⭐ **Solar Radiation in W/m²**

---

## 📊 **2. EDA Tab**

Includes:

* Sample dataset preview
* Radiation trend chart
* Heatmap (numeric columns only)
* Cleaned visualization without conversion errors

---

## ℹ️ **3. About Tab**

Displays project summary, features used, and author details.

---

# 🌐 **Deployment (Colab + ngrok)**

The dashboard runs live using:

```bash
!streamlit run app.py --server.port 8501 --server.address 0.0.0.0
```

ngrok is used to create a public URL:

```python
from pyngrok import ngrok
ngrok.connect(8501)
```

This gives a link like:

```
https://xyz.ngrok-free.app
```

Accessible from any browser.

---

# 📂 **Project Structure**

```
├── app.py                   # Streamlit dashboard
├── solar_small.csv          # Sample dataset
├── solar_model.pkl          # Trained ML model
├── notebook.ipynb           # Week-3 notebook (training + deployment)
└── README.md                # Documentation
```

---

# 🛠 **Technologies Used**

### 📦 Backend & ML

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* Joblib

### 🎨 Frontend

* Streamlit
* Seaborn
* Matplotlib

### ☁️ Deployment

* Google Colab
* ngrok

---

# 📌 **Conclusion**

This week’s implementation successfully integrates:

* 🔥 A trained ML model
* 💻 A full dashboard UI
* 📊 Visualization and analysis
* 🌍 Online hosting via ngrok


