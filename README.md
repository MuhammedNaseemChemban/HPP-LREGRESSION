# Housing Price Prediction Using Linear Regression

## Overview

This project involves predicting the **median house value** in California using various features such as the number of rooms, population, income, and more. The primary goal was to build a predictive model using **linear regression** and improve its performance using feature engineering, transformations, and regularization techniques, while adhering to project constraints.

## Data

The dataset used in this project is **housing.csv**, which contains data related to California's housing. The dataset includes the following columns:

- `longitude`: Longitude of the housing district.
- `latitude`: Latitude of the housing district.
- `housing_median_age`: Median age of the housing.
- `total_rooms`: Total number of rooms in the district.
- `total_bedrooms`: Total number of bedrooms in the district.
- `population`: Population of the district.
- `households`: Number of households in the district.
- `median_income`: Median income in the district.
- `median_house_value`: The target variable representing the median house value in the district.
- `ocean_proximity`: A categorical feature indicating the proximity to the ocean (e.g., `NEAR BAY`, `NEAR OCEAN`).

## Methodology

### 1. **Data Preprocessing**
   - **Missing Values**:Solve by using fillna().
   - **Feature Selection**: The relevant features were selected, which include `median_income`, `total_rooms`, `total_bedrooms`, `population`, `households`, `longitude`, `latitude`, and `ocean_proximity`.
   
### 2. **Log Transformation of Target Variable**
   - The target variable `median_house_value` was transformed using the **logarithmic transformation** to reduce the effect of large outliers and to normalize the distribution.

### 3. **Feature Engineering**
   - **Interaction Features**: Two new interaction features were created:
     - `rooms_per_person`: Total rooms divided by the population.
     - `bedrooms_per_room`: Total bedrooms divided by the total rooms.
   - **One-hot Encoding**: The categorical feature `ocean_proximity` was one-hot encoded to handle the categorical data effectively.

### 4. **Feature Scaling**
   - The features were scaled using **StandardScaler** to standardize the input data for better performance of the linear regression model.

### 5. **Model Training**
   - A **Linear Regression** model was trained using the processed features, and the performance was evaluated using the **Mean Squared Error (MSE)** and **R-squared (R²)** on both the test set and through **cross-validation**.

### 6. **Cross-Validation**
   - Cross-validation with 5-folds was performed to ensure the model's performance is consistent across different subsets of the data.

## Results

### Performance Metrics:

- **Test Set Results**:
   - **Mean Squared Error (MSE)**: 0.1114
   - **R-squared (R²)**: 0.6567
   
- **Cross-Validation Results**:
   - **Cross-validated MSE**: 0.1280

### Insights:

1. **Test Set Performance**:
   - The model performed well with an **MSE of 0.1114** on the test set, suggesting that it predicts the median house values fairly accurately.
   - The **R-squared value of 0.6567** indicates that about **66%** of the variance in the target variable (median house value) is explained by the model.

2. **Cross-Validation**:
   - The **cross-validated MSE of 0.1280** is slightly higher than the test set MSE but remains quite close. This indicates that the model is **generalizing well** to different subsets of the data and is not overfitting.

3. **Log Transformation**:
   - The **log transformation** of the target variable improved the model's ability to handle large outliers, making the model predictions more stable and accurate.

4. **Interaction Features**:
   - The interaction features `rooms_per_person` and `bedrooms_per_room` provided useful information that helped the model better capture relationships between the features and the target variable.

## Conclusion

The **linear regression** model, after feature engineering and transformation, demonstrated solid performance with an **R-squared value of 0.6567** and an **MSE of 0.1114** on the test set. The cross-validation results showed that the model is not overfitting and generalizes well to unseen data.
