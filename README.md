# Predicted Adjusted Closing Price

The last 10 years historical data of 3 companies (Adidas, Apple and Toyota Motors) has been used as a database which was retrieved from the Yahoo finance website.
The complete database was split into training (60%), cross validation(20%) and test data(20%).

## LSTM
Long Short Term Memory (LSTM) has been used to predict the Adjusted Closing Price using the values of Adjusted Closing Price of the past 3 days.
The model used has 2 alternating LSTM and dropout layers and 1 dense layer and was trained using 10 epochs.

## LAST VALUE

The value of Adjusted Closing Price of the previous day is used for predictimg the next value, hence the name Last Value.

## LINEAR REGRESSION
Used sklearn.linear_model.LinearRegression to construct a linear regression model and implemented it by varying the Number of elements used to predict next value (from 1 to 30) . The R2 score decreased as the value increased from 1 to 30 while the root mean square error increased.
Selected the values 3 and 5 for optimum results and checked the results on test data.

## MOVING AVERAGE

Used dataframe.rolling function for performing rolling window calculations(Varied the size of rolling window from 1 to 25) and used the rolling mean function to predict values, used Root mean squared error values for selecting an optimum window size from 1-25 .The final size of rolling window is 2.


## XGB

xgbRegressor from xgboost is used for constructing the model which implements gradient boosting. 
Values of the past 3 days are used to predict the value for the next day.
