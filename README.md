# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
![Screenshot 2025-04-27 122149](https://github.com/user-attachments/assets/28b9a640-091d-4ac7-8597-ce67aad2039b)
    
3.	Obtain the Q matrix   
![Screenshot 2025-04-27 122248](https://github.com/user-attachments/assets/83daffcc-2fb1-4f23-b971-34b58517ec33)

4.	Construct the upper triangular matrix R
 ![Screenshot 2025-04-27 122432](https://github.com/user-attachments/assets/d817b0da-41c0-44e4-8a96-64bf5e8c8152)




## Program:
### Gram-Schmidt Method
```

import numpy as np
def QR_Decomposition(A):
    # Write your code
    n,m=A.shape
    Q=np.empty((n,m))
    u=np.empty((n,m))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print(Q)
    print(R)
a=np.array(eval(input()))
QR_Decomposition(a)

```

## Output

![Screenshot 2025-04-27 122519](https://github.com/user-attachments/assets/fa545563-8445-42a5-8d41-30eca5a38d5c)



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
