# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Read the number of unknowns and form the augmented matrix.
2.Perform forward elimination to convert the matrix into upper triangular form.
3.Apply back substitution to find the values of unknowns.
4.Print the computed solutions.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Mageshkumar U
RegisterNumber: 212224240085 
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
    if a[i][j]==0:
        sys.exit('Divide by Zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %.2f'%(i,x[i]),end=' ')
```

## Output:
<img width="841" height="476" alt="image" src="https://github.com/user-attachments/assets/bf25e131-c699-4070-9b84-d6492268aa64" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

