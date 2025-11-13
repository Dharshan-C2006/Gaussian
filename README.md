# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
Step1 : Import the NumPy module to perform matrix operations easily.
Step 2: Take input from the user:
     ->Number of equations (n)
     ->Coefficients and constants of each equation
       Store them in an augmented matrix using np.array() or np.zeros()
Step 3: Use for loops to perform Forward Elimination to make the matrix upper triangular.
Check for division by zero.
Then use another for loop to do Back Substitution and calculate the values of unknowns.
Step 4:Store the final results (solutions) in a list or array (x) and display each variable with 2 decimal places.
Step 5:End the program
```

## Program:

```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: C Dharshan
RegisterNumber: 212224230059
'''

import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit("Divide by zero detected")
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i];
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f "%(i,x[i]),end='')
```

## Output:
<img width="1189" height="665" alt="image" src="https://github.com/user-attachments/assets/cc55c459-6e34-4f7e-9d7a-8ace1d5a348e" />

<img width="1227" height="588" alt="image" src="https://github.com/user-attachments/assets/afb3035c-b7cb-45d4-b5b2-5a87c931b661" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

