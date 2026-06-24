<h1 align="center">📈 Polynomial Regression — Salary Prediction</h1>

<p align="center">
  <i>Predicting salaries from job seniority levels using a non-linear Polynomial Regression model.</i>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter" />
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="scikit-learn" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy" />
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white" alt="Matplotlib" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="License" />
  <img src="https://img.shields.io/badge/Status-Completed-success?style=flat-square" alt="Status" />
  <img src="https://img.shields.io/badge/Model-Polynomial%20Regression-blueviolet?style=flat-square" alt="Model" />
</p>

---

## 🎯 About the Project

> **Goal:** Build a model that predicts the **salary** an employee should earn based on their **position level**, capturing the *non-linear* relationship between the two.

In real-world compensation data, salary rarely grows in a straight line as seniority increases — it tends to **accelerate** at higher levels. A simple **Linear Regression** model fails to capture this curvature and produces large prediction errors.

This project demonstrates why **Polynomial Regression** is the right tool for the job:

- 🔹 It extends Linear Regression by adding **higher-degree features** (`Level²`, `Level³`, …).
- 🔹 This lets the model **bend** to fit the curved trend in the data.
- 🔹 We **visually compare** the Linear and Polynomial fits to make the difference obvious.

The notebook walks through the full workflow: loading the data, fitting both models, plotting their decision curves side by side, and predicting the salary for a new seniority level.

---

## 📊 Dataset

The dataset (`Position_Salaries.csv`) contains **10 records** mapping job titles to their seniority level and corresponding salary.

| Column     | Type        | Description                                            |
| :--------- | :---------- | :----------------------------------------------------- |
| `Position` | Categorical | The job title (e.g., *Business Analyst*, *Manager*).   |
| `Level`    | Numerical   | The numeric seniority level (1–10).                    |
| `Salary`   | Numerical   | The annual salary in USD — the **target** variable.    |

### 🔍 A Note on Feature Selection

> The **`Position`** column is **intentionally excluded** from the model.
>
> Each position title maps one-to-one onto a `Level` value — both columns encode the *same hierarchical information*. Keeping `Position` would be redundant, so only **`Level`** is used as the independent variable (**X**), and **`Salary`** is the dependent variable (**y**).

#### Sample of the data:

| Position           | Level | Salary    |
| :----------------- | :---: | --------: |
| Business Analyst   |   1   |   45,000  |
| Senior Consultant  |   3   |   60,000  |
| Region Manager     |   6   |  150,000  |
| Senior Partner     |   8   |  300,000  |
| CEO                |  10   | 1,000,000 |

---

## 🛠️ Technologies Used

| Library            | Role in the Project                                      |
| :----------------- | :------------------------------------------------------- |
| 🐍 **Python**      | Core programming language.                               |
| 🐼 **Pandas**      | Loading and handling the dataset.                        |
| 🔢 **NumPy**       | Numerical operations and array manipulation.             |
| 📉 **Matplotlib**  | Visualizing the Linear vs. Polynomial regression curves. |
| 🤖 **Scikit-Learn**| Building the regression models (`LinearRegression`, `PolynomialFeatures`). |

---

## 🚀 How to Run

Follow these steps to run the project locally.

**1. Clone the repository**

```bash
git clone https://github.com/<your-username>/polynomial_regression.git
cd polynomial_regression
```

**2. (Recommended) Create and activate a virtual environment**

```bash
# Create the environment
python -m venv venv

# Activate it (Windows)
venv\Scripts\activate

# Activate it (macOS / Linux)
source venv/bin/activate
```

**3. Install the required dependencies**

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
```

**4. Launch the notebook**

```bash
jupyter notebook polynomial_regression.ipynb
```

> 💡 Run the cells from top to bottom to reproduce the data loading, model training, visualizations, and final salary prediction.

---

## ✅ Conclusion

> **Polynomial Regression clearly outperforms Linear Regression on this non-linear dataset.**

The visual comparison tells the whole story:

- 📏 The **Linear** model draws a single straight line that badly under-fits the data — overestimating low levels and severely underestimating high ones.
- 🎯 The **Polynomial** model bends smoothly along the data points, tracking the steep salary growth at senior levels with high accuracy.

This project is a practical reminder of a key machine learning principle: **the model must match the shape of the data**. When the underlying relationship is curved, adding polynomial features is a simple yet powerful way to achieve a far more accurate fit. 🚀

---

<p align="center">
  <i>⭐ If you found this project helpful, consider giving it a star!</i>
</p>
