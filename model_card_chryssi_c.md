# Model Card

See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration. 

## Model Description

Polynomial Regression
Suitability: Better for capturing nonlinear relationships between variables.
Use if: Initial results from linear regression suggest non-linearity in the relationships.
Limitations: Can lead to overfitting if the degree of the polynomial is too high.

Steps to Implement Polynomial Regression
Data Preparation: First, ensure that the data is clean, merged appropriately, and ready for modeling.
Feature Selection: Identify the predictor variables (global temperatures) and the response variable (sea level rise).
Polynomial Feature Transformation: Transform the predictor variables into polynomial features.
Model Setup: Set up the polynomial regression model using these features.
Model Training: Train the model on your dataset.
Model Evaluation: Evaluate the model using appropriate metrics such as RMSE (Root Mean Squared Error), MAE (Mean Absolute Error), or R-squared.

## Inputs

The inputs of the model are: 
1. UK average temparature rises (median) every month between 2050 and 2079
2. UK Sea level rises including the coordinates (x,y) 5%, 50% and 95% percentile every 10 years from 2010 till 2100.
3. Global max temperature rises (median, lower and upper) every month between 2040 to 2069

For further detail:
1. UK Average Temperature Rises (2050-2079)
Data Points: Monthly median temperatures, including statistical upper and lower bounds.
Usage: Convert monthly temperatures to annual averages to correspond with sea level data at decade intervals.
2. UK Sea Level Rises (2010-2100)
Data Points: Sea level rises at 5%, 50%, and 95% percentiles every 10 years.
Usage: Use the relevant sea level data that corresponds to the temperature dataset years.
3. Global Max Temperature Rises (2040-2069)
Data Points: Monthly median, lower, and upper temperature projections.
Usage: This can be used to establish a relationship between global temperature increases and UK-specific changes.

## Outputs

1. Computed UK temperature annual averages for the years 2050 to 2079, to align with the sea level data for corresponding years.
2. Computed average sea level rises for the years 2050, 2060, and 2070.
3. Merged and aligned UK temperature and sea level rise data.
4. Global temperature data similarly for years where it overlaps with the sea level data.
5. MSE and R square
6. The model outputs predictions of sea level anomalies based on input temperatures. With current data, these predictions are very accurate within the training set.

## Model Architecture

Steps followed to develop the model:
Data Loading: Load all three datasets to examine their structure.
Data Preprocessing: Since the datasets cover different periods and have different structures, we need to preprocess them to ensure they are aligned for modeling. This includes:
Converting monthly temperature data to annual averages for both UK and global data.
Extracting relevant sea level data for corresponding years.
Feature Engineering: Generate polynomial features from temperature data.
Model Building: Use Ridge and Lasso regression to incorporate regularization.
Model Training and Tuning: Employ cross-validation to determine the optimal polynomial degree and regularization strength.
Evaluation: Assess the model using appropriate metrics and visualize the results to interpret the relationships.
Graphical Representation: Plot the results to show the predicted vs. actual values and how temperature changes influence sea level rises

## Performance

Insights: The model suggests that there is a strong correlation between the combined effect of UK and global temperatures and sea level rises. This could be crucial for planning and mitigation strategies in response to climate change, especially in predicting the impact on coastal and low-lying areas.

R² Score (0.991): This score is very close to 1, which indicates that the model explains nearly all of the variability in sea level anomalies around their mean. In other words, the model does an excellent job at capturing the relationship between the input temperatures and sea level changes.

Mean Squared Error (0.197): This is quite low, suggesting that the model's predictions are very close to the actual data points. The smaller the MSE, the closer the fit is to the data. 


## Limitations

Firstly, each data file was different, the ID was inconsistent as well as the timeframe eg the global temperatures were from 2040 - 2069 whereas the UK temperatures were from 2050 to 2079. The temperature files used a GRID ID where as the flooding file used co-ordinates.
Additional, limitations were the number of years, which resulted in a few data points given that I averaged the data.

Overall, the model is currently based on a limited dataset (only three data points: 2050, 2060, and 2070). This can lead to overfitting despite the regularization used in the Ridge regression. Therefore, while the model fits the given data well, its predictions for other years or under different conditions should be treated cautiously.

## Trade-offs

There are plenty of trade-offs given the data set I chose:

1. Overfitting
Description: The model was trained on a very limited dataset with only three data points (2050, 2060, and 2070).
Trade-off: While the model fits these points perfectly (R² of 1.0), it is likely overfitted to this specific dataset.
Impact: This means the model may not generalize well to other years or different datasets, exhibiting poor performance when applied to unseen data.

2. Limited Data Points
Description: The training dataset includes only three points.
Trade-off: With such limited data, it’s challenging to capture complex patterns and relationships.
Impact: The model's predictions and insights are based on very sparse information, reducing confidence in its ability to accurately forecast future temperatures or sea level changes.

3. Degree of Polynomial
Description: The model uses a polynomial degree of 5.
Trade-off: Higher-degree polynomials can capture more complex relationships but also increase the risk of overfitting.
Impact: While the model captures the existing data well, the high-degree polynomial may cause it to react too strongly to small fluctuations, leading to instability and poor predictions on new data.

4. Regularization
Description: Ridge regression with alpha = 0.1 was used for regularization.
Trade-off: While regularization helps control overfitting, the chosen alpha value was determined based on the small dataset.
Impact: The effectiveness of this regularization parameter may vary with larger or different datasets, potentially requiring re-tuning for optimal performance.

5. Extrapolation Beyond Training Data
Description: The model predicts sea level anomalies based on given temperature values within a small range (three data points).
Trade-off: Predictions outside this range (extrapolation) can be highly unreliable.
Impact: Forecasting for years significantly beyond 2070 or for temperatures outside the observed range may lead to inaccurate predictions due to the lack of representative data.

6. Assumptions on Data Quality
Description: The model assumes the provided data points are accurate and representative of broader trends.
Trade-off: Any errors or biases in the input data directly impact the model's performance.
Impact: If the data points for 2050, 2060, and 2070 are not accurate reflections of future trends, the model's predictions will be flawed.


