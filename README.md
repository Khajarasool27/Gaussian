# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

### Step 1: Start the process and input the augmented matrix of size n × (n+1) for n equations and n unknowns.
### Step 2: Perform forward elimination to convert the matrix into upper triangular form by eliminating the entries below the pivot element.
### Step 3: Check for zero pivots to avoid division by zero. If found, terminate the process.
### Step 4: Perform backward substitution starting from the last equation to find the values of unknowns one by one.
### Step 5: Display the solution of all variables and end the process.


## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: BOYALAKUNTLA KHAJA RASOOL 
RegisterNumber: 212224230040 
'''
import numpy as np
import sys 
n=int(input())
a=np.zeros((n,n+1))
X=np.zeros(n)
for i in range (n):
    for j in range(n+1):
        a[i][j]=float(input())
        
for i in range (n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
            
X[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-1,-1,-1):
    X[i]=a[i][n]
    
    for j in range (i+1,n):
        X[i]=X[i]-a[i][j]*X[j]
        
    X[i]=X[i]/a[i][i]
for i in range (n):
    print('X%d = %0.2f'%(i,X[i]),end=" ")
```

## Output:
![image](https://github.com/user-attachments/assets/b86829fd-3db5-4cb7-8e67-9e36813b9c82)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

