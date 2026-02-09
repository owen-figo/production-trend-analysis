# 📈 Production Trend Analysis Using Polynomial Regression

This project analyzes long-term **production trends** using **Polynomial Regression (degree 3)** and applies the model to support **warehouse capacity planning decisions**.  
The analysis is implemented in **Python** using `pandas`, `numpy`, `matplotlib`, and `scikit-learn`.

---

## 📌 Project Overview

Understanding production growth trends is critical for operational and infrastructure planning.  
This project models monthly production data over multiple years and estimates **when production will exceed a maximum warehouse capacity**, enabling proactive decision-making.

### Key Objectives
- Analyze historical production data
- Model non-linear growth using polynomial regression
- Evaluate model performance using MAE and RMSE
- Forecast future production trends
- Determine the latest safe time to start building a new warehouse

---

## 📊 Dataset Description

- Monthly production data starting from **January 2018**
- Total observations: **144 months**
- Each data point represents production volume for a given month

The dataset is indexed using a **monthly datetime range**, allowing time-based visualization and analysis.

---

## 🧠 Methodology

### 1. Feature Engineering

- **Independent Variable (X):**  
  Sequential month index  
X = {0, 1, 2, ..., 143}

markdown
Copy code

- **Dependent Variable (y):**  
Monthly production values

Polynomial feature expansion is applied to capture non-linear trends:
[1, x, x², x³]

yaml
Copy code

---

### 2. Polynomial Regression Model

A **degree-3 polynomial regression** model is fitted using linear regression:

y = β₀ + β₁x + β₂x² + β₃x³

yaml
Copy code

**Reason for choosing degree 3:**
- Captures accelerating growth trends
- Avoids excessive overfitting
- Remains interpretable for business and operations planning

---

### 3. Taylor Series Interpretation

Because the model is a third-degree polynomial, its **Taylor series expansion around x = 0** is mathematically identical to the regression model itself.  
This provides a smooth analytical approximation of production growth over time.

---

## 📈 Visualization

The model outputs:
- Actual production values
- Polynomial regression predictions
- Trend comparison over time

This visualization helps assess how well the regression model follows the historical data.

---

## 📐 Model Evaluation

The model is evaluated using:

### Mean Absolute Error (MAE)
MAE = (1/n) * Σ |yᵢ − ŷᵢ|

mathematica
Copy code

### Root Mean Square Error (RMSE)
RMSE = sqrt((1/n) * Σ (yᵢ − ŷᵢ)²)

yaml
Copy code

Lower values indicate better model performance.

---

## 🏭 Warehouse Capacity Planning

### Problem Definition
- **Maximum warehouse capacity:** 25,000 units
- **Construction lead time:** 13 months

### Approach
1. Predict future production using the regression model
2. Identify the month when predicted production exceeds capacity
3. Subtract the construction lead time
4. Convert the result into a calendar date

### Output
The script outputs the **recommended month to start building a new warehouse** to avoid exceeding storage capacity.


## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn



