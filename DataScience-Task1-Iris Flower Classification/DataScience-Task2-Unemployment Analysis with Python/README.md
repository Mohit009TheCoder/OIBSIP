# Unemployment Analysis with Python

This repository contains the implementation of a Python-based Exploratory Data Analysis (EDA) on unemployment rates in India, with a specific focus on the severe economic impact of the COVID-19 pandemic.

## Objective
Analyze unemployment data in India during the year 2020 to uncover regional and temporal trends, investigate correlation between key labor metrics, and contrast the pre-COVID era with the post-COVID era.

## Tech Stack
- **Python**
- **SciPy** (Statistical Analysis)
- **Pandas & NumPy** (Data Preprocessing and Aggregation)
- **Matplotlib & Seaborn** (Data Visualization)
- **Jupyter Notebook**

---

## Project Structure and Workflow

The analysis is structured inside a clean, commented Jupyter Notebook:
- [unemployment_analysis.ipynb](unemployment_analysis.ipynb)

### 1. Data Preprocessing & Cleaning
- Cleaned leading/trailing whitespaces in column names.
- Renamed duplicate zone columns.
- Converted date strings into pandas datetime objects.
- Added Month helper fields.

### 2. Exploratory Data Analysis (EDA)
- Analyzed regional average unemployment rates.
- Sorted top 10 states by average unemployment rate.

### 3. Core Visualizations
- **Time-Series Line Chart**: Analyzes monthly trend for selected states (Haryana, Maharashtra, Delhi).
- **Top 10 States Bar Chart**: Highlights regions with the highest average monthly unemployment rate.
- **Correlation Heatmap**: Explores interactions between Unemployment Rate, Employed Count, and Labour Participation Rate.

### 4. COVID-19 Impact Analysis (Pre vs. Post COVID)
- Defined Pre-COVID as Jan-Mar 2020 and Post-COVID as Apr-Nov 2020.
- State-by-state grouped comparison bar chart showing the shift in average unemployment rate post-lockdown.

### 5. Advanced Visualizations & Statistical Analytics
- **State-Month Heatmap**: Visualizes the month-wise progression of unemployment rate across all states in a dense matrix.
- **Geospatial Bubble Plot**: Uses latitude/longitude columns to map the geographic spread and severity of unemployment during the lockdown peak (April 2020).
- **Statistical Analytics (T-Test)**: Formally compared pre-COVID vs. post-COVID groups using an independent t-test (`scipy.stats.ttest_ind`), yielding a statistically significant difference (p < 0.05).

---

## Datasets
The notebook relies on:
- `Unemployment_Rate_upto_11_2020.csv` (contains geographic variables: latitude, longitude, zone, and state metrics).
- `Unemployment in India.csv` (contains rural/urban split metrics).

---

## How to Run the Notebook

1. Ensure the dataset CSVs are present in the directory.
2. Install dependencies:
   ```bash
   pip install numpy pandas matplotlib seaborn scipy notebook
   ```
3. Launch Jupyter:
   ```bash
   jupyter notebook
   ```
4. Run all cells in [unemployment_analysis.ipynb](unemployment_analysis.ipynb).
