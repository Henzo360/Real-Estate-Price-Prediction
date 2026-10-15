# Bangalore Real Estate Price Prediction

## Project overview

This project uses supervised regression to estimate Bangalore property listing prices from location, size, total square footage, and bathroom count. The notebook includes data cleaning, exploratory checks, model comparison, held-out evaluation, and model export.

## Tools

- Python
- pandas and NumPy
- Matplotlib
- scikit-learn
- joblib
- Jupyter Notebook

Install dependencies from `requirements.txt`.

## Repository contents

- `Real Estate Price Prediction Project.ipynb` — end-to-end cleaning, modelling, evaluation, and export workflow.
- `banglore.csv` — source dataset included in this repository.
- `requirements.txt` — Python package dependencies.
- `output/` — generated model, metrics, and metadata; created when the notebook runs.

## Workflow

1. Load the source dataset using a project-relative path.
2. Keep the model fields and parse bedroom/room counts, square footage, bathrooms, and prices into numeric formats.
3. Convert square-footage ranges to their midpoint; non-numeric values with other units are treated as missing rather than incorrectly labelled as square feet.
4. Inspect cleaned numeric distributions and listing counts by location.
5. Split the data into training and test sets before fitting model preprocessing.
6. Fit Linear Regression, Lasso, and Decision Tree regression pipelines with numeric scaling/imputation and one-hot encoding for location.
7. Compare held-out R², MAE, and RMSE, inspect actual-vs-predicted values, and export the selected complete pipeline and metrics.

## Evaluation notes

- R² measures goodness of fit; it is not classification accuracy.
- MAE and RMSE are reported in the same units as the source dataset's `price` column.
- Preprocessing is fitted inside a pipeline using the training set, reducing leakage from data-driven preprocessing.
- Unknown locations are handled by the encoder, but predictions for unseen locations may be less reliable.

## How to run

1. Clone or download this repository.
2. Install dependencies with `python -m pip install -r requirements.txt`.
3. Open `Real Estate Price Prediction Project.ipynb` in Jupyter and run cells from top to bottom.
4. The notebook creates `output/` and saves the selected model pipeline, evaluation metrics, and metadata.

## Limitations

- This is a model trained on the included historical listing dataset; performance may not generalise to current market prices or other cities.
- The source data may contain inconsistent measurement formats and unusual listings. Rows with required fields that cannot be parsed or have non-positive values are excluded.
- The model is a portfolio demonstration and should not be treated as a professional property valuation.

## Author

Henry Odionye
