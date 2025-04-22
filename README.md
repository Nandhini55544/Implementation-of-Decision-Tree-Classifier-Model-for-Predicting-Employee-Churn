# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas module and import the required data set.
2. Find the null values and count them.
3. Count number of left values.
4.From sklearn import LabelEncoder to convert string values to numerical values.
5. From sklearn.model_selection import train_test_split.
6. Assign the train dataset and test dataset.
7. From sklearn.tree import DecisionTreeClassifier.
8. Use criteria as entropy.
9. From sklearn import metrics.
10. Find the accuracy of our model and predict the require values.

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: Nandhini M
RegisterNumber: 212224040211
*/

import pandas as pd data = pd.read_csv("Employee (1).csv") data.head()

data.info() data.isnull().sum() data['left'].value_counts()

from sklearn.preprocessing import LabelEncoder le = LabelEncoder()

data['salary'] = le.fit_transform(data['salary']) data.head()

x=data[['satisfaction_level','last_evaluation','number_project','average_montly_hours','time_spend_company','Work_accident','promotion_last_5years','salary']] x.head()

y=data['left']

from sklearn.model_selection import train_test_split x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state =100)

from sklearn.tree import DecisionTreeClassifier dt=DecisionTreeClassifier(criterion='entropy') dt.fit(x_train,y_train) y_predict=dt.predict(x_test)

from sklearn import metrics accuracy=metrics.accuracy_score(y_test,y_predict) accuracy

dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```

## Output:
## Data haed:
![image](https://github.com/user-attachments/assets/f6742e6e-4349-4c7a-ac4a-543652fff0d7)
## Dataset info:
![image](https://github.com/user-attachments/assets/e90e30da-1a9a-44d2-ab6c-05fb62c40cd0)
![image](https://github.com/user-attachments/assets/c09d0bd9-54f6-44a1-993c-2044a5a2f28e)
## Dataset transformed head:
![image](https://github.com/user-attachments/assets/cc7d809c-3574-4852-9c72-65c19186f817)
## X.Head:
![image](https://github.com/user-attachments/assets/dd6adf06-f3de-452e-a3b9-7918d9981847)
## Accuracy:
![image](https://github.com/user-attachments/assets/c7bbc232-31f5-4893-b130-d3f94b6a8b67)


## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
