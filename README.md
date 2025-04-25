# 💎 Diamond Price Analysis & Prediction Using Python

This project focuses on analyzing and predicting the prices of diamonds based on their physical and quality attributes using Python. By leveraging data visualization and machine learning techniques, we explore how features like carat, cut, and physical dimensions influence the price of a diamond.

## 📊 Project Overview

Diamonds are priced based on multiple factors beyond just their size. This project walks through a data-driven approach to:

- Analyze relationships between diamond attributes and price.
- Visualize trends across cut, color, and clarity.
- Predict diamond prices using machine learning models.

## 📁 Dataset

The dataset is sourced from [Kaggle](https://www.kaggle.com/datasets/shivam2503/diamonds), and contains ~54,000 records with features like:

- `carat`: Weight of the diamond
- `cut`: Quality of the cut (Ideal, Premium, Good, etc.)
- `color`: Diamond color (from D best to J worst)
- `clarity`: Clarity grading
- `depth`, `table`: Proportions of the diamond
- `price`: Price in USD
- `x`, `y`, `z`: Dimensions in mm

## 🧪 Key Steps

### 1. Data Preprocessing
- Removed unnecessary `Unnamed: 0` column.
- Calculated a new `size` (actually volume) feature:  
  \[
  \text{size} = x \times y \times z
  \]

### 2. Data Visualization
- Used `plotly.express` to explore:
  - Carat vs Price
  - Size vs Price
  - Price distribution by `cut`, `color`, and `clarity`
- Applied `trendline='ols'` for linear regression overlays.

### 3. Feature Engineering
- Mapped categorical values of `cut` to numeric for model training:
  ```python
  {"Ideal": 1, "Premium": 2, "Very Good": 3, "Good": 4, "Fair": 5}
  ```

### 4. Model Building
- Split data into train/test sets.
- Used **RandomForestRegressor** to predict diamond prices.
- Input: `carat`, `cut (numeric)`, and `size`
- Output: Predicted `price`

## 🔍 Example Prediction

```python
Carat Size: 0.60
Cut Type: Premium (2)
Size: 40

→ Predicted Diamond's Price = $937.13
```

## 📈 Insights

- Strong correlation between **carat**, **size**, and **price**.
- **Premium cut** diamonds tend to have larger sizes and higher prices.
- `carat` and `size` are top predictors of price, while `depth` has minimal impact.

## 🔧 Tech Stack

- **Python**
- **Pandas**, **NumPy**
- **Plotly Express** for interactive plots
- **Scikit-learn** for model training and evaluation

## 🧠 Author

Based on a tutorial by [Aman Kharwal](https://thecleverprogrammer.com/2022/09/26/diamond-price-analysis-using-python/). Replicated and customized by *[Your Name]*.
