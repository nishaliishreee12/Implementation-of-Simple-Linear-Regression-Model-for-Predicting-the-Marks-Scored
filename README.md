# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load the dataset and separate the features (X) and target (Y).

2. Split the dataset into training and testing sets, then train a Linear Regression model using the training data.

3.Predict the target values for the test data and compare actual and predicted values using graphs.

4.Evaluate the model using MSE, MAE, RMSE, and display the regression equation (slope and intercept).

## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: KARANKUMAR K
RegisterNumber:212225040171

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, mean_absolute_error

# Load dataset
df = pd.read_csv("student_scores.csv")

print(df.head())

# Features and target
X = df.iloc[:, :-1].values
Y = df.iloc[:, -1].values

# Split dataset
X_train, X_test, Y_train, Y_test = train_test_split(
    X, Y, test_size=1/3, random_state=0
)

# Train model
regressor = LinearRegression()
regressor.fit(X_train, Y_train)

# Prediction
Y_pred = regressor.predict(X_test)

print(pd.DataFrame({
    "Actual": Y_test,
    "Predicted": Y_pred
}))

# Training graph
plt.scatter(X_train, Y_train, color="red")
plt.plot(X_train, regressor.predict(X_train), color="blue")
plt.title("Hours vs Scores (Training Set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()

# Test graph
plt.scatter(X_test, Y_test, color="green")
plt.plot(X_train, regressor.predict(X_train), color="red")
plt.title("Hours vs Scores (Test Set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()

# Metrics
mse = mean_squared_error(Y_test, Y_pred)
mae = mean_absolute_error(Y_test, Y_pred)
rmse = np.sqrt(mse)

print("MSE :", mse)
print("MAE :", mae)
print("RMSE:", rmse)

# Regression equation
print("Slope :", regressor.coef_[0])
print("Intercept :", regressor.intercept_)
*/
```

## Output:

<img width="276" height="436" alt="image" src="https://github.com/user-attachments/assets/49974e7d-fb51-4928-8bd2-e1839f48c373" />



## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
