EGIER Production Forecast & Warehouse Planning
This project models monthly production data (M1–M144) using Polynomial Regression and compares it with the Taylor Series approximation.
It also estimates when EGIER will need to start building a new warehouse, based on production forecasts and maximum warehouse capacity.

📊 Features
Loads 144 months of production data (2018–2029).
Fits a 3rd-degree polynomial regression model.
Uses Taylor Series approximation (which matches the polynomial model at degree 3).
Visualizes actual production vs. predicted production.
Calculates Mean Absolute Error (MAE) and Root Mean Square Error (RMSE).
Predicts when warehouse capacity will be exceeded and suggests when to start building.

🛠️ Tech Stack
Python 3.9+
pandas – data handling
numpy – numerical operations
matplotlib – visualization
scikit-learn – regression modeling & metrics

📈 Results
Polynomial Regression (Degree 3) fits production growth well.
Taylor approximation matches polynomial regression.
Model accuracy:
MAE: ~245
RMSE: ~288
