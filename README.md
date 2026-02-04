# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load the placement dataset and preprocess it by handling missing values and encoding categorical data.
2. Split the dataset into training and testing sets.
3.Split the dataset into training and testing sets. 
4.Predict student placement on test data and evaluate using accuracy and confusion matrix. 

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by:   S.NITHYASRI
RegisterNumber:  25018590
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

from sklearn.preprocessing import LabelEncoder
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report
from sklearn.metrics import ConfusionMatrixDisplay
dataset = pd.read_csv("C:/Users/acer/Downloads/Placement_Data.csv")
dataset.head()
df = dataset.copy()
df = df.drop(columns=['sl_no', 'salary'])

df.head()
print("Missing Values in Dataset:\n")
print(df.isnull().sum())

print("\nTotal Duplicate Rows:", df.duplicated().sum())
encoder = LabelEncoder()

df['gender'] = encoder.fit_transform(df['gender'])
df['ssc_b'] = encoder.fit_transform(df['ssc_b'])
df['hsc_b'] = encoder.fit_transform(df['hsc_b'])
df['hsc_s'] = encoder.fit_transform(df['hsc_s'])
df['degree_t'] = encoder.fit_transform(df['degree_t'])
df['workex'] = encoder.fit_transform(df['workex'])
df['specialisation'] = encoder.fit_transform(df['specialisation'])
df['status'] = encoder.fit_transform(df['status'])

df.head()
X = df.drop('status', axis=1)
y = df['status']

print("Input Features Shape:", X.shape)
print("Output Target Shape:", y.shape)
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.20, random_state=10
)
log_reg = LogisticRegression(
    solver='liblinear',
    max_iter=1000
)

log_reg.fit(X_train, y_train)
y_pred = log_reg.predict(X_test)

print("Predicted Values:\n", y_pred)
acc = accuracy_score(y_test, y_pred)
print("\nAccuracy Score:", acc)

cm = confusion_matrix(y_test, y_pred)
print("\nConfusion Matrix:\n", cm)

print("\nClassification Report:\n")
print(classification_report(y_test, y_pred))
cmd = ConfusionMatrixDisplay(
    confusion_matrix=cm,
    display_labels=['Not Placed', 'Placed']
)

cmd.plot()
plt.title("Confusion Matrix – Logistic Regression")
plt.show()
*/
```

## Output:
![the Logistic Regression Model to Predict the Placement Status of Student](sam.png)<img width="555" height="356" alt="Screenshot 2026-02-04 110944" src="https://github.com/user-attachments/assets/bea4a98b-5510-462c-9f08-255c1da6a92f"<img width="819" height="583" alt="Screenshot 2026-02-04 110953" src="https://github.com/user-attachments/assets/436117ea-5a0c-4766-821e-3cf2bae7a0c2" />

                                                                                      />



## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
