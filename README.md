# House Price Predictor
 
My first hands-on machine learning project, built after completing Andrew Ng's Machine Learning Specialization on Coursera. The goal was to apply the concepts from the specialization — regression, feature scaling, regularization, and model evaluation — on a real dataset instead of guided lab exercises.
 
## Dataset
 
[California Housing Prices](https://www.kaggle.com/datasets/camnugent/california-housing-prices) from Kaggle. Contains ~20,000 rows describing California housing districts, with features like location, median income, and room counts, and the target variable `median_house_value`.
 
> The dataset (`housing.csv`) is not included in this repo — download it from the Kaggle link above and place it in the project folder to run the notebook.
 
## What I did
 
1. **Data cleaning** — filled missing `total_bedrooms` values with the column median.
2. **Feature engineering**
   - Applied log transforms to `total_rooms`, `total_bedrooms`, `population`, and `households` to reduce skew.
   - Created two new ratio features: `bedroom_ratio` (bedrooms per room) and `household_rooms` (rooms per household).
3. **Categorical encoding** — one-hot encoded the `ocean_proximity` column.
4. **Train/test split** — 80/20 split, done *after* feature engineering so both sets share identical columns.
5. **Feature scaling** — standardized features using `StandardScaler`, fit on the training set only.
6. **Modeling** — trained and compared two models:
   - Linear Regression
   - Random Forest Regressor
7. **Evaluation** — compared R² scores on the held-out test set.
## Results
 
| Model | Test R² |
|---|---|
| Linear Regression | 0.687 |
| Random Forest | 0.832 |
 
Random Forest outperformed Linear Regression by a solid margin, likely because it captures non-linear relationships and feature interactions that a linear model can't represent.
 

## Tools used
 
Python, pandas, NumPy, scikit-learn, Jupyter Notebook
