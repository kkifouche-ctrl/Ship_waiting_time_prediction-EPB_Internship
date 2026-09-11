# 🚢 Ship Waiting Time Prediction at Anchorage

## 📌 Overview

This project was developed during my **internship at EPB (Entreprise Portuaire de Béjaïa)** and focuses on analyzing and predicting **ship waiting time at anchorage before berthing** using Machine Learning.

The goal is to explore how data-driven methods can help understand factors affecting waiting time and support future port planning and decision-making.

> **Data & Internship Note:**
> This project was developed during my internship at **EPB Béjaïa**. Due to company data confidentiality, access to real EPB operational data was not authorized. Therefore, a **fictitious/synthetic dataset** was used.
> The dataset represents a **fictitious Port of Algiers scenario** and does **not contain real Port of Algiers or EPB data**.
> The model is developed **for training and experimentation purposes only** and is **not intended for production or operational use at EPB**.

---

## 📊 Dataset

The dataset contains simulated information related to ships, port congestion, weather conditions, berthing, and waiting time.

The main target variable is:

**`Duree_en_rade_heures`** — Ship waiting time at anchorage, expressed in hours.

Example features include:

* Ship type
* Ship characteristics (GT, LOA, draft)
* Waiting reason
* Number of ships waiting at anchorage
* Port congestion index
* Weather conditions
* Assigned berth
* Arrival and date-related information

The dataset is **entirely synthetic** and was created for Machine Learning experimentation.

---

## 🧠 Methodology

The project follows a standard Machine Learning workflow:

1. Data preprocessing
2. Handling missing values
3. Categorical feature encoding
4. Feature scaling
5. Train/test splitting
6. Model training
7. Model comparison
8. Hyperparameter optimization
9. Final model evaluation
10. Feature importance analysis

### Preprocessing

The project uses:

* `SimpleImputer`
* `OneHotEncoder`
* `StandardScaler`
* `ColumnTransformer`
* `Pipeline`

### Validation & Optimization

* `TimeSeriesSplit`
* `RandomizedSearchCV`
* Hyperparameter optimization using 40 iterations
* Evaluation based primarily on **Mean Absolute Error (MAE)**

---

## 🤖 Machine Learning Models

Five regression models were evaluated:

* Random Forest Regressor
* Extra Trees Regressor
* Gradient Boosting Regressor
* XGBoost Regressor
* Optimized XGBoost Regressor

### Model Comparison

| Model                 |   MAE (h) |  RMSE (h) |        R² |   MAPE |
| --------------------- | --------: | --------: | --------: | -----: |
| **Gradient Boosting** | **38.76** |     61.72 |     0.542 | 41.36% |
| XGBoost Optimized     |     40.36 |     62.33 |     0.533 | 44.91% |
| Extra Trees           |     41.05 | **61.29** | **0.549** | 45.00% |
| XGBoost               |     44.23 |     64.17 |     0.505 | 54.53% |
| Random Forest         |     45.90 |     62.27 |     0.534 | 56.75% |

Based on the validation results, **Gradient Boosting** was selected as the final model.

---

## 📈 Final Model Performance

The final Gradient Boosting model achieved the following results on the test set:

| Metric   |          Result |
| -------- | --------------: |
| **MAE**  | **34.40 hours** |
| **RMSE** | **54.30 hours** |
| **R²**   |      **0.6748** |
| **MAPE** |      **33.23%** |

These results demonstrate the model's performance on the **synthetic test data**.

---

## 🔍 Feature Importance

Feature importance analysis was performed using the selected Gradient Boosting model to identify the variables that contribute most to the prediction of ship waiting time.

This provides an initial understanding of the factors influencing simulated anchorage waiting time.

---

## 🛠️ Technologies

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Scikit-learn**
* **XGBoost**
* **Joblib**
* **Jupyter Notebook / Google Colab**

---

## 🎯 Project Objective

The main objective is to demonstrate the application of **Data Science and Machine Learning** to a port-related operational problem:

> **Predicting the waiting time of ships at anchorage before berthing.**

Although the current model is based on synthetic data, the project provides a foundation for a future real-world solution if authorized and reliable operational data becomes available.

---


## ⚠️ Disclaimer

**This project is academic and experimental.**

The dataset is **fictitious** and does not represent real operational data from EPB Béjaïa or the Port of Algiers.

The model is intended **for learning, experimentation, and demonstration purposes only**. It must **not be used for production, operational decisions, or deployment at EPB** without real, authorized data and proper validation.
