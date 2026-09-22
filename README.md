# California Housing Regression Analysis

## Project Overview

This project uses the California Housing dataset to build and compare regression models for predicting median house values.

The main objective is to identify the best regression model using evaluation metrics, cross-validation, and hyperparameter tuning.

## Dataset

The California Housing dataset is loaded using Scikit-learn's `fetch_california_housing()` function.

### Features

- **MedInc:** Median income of residents
- **HouseAge:** Median house age
- **AveRooms:** Average number of rooms
- **AveBedrms:** Average number of bedrooms
- **Population:** District population
- **AveOccup:** Average number of household members
- **Latitude:** Geographical latitude
- **Longitude:** Geographical longitude

### Target Variable

- **MedHouseVal:** Median house value

## Project Objectives

1. Load and explore the dataset.
2. Check for missing values and duplicate records.
3. Perform exploratory data analysis.
4. Visualise feature distributions and relationships.
5. Preprocess the data for machine learning.
6. Train different regression models.
7. Evaluate the models using MSE, MAE, and R².
8. Perform five-fold cross-validation.
9. Apply hyperparameter tuning.
10. Select the best-performing regression model.

## Data Preprocessing

The dataset was checked for missing values and duplicate records.

Feature scaling was performed using `StandardScaler` for models that benefit from scaling, such as Linear Regression and Support Vector Regression. The scaler was fitted only on the training data to avoid data leakage.

Tree-based models, including Decision Tree, Random Forest, and Gradient Boosting, generally do not require feature scaling.

## Regression Models Used

- **Linear Regression:** Used as a baseline model and assumes a linear relationship between the features and the target.
- **Decision Tree Regression:** Captures non-linear relationships using a tree structure.
- **Random Forest Regression:** Combines multiple decision trees to improve accuracy and reduce overfitting.
- **Gradient Boosting Regression:** Builds trees sequentially, with each tree attempting to reduce previous errors.
- **Support Vector Regression:** Predicts continuous values and can model non-linear relationships using kernels.

## Evaluation Metrics

The models were evaluated using:

- **Mean Squared Error (MSE):** Lower values indicate better performance.
- **Mean Absolute Error (MAE):** Lower values indicate better performance.
- **R² Score:** Higher values indicate better performance.

The best model should generally have low MSE and MAE and a high R² score.

## Cross-Validation

Five-fold cross-validation was used to evaluate the consistency of each model across different subsets of the dataset.

The average cross-validation score was compared across the models to assess their generalisation performance.

## Hyperparameter Tuning

`GridSearchCV` was used to find suitable hyperparameter combinations for the regression models.

Hyperparameter tuning was applied to:

- Decision Tree Regression
- Random Forest Regression
- Gradient Boosting Regression
- Support Vector Regression

Linear Regression was used as a baseline because it has relatively few important hyperparameters.

The tuned models were evaluated again using the test dataset.

## Identifying the Best and Worst Models

The best model was selected by considering:

- The lowest MSE
- The lowest MAE
- The highest R² score
- Strong and consistent cross-validation performance
- Improved performance after hyperparameter tuning

The worst model was identified by considering the highest prediction errors and the lowest R² score.


## Conclusion

The final model should be selected using the combined results of test-set evaluation, cross-validation, and hyperparameter tuning.

Random Forest and Gradient Boosting may perform strongly because they can capture complex and non-linear relationships in housing data. However, the final model must be selected based on the actual results obtained from the experiment.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

