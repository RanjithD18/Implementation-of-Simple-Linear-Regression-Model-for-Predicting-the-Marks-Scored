# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to implement the simple linear regression model for predicting the marks scored.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the standard Libraries.
2. Set variables for assigning dataset values.
3. Import linear regression from sklearn.
4. Assign the points for representing in the graph
5. Predict the regression for marks by using the representation of the graph.
6. Compare the graphs and hence we obtained the linear regression for the given datas.


## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: Ranjith D
RegisterNumber: 212221240044 
*/
```
~~~
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

data=pd.read_csv("student_scores.csv")

data.head()

X=data.iloc[:,:-1].values #assigning column hours to X
Y=data.iloc[:,1].values #assigning row scores to Y
print(X)
print(Y)

from sklearn.model_selection import train_test_split
X_train,X_test,Y_train,Y_test=train_test_split(X,Y,test_size=1/3,random_state=0)
from sklearn.linear_model import LinearRegression
regressor=LinearRegression()
regressor.fit(X_train,Y_train)

y_pred=regressor.predict(X_test)
plt.scatter(X_train,Y_train,color="red")
plt.plot(X_train,regressor.predict(X_train),color="orange")
plt.title("h vs s(training Set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()

plt.scatter(X_test,Y_test,color="black")
plt.plot(X_test,regressor.predict(X_test),color="brown")
plt.title("h vs s(testing Set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
~~~
## Output:
![simple linear regression model for predicting the marks scored](https://github.com/RanjithD18/Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored/blob/main/1.png)<br>
![simple linear regression model for predicting the marks scored](https://github.com/RanjithD18/Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored/blob/main/2.png)

## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
