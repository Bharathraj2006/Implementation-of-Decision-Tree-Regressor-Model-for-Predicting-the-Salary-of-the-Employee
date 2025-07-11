# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the libraries and read the data frame using pandas.
2. Calculate the null values present in the dataset and apply label encoder.
3. Determine test and training data set and apply decison tree regression in dataset.
4. Calculate Mean square error,data prediction and r2. 

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Bharath Raj P
RegisterNumber:  212223230031
*/
import pandas as pd
from sklearn.metrics import r2_score
data=pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
x=data[["Position","Level"]]
x.head()
y=data["Salary"]
y.head()
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
y_pred
r2= r2_score(y_test,y_pred)
r2
dt.predict([[5,6]])
```

## Output:
## Dataset
![alt text](output/dataset.png)

## Info
![alt text](output/info.png)

## NULL value
![alt text](output/null.png)

## Encoded
![alt text](output/encoded.png)

## x and y value
![alt text](output/x.png)
![alt text](output/y.png)

## Algorithm
![alt text](output/algorithm.png)

## R2 Score
![alt text](output/r2.png)

## Predicted
![alt text](output/out.png)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
