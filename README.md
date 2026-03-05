# 🏙️ NYC Housing Price Prediction (2009 to 2024), Inflation Adjusted ML

A full MSc Applied Data Science dissertation project (Royal Holloway, University of London) focused on predicting **inflation adjusted residential sale prices** across the **five boroughs of New York City** using **1.5M+ property transactions from 2009 to 2024**.

Most housing price projects model **nominal prices**, which can cause models to learn inflation rather than real market behaviour. In this project, every transaction is converted into **real 2024 dollars** using CPI adjustment, making the modelling task economically meaningful across a long time horizon.

---

## ⭐ What makes this project strong
- **Scale:** 1.5M+ NYC transactions across 15 years
- **Real world data:** messy municipal data cleaned and validated (missing values, inconsistencies, invalid sales, outliers)
- **Inflation adjustment:** prices converted into **2024 real terms** using CPI (World Bank)
- **Feature engineering:** 22 engineered features (structural, temporal, ratios, encoded categories)
- **Broad model benchmarking:** linear, ensemble, deep learning
- **From scratch models:** selected algorithms implemented using **NumPy and linear algebra** to compare against library versions
- **Hybrid ensemble:** averaged predictions from **XGBoost + Random Forest + Histogram Gradient Boosting**
- **Evaluation:** MAE, RMSE, R², compared **per borough** to capture market heterogeneity

---

## 🗺️ Borough coverage
- Bronx  
- Brooklyn  
- Manhattan  
- Queens  
- Staten Island  

---

## 📦 Data sources
- **NYC Rolling Sales Data:** New York City Department of Finance  
- **Inflation (CPI):** World Bank, used to convert all sale prices into **real 2024 dollars**  

Both sources are referenced inside the dissertation report.

---

## 🧠 What I built

### 1) Data pipeline
- Consolidated borough and yearly NYC sales files into borough level panels (2009 to 2024)
- Cleaned and validated transactions to remove invalid sales and non market records
- Engineered features to capture property structure and market timing
- Applied CPI adjustment to remove inflation distortion and standardise prices to 2024

### 2) Feature engineering
Examples of engineered features include:
- Property age and time features (sale year, month, day)
- Unit totals
- Price per square foot
- Density and ratio measures (land per unit, FAR)
- Encoded categorical features and log transforms for skewed distributions

Final modelling schema: **22 engineered features** per borough dataset.

### 3) Modelling and evaluation
Models were trained and tested **per borough**, then compared using:
- **MAE** (typical error)
- **RMSE** (penalises large errors)
- **R²** (explained variance)

---

## 🤖 Models included

### Linear and regularised
- Linear Regression (OLS)
- Ridge Regression (library and from scratch)
- LASSO Regression
- Huber Regression

### Instance based
- KNN (includes from scratch work)

### Tree based ensembles
- Random Forest
- XGBoost
- Histogram Gradient Boosting

### Deep learning
- MLP
- LSTM
- Deep and Cross Network (DCN)

### Hybrid
- Simple averaging ensemble (XGBoost + Random Forest + Histogram Gradient Boosting)

---

## 🔥 Key takeaway
Tree based ensemble models consistently performed best across most boroughs.  
**Manhattan was the hardest borough to model** due to extreme price variance and luxury outliers, leading to higher residual error across all model families.

---

## 📁 Repo layout
Each borough is organised as a separate notebook:

- `bronx.ipynb`  
- `brooklyn.ipynb`  
- `manhattan.ipynb`  
- `queens.ipynb`  
- `staten_island.ipynb`  

---

## 🚀 How to run
Install dependencies:
```bash
pip install pandas numpy scikit-learn xgboost matplotlib seaborn tensorflow jupyter
