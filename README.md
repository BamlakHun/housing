# Housing LTU Project

1. Data Loading and Initial Inspection
Loaded Data: The housing dataset was loaded from a GitHub URL into a pandas DataFrame. </br>
Initial View: Displayed the first 10 rows and checked the DataFrame's information (df.info()). </br>
Missing Values: Confirmed no missing values in the dataset.</br>
Duplicates: Identified and removed duplicate rows. </br>
Unique Values: Checked the number of unique values for each column. </br> </br>
2. Data Preprocessing
Categorical Encoding: Ordinal encoding was applied to specified categorical features ('Irregular Shape', 'Quadrant', 'School District', 'Sold Terms', 'Zip') using OrdinalEncoder from sklearn.preprocessing. </br>
Column Drop: The 'built_after_2000' column was dropped from the DataFrame. </br></br>
3. Data Splitting
Feature/Target Split: The 'Sold Price' column was set as the target variable (y), and the rest of the columns as features (X). </br>
Train-Test Split: The data was split into training (70%) and testing (30%) sets using train_test_split with a fixed random_state. </br></br>
4. Model Training and Evaluation (Random Forest - Initial) 
Model Initialization: A RandomForestRegressor was initialized with a random_state.</br>
Training: The model was trained on the X_train and y_train datasets.</br>
Predictions: Predictions (y_hat) were generated on the X_test dataset.</br>
Evaluation: The R-squared score (0.7866) and RMSE (57113.51) were calculated for the initial model.</br>
Visualization: A scatter plot of actual vs. predicted prices for the test set was generated. </br></br>
5. Hyperparameter Tuning (Random Forest - GridSearchCV)
Parameter Grid: Defined a my_param_grid for n_estimators, max_features, and max_depth.</br>
Grid Search: GridSearchCV was used to find the best hyperparameters for the RandomForestRegressor using 5-fold cross-validation.</br>
Best Parameters: The best parameters found were {'max_depth': 20, 'max_features': 'sqrt', 'n_estimators': 500}.
Optimized Model: The best estimator from the grid search was retrieved.</br></br>
6. Model Training and Evaluation (Random Forest - Optimized)
Predictions: Predictions (y_hat_optimized) were generated using the optimized model on the X_test dataset.</br>
Evaluation: The R-squared score (0.7529) and RMSE (61456.07) were calculated for the optimized model.</br>
Visualization: A scatter plot of actual vs. optimized predicted prices for the test set was generated.</br></br>
7. Feature Importance
Feature Importance Calculation: Feature importances were extracted from the optimized Random Forest model.</br>
Visualization: A bar plot showing the importance of each feature in predicting house prices was created.</br></br>
8. Linear Regression Model
Model Initialization: A LinearRegression model was initialized.</br>
Training: The model was trained on the X_train and y_train datasets.</br>
Predictions: Predictions (y_hat) were generated on the X_test dataset.</br>
Residuals: Calculated residuals (actuals - predictions).</br>
Evaluation: Reported training (0.782) and test (0.739) R-squared scores, and calculated Adjusted R-squared for both training (0.781) and test (0.736) sets. MSE (3.98 billion) and RMSE (63,122.87) were also calculated.</br></br>
9. Data Visualization
Price Distribution: A histogram with KDE was plotted to visualize the distribution of 'Sold Price'.</br>
Correlation Heatmap: A heatmap was generated to show the correlations between all features.</br>
Pairplot: A pairplot was created for 'Sold Price', 'Total Square Feet', 'Total Bedrooms', 'Total Bathrooms', 'Garage Capacity', and 'DOM' to visualize relationships.</br></br>
Overall, we have performed a comprehensive analysis starting from data ingestion and cleaning, through training and evaluating both a basic and hyperparameter-tuned Random Forest model, and a Linear Regression model, all while visualizing key aspects of the data and model performance.
