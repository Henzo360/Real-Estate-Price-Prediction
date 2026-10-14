# Bangalore Real Estate Price Prediction

## Project overview
A supervised machine-learning project that estimates residential property prices in Bangalore using property attributes such as location, number of rooms, floor area, and bathrooms. The notebook covers data preparation, exploratory analysis, feature engineering, model training, and saving artefacts for potential use in an application.

## Business problem
Property buyers, sellers, and analysts need a consistent starting point for comparing listings. This project explores how property features and location relate to listed prices and builds a regression model to estimate price.

## Tools
- Python
- pandas and NumPy
- Matplotlib
- scikit-learn
- pickle and JSON for saving model artefacts and feature-column metadata

## Workflow
1. Loaded and inspected the Bangalore housing dataset.
2. Standardised room-count values and converted square-footage ranges to numeric values.
3. Handled missing values and inspected duplicate records.
4. Explored location and property-feature distributions and removed selected outliers.
5. Encoded location features for model training.
6. Split the data into training and test sets.
7. Compared Linear Regression, Lasso, and Decision Tree Regressor models.
8. Saved the trained model and feature-column metadata for potential integration.

## Evaluation
The notebook reports a test-set score of approximately **0.8444** for Linear Regression using scikit-learn's `model.score(X_test, y_test)`. For a regression estimator, this is the coefficient of determination (`R²`), not classification accuracy. It indicates how much variation in the test-set target is explained by the model under this split; it does not mean that predictions are 84.44% accurate.

For a stronger evaluation, add MAE and RMSE, compare all candidate models using the same held-out data or cross-validation, and check for data leakage and the impact of outlier removal.

## Repository contents
- `Real Estate Price Prediction Project.ipynb` — preprocessing, EDA, modelling, and model-saving notebook.
- `banglore.csv` — source dataset file included in the repository.

## Setup
Install the main dependencies:

```bash
pip install pandas numpy matplotlib scikit-learn jupyter
```

Open the notebook and run the cells in order. Update file paths if your working directory differs.

## Limitations and next steps
- Document the dataset source, licence, and the meaning/units of the `price` column.
- Add MAE and RMSE to complement R².
- Ensure preprocessing is fitted only on training data; use a scikit-learn Pipeline and ColumnTransformer where appropriate.
- Consider cross-validation and compare the candidate models on consistent metrics.
- Handle unseen locations explicitly in the prediction function.
- Avoid relying on a saved pickle file from an untrusted source; only load model files you created or trust.
- Add a clear example showing inputs, predicted output, and price units.
- If the project is deployed as a web application, add the app source code and deployment instructions.

## Author
Henry Odionye
