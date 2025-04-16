# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. import pandas module and import the required data set.
2. Find the null values and count them.
3. Count number of left values.
4. From sklearn import LabelEncoder to convert string values to numerical values.
5. From sklearn.model_selection import train_test_split.
6.Assign the train dataset and test dataset.
7.From sklearn.tree import DecisionTreeClassifier.
8.Use criteria as entropy.
9.From sklearn import metrics.
10.Find the accuracy of our model and predict the require values.

## Program && Output:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: TAMIZHSELVAN B
RegisterNumber: 212223230225
*/
```
```
import pandas as pd
data=pd.read_csv("Employee.csv")
data.head(5)
```
![image](https://github.com/user-attachments/assets/0a5e6639-f80a-4591-881f-de7f73ab0bc0)

```
data.isnull().sum()
```

![image](https://github.com/user-attachments/assets/496aa59d-4b40-48e8-8fce-257a6fc94d91)

```
data["left"].value_counts()
```

![image](https://github.com/user-attachments/assets/7b0520b0-3df8-44ba-a967-5e1c58dc6cb7)

```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
```
![image](https://github.com/user-attachments/assets/d3432a76-ff8b-4378-9aee-e6c858583c8b)


```
x=data[["satisfaction_level","last_evaluation","Work_accident","promotion_last_5years","number_project","average_montly_hours","time_spend_company","salary"]]
x.head()
```
![image](https://github.com/user-attachments/assets/dbc1b5bb-8648-4b44-99dc-4a07e2736a62)

```
y=data['left']
y.head()
```

![image](https://github.com/user-attachments/assets/deba4896-5881-45bf-b400-072ad663ac93)

```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)

from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
y_pred
```

![image](https://github.com/user-attachments/assets/606443fb-ebe7-4291-abab-fcb1d8e75600)

```
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
![image](https://github.com/user-attachments/assets/df897bef-ac70-45ca-9633-148a8416ffe5)

```
dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```

![image](https://github.com/user-attachments/assets/f719855f-04f3-4cbf-b53e-d4d5c21d7550)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
