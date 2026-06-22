# Iris Flower Classification

This repository contains the implementation of a Machine Learning classification model to identify the species of an Iris flower based on its physical measurements.

## Objective
Train a classifier using the physical dimensions (sepal length, sepal width, petal length, petal width) of an iris flower to classify it into one of three species:
- **Setosa**
- **Versicolor**
- **Virginica**

## Tech Stack
- **Python**
- **Scikit-learn** (Machine Learning library)
- **Pandas & NumPy** (Data Manipulation)
- **Matplotlib & Seaborn** (Data Visualization)
- **Jupyter Notebook**

---

## Project Structure and Workflow

The pipeline is implemented inside a clean, commented Jupyter Notebook:
- [iris_classification.ipynb](iris_classification.ipynb)

### 1. Exploratory Data Analysis (EDA)
- Analyzed dataset shape (150 samples, 4 features + targets).
- Verified data types (`float64` for feature columns).
- Performed a null value check (0 missing values).
- Calculated descriptive statistics (mean, standard deviation, min, max, percentiles).

### 2. Advanced Data Visualization
- **Pairplot**: Pairwise feature distributions categorized by species.
- **Box plots & Violin plots**: Probability density and spread of features per species.
- **Correlation Heatmap**: Annotated Pearson correlation coefficients between features.
- **PCA 2D Projection**: Dimensionally reduced visualization showing global cluster separations.

### 3. Feature Selection Discussion
- Visualizations show that **Petal Length** and **Petal Width** are highly discriminative.
- **Setosa** is linearly separable using only petal dimensions.
- **Versicolor** and **Virginica** are also well-separated with minor overlap.

### 4. Model Training & Testing
- Split data 80% training / 20% testing using stratified sampling.
- Trained three classifiers:
  1. **Logistic Regression** (Accuracy: `96.67%`)
  2. **K-Nearest Neighbors (KNN)** (Accuracy: `100.00%`)
  3. **Random Forest Classifier** (Accuracy: `90.00%`)

### 5. Evaluation
- Evaluated models using **Accuracy score**, **Classification Report (Precision, Recall, F1)**, and **Confusion Matrices**.
- Declared **K-Nearest Neighbors (KNN)** as the best-performing model due to perfect accuracy and simplicity/generalization on this dataset size.

---

## How to Run the Notebook

1. Clone or download this repository.
2. Install the required dependencies:
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn notebook
   ```
3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
4. Open and run all cells in [iris_classification.ipynb](iris_classification.ipynb).
