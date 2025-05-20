# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Start the process and input the number of variables n.

2.Create an augmented matrix a[n][n+1] and a solution array x[n].

3.Input all elements of the augmented matrix a from the user.

4.For each row i from 0 to n-1, check if the pivot element a[i][i] == 0. If true, print an error and stop (to avoid division by zero).

5.For each row j from i+1 to n-1, compute the ratio: ratio = a[j][i] / a[i][i].

6.For each column k from i to n, update the matrix element: a[j][k] = a[j][k] - ratio * a[i][k].

7.After forward elimination is complete, begin back substitution starting from the last row i = n-1 to 0.

8.Set x[i] = a[i][n] (the constant term of the current equation).

9.For each column j from i+1 to n-1, update x[i] = x[i] - a[i][j] * x[j].

10.Divide to get the final value: x[i] = x[i] / a[i][i]. 

11. Print all values in x.
## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Shri Raama Krishanan J
RegisterNumber: 212224220100
*/
```
![Screenshot 2025-04-28 123330](https://github.com/user-attachments/assets/1292cfa0-5a8a-46b9-a030-1a56a8272116)
```python
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
        sys.exit('Divide by zero detected!')
        
    for j in range(i+1,n):
        ratio=a[j][i] / a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio*a[i][k]
            
x[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
    
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end=' ')
```
## Output:
![Screenshot 2025-04-28 123035](https://github.com/user-attachments/assets/f5b067af-a419-44d6-a2d9-dee90496761d)
## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

