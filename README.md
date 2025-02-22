# EX-03-Implementation-of-Linear-Regression-Using-Gradient-Descent
# DATE:07.09.2023

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Initialize the weights (θ) with random values or zeros.
2. For each iteration from 1 to num_iterations:
a. Compute the predicted values (hypothesis) for all examples in the training dataset
b. Calculate the error for each example
c. Compute the gradients for each weight
d. Update the weights simultaneously using the gradients and learning rate
4. Repeat step 2 for num_iterations or until convergence (i.e., when the change in the cost function J(θ) becomes very small).
5. Once the algorithm converges or reaches the specified number of iterations, the final values of θ represent the coefficients of the Linear Regression model
6. That's the high-level algorithm for implementing Linear Regression using Gradient Descent. 

## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by: SYED ADIL BASHA
RegisterNumber:  212221043008

import numpy as np
import matplotlib.pyplot as plt
import pandas as pd

data=pd.read_csv("/content/ex1 (3).txt",header =None)

plt.scatter(data[0],data[1])
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Population of City (10,000s)")
plt.ylabel("Profit ($10,000")
plt.title("Profit Prediction")

def computeCost(X,y,theta):
  m=len(y)
  h=X.dot(theta)
  square_err=(h-y)**2
  j=1/(2*m)* np.sum(square_err)
  return j

data_n=data.values
m=data_n[:,0].size
X=np.append(np.ones((m,1)),data_n[:,0].reshape(m,1),axis=1)
y=data_n[:,1].reshape(m,1)
theta=np.zeros((2,1))
computeCost(X,y,theta)

def gradientDescent(X,y,theta,alpha,num_iters):
  m=len(y)
  J_history=[]
  for i in range (num_iters):
    predictions=X.dot(theta)
    error = np.dot(X.transpose(),(predictions-y))
    descent=alpha*1/m * error
    theta-=descent
    J_history.append(computeCost(X,y,theta))
  return theta,J_history

theta,J_history = gradientDescent(X,y,theta,0.01,1500)
print("h(x) ="+str(round(theta[0,0],2))+" + "+str(round(theta[1,0],2))+"x1" )

plt.plot(J_history)
plt.xlabel("Iteration")
plt.ylabel("$J(\Theta)$")
plt.title("Cost function using Grading Descent")

plt.scatter(data[0],data[1])
x_value=[x for x in range(25)]
y_value=[y*theta[1]+theta[0] for y in x_value]
plt.plot(x_value,y_value,color="r")
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Population of City(10,000s)")
plt.ylabel("Profit ($10,000")
plt.title("Profit Prediction")

def predict (x,theta):
  predictions=np.dot(theta.transpose(),x)
  return predictions[0]

predict1=predict(np.array([1,3.5]),theta)*10000
print("For population = 35,000,we predict a profit a profit of $"+str(round(predict1,0)))

print(theta)

predict2=predict(np.array([1,7]),theta)*10000
print("For population =70,000,we predict a profit a profit of $"+str(round(predict2,0)))

*/
```

## Output:

# 1.PROFIT PREDICTION GRAPH:
![1](https://github.com/SYEDADILBASHA1/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/134796157/949d776b-72db-490d-94d3-b93d1ee587e3)

# 2.COMPUTE COST VALUE:
![2](https://github.com/SYEDADILBASHA1/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/134796157/739792ac-1620-4408-80e5-cb1d8aae31c8)

# 3.h(x) VALUE:
![3](https://github.com/SYEDADILBASHA1/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/134796157/c837ab7c-e98f-4de3-a957-2c659541f568)

# 4.COST FUNCTION USING GRADIENT DESCENT GRAPH:
![4](https://github.com/SYEDADILBASHA1/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/134796157/12ba7bee-9b18-4d05-a932-1cd81d2f9736)

# 5.PROFIT PREDICTION GRAPH:
![5](https://github.com/SYEDADILBASHA1/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/134796157/7a1a2449-8d3e-4430-b996-7c138b36236e)

# 6.PROFIT FOR THE POPULATION 35,000:
![6](https://github.com/SYEDADILBASHA1/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/134796157/9a158990-6a69-4c61-b2cc-18f42ea7d86d)

![7](https://github.com/SYEDADILBASHA1/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/134796157/fbb225ea-6587-449f-9fbe-34668c848db3)
# 7. PROFIT FOR THE POPULATION 70,000:
![8](https://github.com/SYEDADILBASHA1/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/134796157/d7de78f5-c9cf-45cc-8797-337ead42a0d1)



## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
