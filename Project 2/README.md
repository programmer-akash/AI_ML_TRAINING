# 🏠 House Price Prediction — Linear Regression

A supervised machine learning project that predicts California house prices using Linear Regression, built with Python and scikit-learn.

---

## 📌 Project Overview

This project trains a **Linear Regression** model on the **California Housing Dataset** (built into scikit-learn) to predict median house values based on demographic and geographic features. The workflow covers a complete 14-step ML pipeline — from data loading and EDA through model training, evaluation, feature importance analysis, log-transform improvement, and saving predictions to CSV.

---

## 🎯 Objective

> Train a Linear Regression model that accurately predicts California house prices based on features such as median income, house age, number of rooms, population, and geographic location.

---

## 📂 Repository Structure

```
├── Project_2.ipynb                  # Main Jupyter Notebook — full ML pipeline
├── house_price_prediction.csv       # Saved prediction results (Actual vs Predicted)
└── README.md
```

---

## 📊 Dataset

| Property | Details |
|---|---|
| **Source** | `sklearn.datasets.fetch_california_housing` |
| **Samples** | 20,640 |
| **Features** | 8 input features |
| **Target** | Median house value (in $100,000s) |
| **Missing Values** | None — clean dataset |

**Features:**

| Feature | Description |
|---|---|
| `MedInc` | Median income in block group |
| `HouseAge` | Median house age in block group |
| `AveRooms` | Average number of rooms per household |
| `AveBedrms` | Average number of bedrooms per household |
| `Population` | Block group population |
| `AveOccup` | Average number of household members |
| `Latitude` | Block group latitude |
| `Longitude` | Block group longitude |

---

## 🔧 Tech Stack

- **Language:** Python 3
- **Environment:** Google Colab / Jupyter Notebook
- **Libraries:**
  - `NumPy` — numerical operations
  - `Pandas` — data manipulation
  - `Matplotlib` — data visualization
  - `Scikit-learn` — model training & evaluation

---

## 🧪 Project Workflow

The notebook follows a structured 14-step ML pipeline:

1. **Import Libraries** — NumPy, Pandas, Matplotlib, Scikit-Learn
2. **Load Dataset** — via `fetch_california_housing()`, no download required
3. **Data Understanding** — `df.shape`, `df.info()`, `df.describe()`
4. **Check Missing Values** — `df.isnull().sum()` — zero missing values found
5. **Feature & Target Split** — `X` (8 features) and `y` (Price)
6. **Train/Test Split** — 80/20 with `random_state=42`
7. **Train Linear Regression Model** — `LinearRegression().fit(X_train, y_train)`
8. **Make Predictions** — `model.predict(X_test)`
9. **Evaluate Model** — RMSE and R² Score
10. **Visualization** — Actual vs Predicted scatter plot
11. **Residual Plot** — Error analysis (Predicted vs Residuals)
12. **Feature Importance** — Coefficient analysis per feature
13. **Model Improvement** — Log transformation on target variable (`np.log1p`)
14. **Save Results** — Export predictions to `house_price_prediction.csv`

---

## 📈 Sample Output

**Dataset preview (`df.head()`):**

```
   MedInc  HouseAge  AveRooms  AveBedrms  Population  AveOccup  Latitude  Longitude  Price
0  8.3252      41.0  6.984127   1.023810       322.0  2.555556     37.88    -122.23  4.526
1  8.3014      21.0  6.238137   0.971880      2401.0  2.109842     37.86    -122.22  3.585
2  7.2574      52.0  8.288136   1.073446       496.0  2.802260     37.85    -122.24  3.521
3  5.6431      52.0  5.817352   1.073059       558.0  2.547945     37.85    -122.25  3.413
4  3.8462      52.0  6.281853   1.081081       565.0  2.181467     37.85    -122.25  3.422
```

**Train/Test Split:**

```
Training set: (16512, 8) (16512,)
Testing set:  (4128, 8)  (4128,)
```

**Model Evaluation:**

```
Model Evaluation Results
RMSE:     0.7455813830127764
R2 Score: 0.5757877060324508
```

**After Log Transform (Feature Engineering):**

```
After Log transform
RMSE:     0.22436602177852213
R2 Score: 0.600615972280346
```

---

## 📉 Model Performance

| Metric | Baseline Model | After Log Transform |
|---|---|---|
| **RMSE** | 0.7456 | **0.2244** ✅ |
| **R² Score** | 0.5758 | **0.6006** ✅ |

> Log-transforming the target variable (`np.log1p(y)`) reduced skewness and cut RMSE by ~70%, improving overall model fit.

---

## 🔍 Feature Importance (Coefficients)

| Feature | Coefficient | Impact |
|---|---|---|
| `AveBedrms` | +0.7831 | ⬆️ Increases price |
| `MedInc` | +0.4487 | ⬆️ Increases price |
| `HouseAge` | +0.0097 | Minor positive effect |
| `Population` | -0.0000 | Negligible |
| `AveOccup` | -0.0035 | Minor negative effect |
| `AveRooms` | -0.1233 | ⬇️ Decreases price |
| `Latitude` | -0.4198 | ⬇️ Decreases price |
| `Longitude` | -0.4337 | ⬇️ Decreases price |

> **Positive coefficient** → feature increases predicted price. **Negative coefficient** → feature decreases predicted price.

---

## 💡 Key Insights

- **`MedInc` (Median Income)** is the strongest positive predictor of house price
- **Geographic coordinates** (`Latitude`, `Longitude`) carry significant weight — location strongly affects price
- **Baseline Linear Regression** achieved R² of 0.576 — reasonable but improvable
- **Log-transforming** the target variable improved R² to 0.601 and cut RMSE by ~70%
- The dataset had **zero missing values**, making preprocessing straightforward

---

## 🔍 Key Concepts Used

- **Linear Regression** — supervised regression using `sklearn.linear_model`
- **Train-Test Split** — `train_test_split` with 80/20 ratio and `random_state=42`
- **Model Evaluation** — RMSE (lower = better) and R² score (closer to 1 = better)
- **Feature Importance** — extracting and ranking `model.coef_` values
- **Feature Engineering** — `np.log1p()` log transform to reduce target skewness
- **Residual Analysis** — plotting errors to detect systematic bias
- **DataFrame operations** — `df.drop()`, `df.groupby()`, `df.isnull()`
- **CSV Export** — saving predictions with `df.to_csv()`

---

## 🚀 Getting Started

### Run Locally

```bash
# Clone the repository
git clone https://github.com/your-username/house-price-prediction.git
cd house-price-prediction

# Install dependencies
pip install numpy pandas matplotlib scikit-learn jupyter

# Launch the notebook
jupyter notebook Project_2.ipynb
```

### Run on Google Colab

Click the badge below to open directly in Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

> No dataset download needed — the California Housing dataset loads automatically via `sklearn.datasets`.

---

## 📋 Requirements

```
numpy
pandas
matplotlib
scikit-learn
```

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you'd like to change.

---

## 👤 Author

**AKASH HALDER**
- GitHub: [@programmer-akash](https://github.com/programmer-akash)
- LinkedIn: [coder-akash-halder](https://www.linkedin.com/in/coder-akash-halder/)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

*Built with ❤️ using Python & scikit-learn*
