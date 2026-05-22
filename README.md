# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by:KAMALESH E
RegisterNumber: 212225230122
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
def QR_Decomposition(A):
    m,n=a.shape
    q=np.zeros((m,n))
    r=np.zeros((m,n))
    for j in range(n):
        v=a[:,j].copy()
        for i in range(j):
            r[i,j]=np.dot(q[:,i].T,a[:,j])
            v=v-r[i,j]*q[:,i]
        r[j,j]=np.linalg.norm(v)
        q[:,j]=v/r[j,j]
    return q,r
a = np.array(eval(input()))
q,r=QR_Decomposition(a)
print("The Q Matrix is\n",q.round(8))
print("The R Matrix is\n",r.round(8))

```

## Output
<img width="1325" height="538" alt="image" src="https://github.com/user-attachments/assets/f5c7fa27-d694-4ef4-9183-81b3395cfb62" />

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
