# Bangalore Real Estate Price Prediction

## Project overview
This project builds a supervised machine-learning workflow to estimate residential property prices in Bangalore using property attributes. The notebook includes data inspection, preprocessing, feature engineering, exploratory analysis, regression-model training, and saving the selected model and feature-column metadata.

The dataset includes fields such as area type, availability, location, size, society, total square footage, number of bathrooms, number of balconies, and price.

## Business problem
Property prices vary with location and property characteristics. This project explores whether a regression model trained on historical property data can estimate a property's listed price from the available features.

## Tools and libraries
- **Python** — project implementation
- **pandas and NumPy** — data preparation and numerical operations
- **Matplotlib** — exploratory visualisation
- **scikit-learn** — preprocessing, train/test splitting, and regression models
- **pickle and JSON** — saving the trained model and feature-column information

## Data preparation and feature engineering
### Missing values and data inspection
The notebook inspects the dataset and removes rows with missing values in the preparation stage.

### Property size
The `size` field contains room-count descriptions such as BHK or bedroom values. The notebook standardises this information into a numeric representation.

### Total square footage
The `total_sqft` field can contain numeric values and ranges. The notebook converts range values into numeric estimates so the field can be used as a model feature.

### Outlier handling
The notebook examines the distribution of property features and removes selected outlier records before training.

### Location encoding
Location is a categorical feature. The notebook uses one-hot/dummy encoding to represent location values numerically for the regression models.

## Model development
The notebook trains and compares the following regression algorithms:
- Linear Regression
- Lasso Regression
- Decision Tree Regressor

The data is split into training and test sets using an 80/20 split with `random_state=20`. The notebook selects Linear Regression as the preferred model and saves the trained model using pickle, alongside JSON metadata for the feature columns.

## Model evaluation
The notebook reports a test-set score of approximately **0.8444** from scikit-learn's `model.score(X_test, y_test)` for Linear Regression. For this regression estimator, the score represents the coefficient of determination, **R²**. It is not classification accuracy and should not be interpreted as a statement that 84.44% of predictions are correct.

R² describes the proportion of target variation explained by the model on the evaluated test set, relative to a baseline that predicts the mean target value. Its value depends on the dataset, preprocessing, split, and evaluation procedure used.

## Repository contents
- `Real Estate Price Prediction Project.ipynb` — notebook for data preparation, exploration, model training, evaluation, and model saving.
- `banglore.csv` — dataset file included in the repository.
- `README.md` — project documentation.

## Running the project
1. Clone or download the repository.
2. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib scikit-learn jupyter
   ```

3. Open the notebook in Jupyter.
4. Confirm that the CSV file path in the notebook points to `banglore.csv` or update it to the correct local path.
5. Run the notebook cells in order.

## Scope and limitations
The model's output is an estimate based on the patterns learned from the dataset; it is not a formal property valuation. The reported evaluation result applies to the notebook's particular train/test split and preprocessing workflow. The saved pickle model should only be loaded from a trusted source.

## Author
Henry Odionye
