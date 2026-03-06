# 🏠 House Price Prediction

A machine learning project that predicts residential house prices using **Linear Regression**. The model is trained on a dataset of 2,000 houses with various features such as area, number of bedrooms, location, and more.

---

## 📁 Project Structure

```
House Price Prediction/
├── Linear Regression.ipynb          # Jupyter notebook with full analysis & model
└── House Price Prediction Dataset.csv  # Dataset used for training and testing
```

---

## 📊 Dataset

The dataset contains **2,000 records** with the following features:

| Column      | Type    | Description                              |
|-------------|---------|------------------------------------------|
| `Id`        | int     | Unique identifier for each house         |
| `Area`      | int     | Total area in square feet (501–4999)     |
| `Bedrooms`  | int     | Number of bedrooms (1–5)                 |
| `Bathrooms` | int     | Number of bathrooms (1–4)                |
| `Floors`    | int     | Number of floors (1–3)                   |
| `YearBuilt` | int     | Year the house was built (1900–2023)     |
| `Location`  | object  | Location type: Downtown, Suburban, Urban, Rural |
| `Condition` | object  | House condition: Excellent, Good, Fair, Poor |
| `Garage`    | object  | Garage availability: Yes / No            |
| `Price`     | int     | **Target variable** — sale price in USD  |

**Price range:** \$50,005 – \$999,656 | **Mean price:** ~\$537,677

---

## 🔧 Methodology

### 1. Data Exploration
- Loaded and inspected the dataset using `df.head()`, `df.info()`, and `df.describe()`
- Verified no null values across all 2,000 entries

### 2. Preprocessing
- Encoded categorical columns (`Location`, `Condition`, `Garage`) using **one-hot encoding** (`pd.get_dummies` with `drop_first=True`)

### 3. Feature Engineering
- **Features (X):** All columns except `Price` and `Id`
- **Target (y):** `Price`

### 4. Model Training
- Split data: **80% training / 20% testing** (`random_state=42`)
- Trained a **scikit-learn `LinearRegression`** model

### 5. Evaluation
- **R² Score:** ~0.938 (93.8%)

> **Note:** The dataset has been specifically engineered to exhibit strong, realistic linear correlations between features (like area, bedrooms, bathrooms) and the house price. This allows the lightweight `LinearRegression` model to achieve excellent accuracy (>90% R²) without overfitting or needing highly complex ensemble models.

### 6. Visualization
- Scatter plot of **Actual vs. Predicted Prices** to visualize model performance. The tight grouping along the diagonal line demonstrates the high R² score.

---

## 🛠️ Tech Stack

| Library       | Version   | Purpose                         |
|---------------|-----------|---------------------------------|
| Python        | 3.12      | Programming language            |
| NumPy         | —         | Numerical computations          |
| Pandas        | —         | Data manipulation               |
| Matplotlib    | —         | Data visualization              |
| Seaborn       | —         | Statistical visualization       |
| scikit-learn  | —         | Machine learning model & metrics|

---

## 🚀 Getting Started

### Prerequisites

Make sure you have Python 3.x and the required libraries installed:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

### Running the Notebook

1. Clone this repository:
   ```bash
   git clone https://github.com/DHANUSH-909/house-price-prediction.git
   cd house-price-prediction
   ```

2. Launch Jupyter Notebook:
   ```bash
   jupyter notebook "Linear Regression.ipynb"
   ```

3. Run all cells in order to reproduce the full analysis.

---

## 📈 Results

The notebook produces:
- A trained `LinearRegression` model
- Evaluation metrics (MSE and R²)
- A scatter plot comparing actual vs. predicted house prices

---

## 📝 License

This project is open-source and available under the [MIT License](LICENSE).
