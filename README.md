# 🏠 Housing Prices Prediction

This project predicts housing prices using machine learning techniques on the Ames Housing dataset, featured in the Kaggle competition:  
**[House Prices - Advanced Regression Techniques](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)**

---

## 📁 Project Structure

- `Housing_Prices_Optimized_Final.ipynb` — Final cleaned and optimized Jupyter Notebook  
- `submission.csv` — Predicted prices for test dataset  
- `README.md` — Project documentation

---

## 🧰 Libraries Used

- pandas  
- numpy  
- matplotlib  
- seaborn  
- scikit-learn  
- xgboost  
- lightgbm

---

## 📊 Dataset Description

The dataset includes detailed information on homes sold in Ames, Iowa. It contains both numerical and categorical features, and the goal is to predict the final sale price.

- **Target variable**: `SalePrice`
- **Features**: Lot area, Year built, Basement, Garage, Overall quality, and more.

---

## ⚙️ Workflow Overview

### 1. Data Loading

- Loaded train and test sets
- Combined them for consistent preprocessing

### 2. Missing Value Handling

- Numerical columns: filled with median  
- Categorical columns: filled with mode

### 3. Feature Engineering

- Created a new feature:  
  `TotalSF = TotalBsmtSF + 1stFlrSF + 2ndFlrSF`

### 4. Preprocessing

- Used `ColumnTransformer`:
  - Numerical: scaled with `StandardScaler`
  - Categorical: encoded with `OneHotEncoder`

### 5. Model Training

Trained and cross-validated multiple models:

- Ridge Regression  
- Random Forest  
- XGBoost  
- LightGBM  

Used **5-fold cross-validation** with RMSE as the scoring metric.

### 6. Final Model: Stacking Regressor

- Base learners: XGBoost, LightGBM  
- Final estimator: Ridge Regression  
- Trained using full training data  
- Output predictions on test set

---

## 📈 Evaluation Metric

- Negative Root Mean Squared Error (neg-RMSE)  
- Averaged across cross-validation folds

---

## 🗃️ Output

- Generates `submission.csv` file for Kaggle submission

---

## 🚀 Usage

1. Install the required dependencies:

   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn xgboost lightgbm
   ```

2. Open and run the Jupyter Notebook:

   ```bash
   jupyter notebook Housing_Prices_Optimized_Final.ipynb
   ```

3. Submit the generated `submission.csv` to Kaggle.

---

## 📌 Notes

- The pipeline is modular and scalable  
- Easy to plug in more models or features  
- All steps are encapsulated for reproducibility

---

## 📜 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).
