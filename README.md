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
6. Assign the train dataset and test dataset.
7. From sklearn.tree import DecisionTreeClassifier.
8. Use criteria as entropy.
9. From sklearn import metrics.
10. Find the accuracy of our model and predict the require values.

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

data.isnull().sum()

data["left"].value_counts()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()

x=data[["satisfaction_level","last_evaluation","Work_accident","promotion_last_5years","number_project","average_montly_hours","time_spend_company","salary"]]
x.head()

y=data['left']
y.head()

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)

from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
y_pred

from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy

dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```

## Output :
### Preview datasets :

![EX_8_OUTPUT_1](https://github.com/user-attachments/assets/0b3f73e5-923a-47af-84ed-9a18721ec74d)

### Finding Null Values :

![EX_8_OUTPUT_2](https://github.com/user-attachments/assets/514b1e5e-4b3c-4c0e-8de8-393056c75aa4)

### Count Value of Left :

![EX_8_OUTPUT_3](https://github.com/user-attachments/assets/cf9911c1-0f0d-4229-81ff-25c3e61fa2e4)

### Label Encoder :

![EX_8_OUTPUT_4](https://github.com/user-attachments/assets/d0f8e292-427a-4111-8c60-3ac586821eee)

### X-Initialize :

![EX_8_OUTPUT_5](https://github.com/user-attachments/assets/42569639-3048-4821-898e-f4381715f7ab)

### Y-Initialize :

![EX_8_OUTPUT_6](https://github.com/user-attachments/assets/16cb3d61-e7ac-4084-b8fc-84f345eb9c8a)

### Y_Predict :

![EX_8_OUTPUT_7](https://github.com/user-attachments/assets/5604039c-8626-4b80-b31d-0437f7380733)

### Accuracy :

![EX_8_OUTPUT_8](https://github.com/user-attachments/assets/3e7e9e4f-a498-467c-aa86-424fbf9c666b)

### Final Predict :

![EX_8_OUTPUT_9](https://github.com/user-attachments/assets/a87368e6-141a-4985-aa28-a1b2297e8dd7)


## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
