# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the packages.
2. Analyse the data.
3.Use modelselection and Countvectorizer to preditct the values. 
4. Use modelselection and Countvectorizer to preditct the values.

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: SANJAI RAM RS
RegisterNumber:  212225040366
*/


import pandas as pd
data=pd.read_csv("spam.csv", encoding='Windows-1252')
data

data.shape

x=data['v2'].values
y=data['v1'].values
x.shape

y.shape

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2, random_state=0)
x_train

x_train.shape

from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred

from sklearn.metrics import accuracy_score,confusion_matrix,classification_report
acc=accuracy_score(y_test,y_pred)
acc

con=confusion_matrix(y_test,y_pred)
print(con)

cl=classification_report(y_test,y_pred)
print(cl)
```

## Output:
<img width="917" height="502" alt="image" src="https://github.com/user-attachments/assets/5572f741-5a4a-440f-b33e-0c092c7b4756" />
<img width="1373" height="220" alt="image" src="https://github.com/user-attachments/assets/43eba5a2-3dc5-4638-a38c-4a74d1a35bec" />
<img width="1373" height="220" alt="image" src="https://github.com/user-attachments/assets/79ad4aec-912b-458c-8bb8-56be04ecd58f" />
<img width="1373" height="220" alt="image" src="https://github.com/user-attachments/assets/0806e6a7-a886-402d-9418-84860c9922b4" />
<img width="237" height="38" alt="image" src="https://github.com/user-attachments/assets/9917582e-9cad-4cb5-a43d-432b7391b46a" />







## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
