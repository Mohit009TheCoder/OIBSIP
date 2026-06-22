# Task 3: Car Price Prediction with Machine Learning

This repository contains a machine learning pipeline to predict the selling price of used cars based on their features (brand, age, mileage, engine power, fuel type, transmission, etc.). 

## Project Highlights
- **Tech Stack**: Python, `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `scipy`
- **Analytics Rigor**: Detailed column-by-column exploratory data analysis (EDA), normality checks (Q-Q plots), jointplots, Boxen/Violin plots, depreciation curves, and Variance Inflation Factor (VIF) multicollinearity diagnostics.
- **Data Engineering**: Regex parsers to clean numerical units (`mileage`, `engine`, `max_power`) and standardise complex torque entries (e.g. `250Nm@ 1500-2500rpm` or `12.7@ 2,700(kgm@ rpm)`) to standard SI units (`Nm` and `RPM`).
- **Modeling**: Evaluated Ridge Regression, Random Forest, and Gradient Boosting Regressors using 5-Fold Cross Validation.
- **Top Performer**: **Random Forest Regressor** achieved a **93.08% Test R² score** with a median prediction error of **~12.4%** across all tiers.

---

## Dataset Description
The model uses the **Vehicle Dataset from Cardekho (v3)** containing 8,128 original rows. After cleaning and duplicate removal, **6,926 rows** were used:
- `selling_price`: Target variable (Log-transformed for stabilization).
- `car_age`: Years since manufacture (`2026 - year`).
- `brand_segment`: Categorized brand tier (`Luxury`, `Premium`, `Economy`).
- `km_driven`: Total distance driven.
- `mileage`: Fuel efficiency (kmpl).
- `engine`: Engine displacement (CC).
- `max_power`: Horsepower (BHP).
- `torque_Nm` / `torque_rpm`: Engine peak torque (Nm) and the RPM at which it is reached.
- `fuel` / `seller_type` / `transmission` / `owner` / `seats`: Categorical specifications.

---

## Model Evaluation Results

Models were trained on an 80/20 train/test split. Numeric variables were scaled (`StandardScaler`) and categorical features encoded (`OneHotEncoder`) within a leakage-free `Pipeline`.

| Model | 5-Fold CV R² | CV R² Std | Test MAE (INR) | Test RMSE (INR) | Test R² Score |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Random Forest Regressor** | **91.18%** | **0.87%** | **72,036.32** | **123,159.12** | **93.08%** |
| **Gradient Boosting Regressor** | 91.14% | 0.82% | 73,719.82 | 131,093.45 | 92.16% |
| **Ridge Regression (Baseline)** | 88.21% | 1.45% | 90,285.46 | 161,749.72 | 88.07% |

---

## Performance Diagnostics & Key Insights
1. **Primary Predictors**: Feature importances show that `max_power` (engine output) is the most dominant factor in used car pricing, followed closely by `car_age` (depreciation) and `brand_segment` flags.
2. **Acceptable Multicollinearity**: Multicollinearity was checked via the Variance Inflation Factor (VIF). All independent variables had VIF scores under 5 (e.g. `engine` at `4.84` and `max_power` at `2.81`), confirming that coefficients are stable.
3. **Segmented Calibration**: Segmented error analysis reveals that median percentage prediction error is exceptionally low across all tiers: **11.9%** for Premium, **12.4%** for Economy, and **15.8%** for Luxury.

---

## File Structure
- `car_price_prediction.ipynb`: Pre-rendered Jupyter Notebook containing data cleaning, advanced visualizations, VIF check, modeling, diagnostics, and conclusion.
- `car_details_v3.csv`: Local dataset.
- `README.md`: This summary sheet.

---

## How to Run

1. Clone or navigate to this folder.
2. Install the requirements:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn scipy notebook
   ```
3. Launch the Jupyter Notebook environment:
   ```bash
   jupyter notebook
   ```
4. Open and run all cells in `car_price_prediction.ipynb` to view interactive plots and train/test the models.
