🏠 **House Price Prediction using XGBoost**

A complete **House Price Prediction** project using the popular **House Price Prediction Dataset**.  
This project covers **EDA → Feature Engineering → Preprocessing → Model Training → Evaluation** — and includes a **reusable XGBoost regression pipeline**!  
Perfect for learning regression or applying in real-world housing scenarios.


🎯 **Project Goals**

- Understand structure & pattern in housing data  
- Preprocess and engineer useful features  
- Train an optimized XGBoost regression model  
- Analyze important predictors  
- Use interactive testing inside a Jupyter Notebook

---

 🏡 **Dataset Used**

**Dataset Name**: House Price Prediction Data  
**Source**: Kaggle / data.csv  
**Total Entries**: ~4600 records  
**Target Variable**: `price`


 🧾 **Features Included**

| Feature            | Description                                      |
|--------------------|--------------------------------------------------|
| bedrooms           | Number of bedrooms                               |
| bathrooms          | Number of bathrooms                              |
| sqft_living        | Interior square footage of the house             |
| sqft_lot           | Lot size in square feet                          |
| floors             | Number of floors                                 |
| waterfront         | Boolean if the property has a waterfront view    |
| view               | Rating of the view (0–4)                         |
| condition          | Overall condition (1–5)                          |
| sqft_above         | Square footage above ground                      |
| sqft_basement      | Square footage of the basement                   |
| city, statezip     | Location features                                |
| house_age          | Engineered feature: 2024 - `yr_built`            |
| was_renovated      | Engineered: 1 if renovated, else 0               |
| log_price          | Log-transformed price for model training         |

---

 📊 **Key EDA Results**

**Distributions:**
- `price` is **right-skewed** → log transformation applied  
- `sqft_living` shows strong range variation  

**Correlations:**
- `sqft_living` has the **strongest positive correlation** with price  
- `bedrooms`, `bathrooms`, and `city` are moderate contributors  
- Location (`city`, `statezip`) plays a **major role**

**Outliers:**
- Outliers in `price`, `sqft_living`, and `bedrooms` removed using IQR and quantile filtering

---

#🔬 **Model Used**

- **Model**: XGBoost Regressor (with regularization)
- **Hyperparameter Tuning**: GridSearchCV  
  - `n_estimators = 300`  
  - `max_depth = 4`  
  - `learning_rate = 0.1`  
  - `reg_alpha = 0.1`  
  - `subsample = 0.8`  

✅ Feature scaling & encoding handled through a `ColumnTransformer` pipeline inside the notebook.

---

 📈 **Final Results**

| Metric              | Value         |
|---------------------|---------------|
| MAE (Test Set)      | $53,531       |
| RMSE (Test Set)     | $76,352       |
| R² Score (Test Set) | 0.805         |
| CV R² (mean)        | 0.7997        |

🚀 Model performs very well and generalizes efficiently. Suitable for real-world prediction.

---

 📷 **Important Features Identified**

Top numerical contributors:
- `sqft_living`
- `bathrooms`
- `condition`
- `view`

Top categorical contributors:
- `city_Seattle`, `statezip_WA 98168`, etc. via OneHot encoding.

Note: City & Zip code dominated importance due to OneHotEncoded multiple columns.

---

 🧪 **Interactive UI (Notebook-based Test App)**

✅ Includes a Jupyter Notebook form using `ipywidgets` to test the model with custom values (like `bedrooms`, `sqft_living`, etc.) and get instant predictions right inside the notebook.

---

 🧰 **Tools & Libraries Used**

- 🐍 Python 3  
- 📘 Jupyter Notebook  
- 🧮 Pandas, NumPy  
- 📊 Matplotlib, Seaborn  
- 🧠 Scikit-Learn  
- 🚀 XGBoost  
- 🔧 ipywidgets (for in-notebook UI demo)

---

 📝 **License**

This project is open-source and available under the MIT License.

---

 🙋‍♂️ Author

**Tayyab Saeed**  
GitHub:@tayabsaeed

---

 ⭐️ If you found this helpful, give this repo a star!
