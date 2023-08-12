### Wind_Power_Prediction

The aim of the project was to build a machine learning model that could predict the active power of a wind turbine.

The dataset used was the ‘Wind Power Forecasting’ dataset from kaggle see link: https://www.kaggle.com/datasets/theforcecoder/wind-power-forecasting. There were 21 dependent variables and the independent variable was ‘Active Power’. The raw data was processed as evident in the Wind Power Data Cleaning Project.

The models tested were Linear Regression, Decision Tree, Random Forest, Neural Network and XGBoost. 
The cost function used was mean absolute error, which gives the average absolute difference between predictions and the measured value in the data. A lower value indicating better model performance. MAE is easy to interpret, robust to outliers, and is not sensitive to positive or negative errors.
Hyperparameters were tuned using grid or random search.

Three fold cross validation was used during model training. The training data was split into three subsets. The model is trained and evaluated three times, each time using a different combination of two folds for training and one fold for testing.The reason cross validation was used was to reduce overfitting on a training test split, it provides a more reliable estimate of model performance than a single train-test split because the evaluation is based on multiple test sets, and is more computationally efficient compared to 5 or 10 splits. 

The most successful model was the random forest, which had a training MAE of 7.98. It was expected that the neural net or extra boost would have performed better. Some reasons this was the case are random forests are good at capturing non linear relationships, where as Neural Networks usually require more extensive hyperparameter tuning. Also Random Forest is an ensemble method that combines multiple decision trees, each trained on a random subset of features. This averaging of multiple trees can reduce the impact of noise and outliers in the data, leading to better generalisation. Finally Random Forests are less affected by irrelevant features, as they select the best features during the tree-building process. In contrast, Neural Networks and XGBoost might struggle with irrelevant features, requiring additional feature engineering.

The hyper parameters of the decisions tree which were selected for final model testing were n_estimators = 20, min_samples_split = 10, min_samples_leaf = 10, max_features = auto and max_depth = 20. 
The final test MAE was 7.93. This is considered a good value as average Active Power value was 619.11 so the model was able to predict Active Power within 1.3% of actual values. 

The limitations of the study were null values were removed from the dataset. It is possible these values reflected important data or patterns which could have been saved e.g. by forward or backfilling. Further industry knowledge should be applied to determine whether these data points could be saved. 
The data points were treated as independent data points. This data set contains temporal information which could be really valuable in active power prediction e.g. by showing trends and seasonality. Future work could consider treating data as dependent data points to retain this information. 
Future development could focus on further data cleaning to reduce my noise from the model i.e removing collinear variables. 
Finally, as grid search was used to find the optimal hyperparameters iterative search could have been applied on these hyperparameters to find a ‘better’ model. 

The project was successful in predicting the active power of a wind turbine to within 1.3% of actual average values.
