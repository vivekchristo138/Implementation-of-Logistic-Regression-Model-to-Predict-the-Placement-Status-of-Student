# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load the placement dataset and select required features.
2. Convert placement status into binary values (Placed = 1, Not Placed = 0).
3. Split and standardize the data, then train the Logistic Regression model.
4. Predict placement status and evaluate the model using accuracy and confusion matrix.


## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: Vivek Christo A
Register Number: 212225040497




import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report
data = pd.read_csv("Placement_Data.csv")
data['status'] = data['status'].map({
    'Placed': 1,
    'Not Placed': 0
})
X = data[['ssc_p', 'mba_p']]
y = data['status']
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)
model = LogisticRegression()
model.fit(X_train, y_train)
y_pred = model.predict(X_test)
print("Accuracy:", accuracy_score(y_test, y_pred))
print("\nConfusion Matrix:")
print(confusion_matrix(y_test, y_pred))
print("\nClassification Report:")
print(classification_report(y_test, y_pred))
new_student = np.array([[70, 75]])

new_student_scaled = scaler.transform(new_student)

prediction = model.predict(new_student_scaled)

print("\nPredicted Placement Status:",
      "Placed" if prediction[0] == 1 else "Not Placed")
*/
```

## Output:
<img width="628" height="337" alt="image" src="https://github.com/user-attachments/assets/6c49b882-5b73-4b57-9284-091eac09d98f" />


## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
