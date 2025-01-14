# Implementation of Linear Regression Using Gradient Descent

## Aim:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas, numpy and mathplotlib.pyplot.
2. Trace the best fit line and calculate the cost function.
3. Calculate the gradient descent and plot the graph for it.
4. Predict the profit for two population sizes.

## Program:
```
Program to implement the linear regression using gradient descent.
Developed by: JANANI.S
RegisterNumber: 212222230049
```
```python
import numpy as np
import pandas as pd
from sklearn.preprocessing import StandardScaler
def linear_regression(X1,y,learning_rate=0.01,num_iters=1000):
    X=np.c_[np.ones(len(X1)),X1]
    theta=np.zeros(X.shape[1]).reshape(-1,1)
    for _ in range(num_iters):
        predictions=(X).dot(theta).reshape(-1,1)
        errors=(predictions-y).reshape(-1,1)
        theta-=learning_rate*(1/len(X1))*X.T.dot(errors)
    return theta
data=pd.read_csv('50_Startups.csv',header=None)
print(data.head())

X=(data.iloc[1:, :-2].values)
print(X)
X1=X.astype(float)
scaler=StandardScaler()
y=(data.iloc[1:,-1].values).reshape(-1,1)
print(y)
X1_Scaled=scaler.fit_transform(X1)
Y1_Scaled=scaler.fit_transform(y)
print(X1_Scaled)
print(Y1_Scaled)

theta=linear_regression(X1_Scaled,Y1_Scaled)

new_data=np.array([165349.2,136897.8,471784.1]).reshape(-1,1)
new_Scaled=scaler.fit_transform(new_data)
prediction=np.dot(np.append(1,new_Scaled),theta)
prediction=prediction.reshape(-1,1)
pre=scaler.inverse_transform(prediction)
print(f"Predicted value: {pre}")
```

## Output:
### Data:
![hd](https://github.com/JananiSoundararajan/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119477549/130e7f0b-e58d-40e9-a545-2730a41ded84)

### X values:
![X](https://github.com/JananiSoundararajan/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119477549/21d5f762-9dfc-49c1-aeea-b85a8aa47585)

### Y values:
![Screenshot 2024-03-10 124528](https://github.com/Jenishajustin/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119405070/d5cacfc3-9ffe-44fc-b800-282b632a49d3)

###  X scaled:
![Screenshot 2024-03-10 124653](https://github.com/Jenishajustin/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119405070/b2433095-d24b-408f-8632-82afb0d684b3)

### y scaled:
![Screenshot 2024-03-10 124737](https://github.com/Jenishajustin/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119405070/435e20b8-40ce-48dd-b63a-c34d7aea8b8b)

### Predicted value:
![Screenshot 2024-03-10 124822](https://github.com/Jenishajustin/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119405070/504a544d-4365-4acf-b86c-20d3a9c207ba)

## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
