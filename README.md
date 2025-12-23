📈 Production Trend Analysis Using Polynomial Regression

This project analyzes long-term production trends using Polynomial Regression (degree 3) and applies the model to support warehouse capacity planning decisions.
The analysis is implemented in Python using scikit-learn, pandas, and matplotlib.

📌 Project Overview

Understanding production growth trends is essential for operational planning, especially when production capacity constraints such as warehouse storage limits exist.
This project models monthly production data over multiple years and estimates when production will exceed a predefined maximum warehouse capacity, enabling proactive infrastructure planning.

Key Objectives

Model historical production data using Polynomial Regression

Evaluate model accuracy using MAE and RMSE

Forecast future production trends

Determine the latest safe time to start building a new warehouse based on capacity constraints

🧠 Methodology
1. Dataset Description

Monthly production data from January 2018 onward

Total observations: 144 months

Each data point represents production volume for a given month

The dataset is indexed using a monthly datetime range, allowing time-based visualization and analysis.

2. Feature Engineering

Independent variable (X):
Sequential month index

𝑋
=
{
0
,
1
,
2
,
…
,
143
}
X={0,1,2,…,143}

Dependent variable (y):
Monthly production values

Polynomial feature expansion is applied to capture non-linear growth patterns:

𝑋
𝑝
𝑜
𝑙
𝑦
=
[
1
,
𝑥
,
𝑥
2
,
𝑥
3
]
X
poly
	​

=[1,x,x
2
,x
3
]
3. Polynomial Regression Model

A degree-3 polynomial regression is fitted using linear least squares:

𝑦
=
𝛽
0
+
𝛽
1
𝑥
+
𝛽
2
𝑥
2
+
𝛽
3
𝑥
3
y=β
0
	​

+β
1
	​

x+β
2
	​

x
2
+β
3
	​

x
3

This degree was chosen to:

Capture accelerating growth trends

Avoid excessive overfitting

Maintain interpretability for business decision-making

4. Taylor Series Interpretation

Since the regression model itself is a third-degree polynomial, its Taylor series expansion around 
𝑥
=
0
x=0 is mathematically identical to the fitted model.
This provides a useful analytical interpretation of production growth as a smooth polynomial function.

📊 Visualization

The project visualizes:

Actual production data over time

Polynomial regression predictions

Comparison between observed and modeled trends

This visual comparison helps assess model fit and trend behavior.

📐 Model Evaluation

The following error metrics are used to assess model performance:

Mean Absolute Error (MAE)

𝑀
𝐴
𝐸
=
1
𝑛
∑
𝑖
=
1
𝑛
∣
𝑦
𝑖
−
𝑦
^
𝑖
∣
MAE=
n
1
	​

i=1
∑
n
	​

∣y
i
	​

−
y
^
	​

i
	​

∣

Root Mean Square Error (RMSE)

𝑅
𝑀
𝑆
𝐸
=
1
𝑛
∑
𝑖
=
1
𝑛
(
𝑦
𝑖
−
𝑦
^
𝑖
)
2
RMSE=
n
1
	​

i=1
∑
n
	​

(y
i
	​

−
y
^
	​

i
	​

)
2
	​


Lower MAE and RMSE values indicate that the polynomial model closely follows the historical production trend.

🏭 Warehouse Capacity Planning
Problem Statement

Maximum warehouse capacity: 25,000 units

Construction lead time: 13 months

Approach

Identify the month when predicted production exceeds warehouse capacity

Subtract the construction lead time

Convert the resulting month index into a calendar date

Outcome

The analysis outputs the latest month when warehouse construction must begin to prevent capacity overflow.

🛠️ Technologies Used

Python

Pandas – data handling and time indexing

NumPy – numerical computation

Matplotlib – data visualization

Scikit-learn – polynomial regression and evaluation metrics

📂 Project Structure
production-trend-analysis/
│
├── production_trend_analysis.py
├── README.md
└── requirements.txt

▶️ How to Run the Project
1️⃣ Install Dependencies
pip install pandas numpy matplotlib scikit-learn

2️⃣ Run the Script
python production_trend_analysis.py


The script will:

Train the polynomial regression model

Plot production trends

Print MAE and RMSE

Output the recommended warehouse construction start date

⚠️ Limitations

Polynomial regression assumes smooth long-term trends and may not capture sudden shocks

No seasonality or external economic factors are modeled

Extrapolation far beyond the observed data range should be interpreted cautiously

🔮 Future Improvements

Incorporate time series models (ARIMA, SARIMA, Prophet)

Add confidence intervals for predictions

Perform model selection using cross-validation

Include seasonal and external variables

👤 Author

Owen Figo
Production Trend Analysis Project


📄 License

This project is intended for educational and analytical purposes.
Free to use and modify with appropriate attribution.
