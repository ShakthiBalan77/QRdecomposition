# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
    <img width="377" height="319" alt="Screenshot 2025-12-19 175322" src="https://github.com/user-attachments/assets/5a4644e5-ec59-4f62-bb1e-ef6351473593" />
3.	Obtain the Q matrix   
    <img width="261" height="33" alt="Screenshot 2025-12-19 175422" src="https://github.com/user-attachments/assets/2356a659-93d4-4dbc-9374-ea10339c2c7c" />

4.	Construct the upper triangular matrix R
    <img width="306" height="104" alt="Screenshot 2025-12-19 175510" src="https://github.com/user-attachments/assets/e5399f03-4c8e-4505-9e9c-a2f9a579c49d" />



## Program:
### Gram-Schmidt Method
```
Developed by: Shakthi Balan V
RegisterNumber : 25016098

```

```
import numpy as np
def QR_Decomposition(A):
    A=np.array(A,dtype=float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((m,n))
    for j in range(n):
        v=A[:,j]
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R
a = np.array(eval(input()))
Q,R = QR_Decomposition(a)
print("The Q Matrix is \n",Q)
print("The R Matrix is \n",R)
```

## Output
```
<img width="921" height="829" alt="Screenshot 2025-12-19 175017" src="https://github.com/user-attachments/assets/2cd2024d-9b59-4eb4-97eb-2a3cbb92040e" />

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
