# 🚢 Project 1: Exploratory Data Analysis (EDA) — Titanic Dataset

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)

## 📌 Overview

This project performs an **Exploratory Data Analysis (EDA)** on the classic [Titanic dataset](https://github.com/datasciencedojo/datasets/blob/master/titanic.csv) to uncover patterns and insights about passenger survival. It covers the full EDA workflow — from data loading and cleaning through statistical analysis and visualization — alongside foundational Python and data science concepts.

---

## 📊 Dataset

| Property | Details |
|---|---|
| **Source** | [datasciencedojo/datasets](https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv) |
| **Records** | 891 passengers |
| **Features** | 12 columns (PassengerId, Survived, Pclass, Name, Sex, Age, SibSp, Parch, Ticket, Fare, Cabin, Embarked) |
| **Missing Values** | Age (177), Cabin (687), Embarked (2) |

---

## 🔍 EDA Workflow

### Step 1 — Import Libraries
Set up `pandas` for data handling and `matplotlib` for visualization.

### Step 2 — Load Dataset
Read the Titanic CSV directly from a public URL using `pd.read_csv()`.

### Step 3 — Understand the Data
Explored dataset shape (`891 rows × 12 columns`), data types via `df.info()`, and descriptive statistics via `df.describe()`.

### Step 4 — Handle Missing Values
- **Age**: Filled 177 missing values with the column mean
- **Embarked**: Filled 2 missing values with the mode

### Step 5 — Analysis
Counted survival outcomes across the passenger population.

### Step 6 — Visualizations
Generated three key charts:
- **Survival Count** — Bar chart of survived vs. did not survive
- **Gender vs. Survival Rate** — Grouped bar chart by sex
- **Age Distribution** — Histogram with 20 bins

---

## 📈 Key Findings

> - **Majority did not survive** — more passengers died than survived
> - **Females had a significantly higher survival rate** than males
> - **Most passengers were aged 20–40 years**
> - **Age and gender were strong predictors** of survival outcome

---

## 🐍 Python Concepts Practiced

Beyond EDA, this notebook also reinforces core Python and library fundamentals:

| Concept | What Was Covered |
|---|---|
| Variables & Data Types | Integers, floats, strings, operators |
| f-Strings | Formatted string output |
| Lists & Indexing | Positive and negative indexing |
| Conditional Statements | `if`, `elif`, `else`, nested conditions |
| Loops | `for` loops, `range()`, even/odd/reverse sequences, nested loops |
| String Methods | `.upper()`, `.lower()`, `.index()` |
| Functions | User-defined functions, parameters, return values |
| Modules | `math`, `datetime` standard library modules |
| **Matplotlib** | Line plots, scatter plots, bar charts, histograms, pie charts |
| **NumPy** | Array creation, random distributions, numerical operations |

---

## 🗂️ Project Structure

```
Project_1__EDA_/
│
├── Project_1__EDA_.ipynb   # Main Jupyter Notebook
└── README.md               # Project documentation
```

---

## ⚙️ Setup & Installation

### Prerequisites
- Python 3.x
- Jupyter Notebook or [Google Colab](https://colab.research.google.com/)

### Install Dependencies

```bash
pip install pandas matplotlib numpy
```

### Run the Notebook

```bash
jupyter notebook Project_1__EDA_.ipynb
```

> **Note:** No local dataset download needed — data is loaded directly from a URL at runtime.

---

## ⚠️ Known Issues

The following `FutureWarning` appears when filling missing values with `inplace=True` (deprecated in Pandas 3.0):

```
FutureWarning: A value is trying to be set on a copy of a DataFrame...
```

**Fix:** Replace with direct assignment:
```python
# Old (deprecated)
df["Age"].fillna(df["Age"].mean(), inplace=True)

# Recommended
df["Age"] = df["Age"].fillna(df["Age"].mean())
```

---

## 🛠️ Technologies Used

- **Python 3** — Core language
- **Pandas** — Data manipulation and analysis
- **Matplotlib** — Static data visualizations
- **NumPy** — Array operations and numerical computing
- **Jupyter Notebook** — Interactive development environment

---

## 👤 Author

Feel free to connect or reach out if you have feedback or questions!

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
