# Product Demand Prediction

A machine learning project for predicting product demand (`units_sold`) using historical sales data. The project explores the distribution of product sales and compares **Random Forest Regression** with **Linear Regression** to determine how well different models can predict demand.

## Project Overview

Accurate demand prediction can help businesses understand product sales patterns and make better decisions about inventory and planning.

In this project, historical sales data is prepared and analyzed before building regression models. Two machine learning approaches are evaluated:

* Random Forest Regressor
* Linear Regression

The models are compared using **Root Mean Squared Error (RMSE)** and **R² (R-squared)**.

The project also examines the effect of extreme sales values by removing observations above the 99th percentile and retraining the models.

## Objectives

* Explore and understand the sales dataset.
* Prepare the data for machine learning.
* Analyze the distribution of `units_sold`.
* Identify the number of unique stores and products.
* Train a Random Forest regression model.
* Train a Linear Regression model.
* Compare model performance using RMSE and R².
* Visualize predicted values against actual sales.
* Investigate how outliers affect model performance.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Jupyter Notebook

## Dataset

The project uses a `train.csv` dataset containing historical product sales information.

The data includes features such as:

* `week` — sales date represented as week/month/year
* `store_id` — store identifier
* `sku_id` — product identifier
* `units_sold` — number of units sold, used as the prediction target

The `week` column is split into separate `day`, `month`, and `year` features during preprocessing.

## Data Preparation

The following preprocessing steps are performed:

1. Load the dataset using Pandas.
2. Split the `week` column into `day`, `month`, and `year`.
3. Remove the original `week` column.
4. Remove `record_ID`, since it is an identifier rather than a predictive feature.
5. Separate the features from the target variable.
6. Split the data into training and testing sets.
7. Handle missing values for Linear Regression.
8. Perform an additional analysis after removing sales values above the 99th percentile.

## Machine Learning Models

### Random Forest Regression

A `RandomForestRegressor` is trained to capture potentially complex relationships between the available features and product demand.

Performance is evaluated using:

* RMSE
* R²

### Linear Regression

A `LinearRegression` model is also trained as a simpler baseline model.

Its predictions are evaluated using the same metrics, allowing the two approaches to be compared consistently.

## Model Evaluation

### RMSE

**Root Mean Squared Error (RMSE)** measures the average magnitude of prediction errors.

A lower RMSE generally indicates better predictive performance.

### R² Score

**R² (R-squared)** measures how much of the variation in the target variable is explained by the model.

A higher R² generally indicates better model performance.

## Exploratory Data Analysis

The project includes visual analysis of the `units_sold` variable and other numerical features.

The analysis is used to identify:

* Data distribution
* Skewness
* Potential outliers
* Variation in sales
* Number of unique stores
* Number of unique products

## Outlier Analysis

The project compares the sales distribution and model performance before and after removing extreme values.

Sales records above the **99th percentile of `units_sold`** are removed for the second round of modeling.

This helps investigate whether unusually high sales observations have a significant effect on prediction performance.

## Visualizations

The project includes:

* Distribution histogram of `units_sold`
* Histograms of dataset variables
* Random Forest predicted vs. actual values
* Linear Regression predicted vs. actual values
* Sales distribution after outlier removal

The prediction plots help visually evaluate how closely model predictions follow the actual sales values.

## Project Structure

```text
Product-Demand-Prediction/
│
├── train.csv
├── demand_prediction.ipynb
└── README.md
```

> File names may vary depending on the notebook and dataset names used in the repository.

## Results

The performance of Random Forest and Linear Regression is compared using RMSE and R².

The analysis also examines whether removing extreme sales values changes model performance.

The model with the **lower RMSE and higher R²** provides the stronger predictive performance for this dataset.

## Key Takeaways

This project demonstrates a practical machine learning workflow:

* Data loading and preprocessing
* Exploratory data analysis
* Feature and target selection
* Train/test splitting
* Regression modeling
* Model evaluation
* Data visualization
* Outlier analysis
* Model comparison

## Future Improvements

Possible improvements include:

* Feature engineering based on dates and product/store information
* Encoding categorical variables appropriately
* Hyperparameter tuning for Random Forest
* Testing additional regression models
* Using time-based train/test splitting for more realistic demand forecasting
* Applying cross-validation
* Investigating seasonal sales patterns
* Comparing additional evaluation metrics

## Author

**Rahel Belay**

Software Engineering Graduate | Full-Stack & Flutter Developer | Data Analytics Enthusiast
