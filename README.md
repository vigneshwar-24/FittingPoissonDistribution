# Fitting Poisson Distribution

# Aim : 

To fit poisson distribution for the given frequencey distribution

 ![image](https://user-images.githubusercontent.com/104613195/166092068-a5bf057f-fe65-41b8-ba2f-310fc6b56078.png)


# Software required :  

Python

# Theory:

The Poisson distribution is the discrete probability distribution of the number of events occurring in a given time period, given the average number of times the event occurs over that time period.

![image](https://user-images.githubusercontent.com/104613195/166248326-fd042076-8b0b-40c4-8b11-1d8e8fcb74db.png)

 Conditions for Poisson Distribution:

1. An event can occur any number of times during a time period.
2. Events occur independently. I
3. The rate of occurrence is constant.
4. The probability of an event occurring is proportional to the length of the time period. 
 
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

# Procedure :

![image](https://user-images.githubusercontent.com/104613195/166251988-d0c53205-6080-4f7b-ae4c-398178586637.png)

# Program
Developed by <br>
Register Number: 212220230058 <br>
Name: vigneshwar s
```python
import numpy as np
import math
import scipy.stats
X=[0,1,2,3,4,5,6]
f=[153,169,72,31,12,6,2]
n=6
N=np.sum(f)
mean=np.inner(X,f)/N
Prob=list(); E=list(); xi=list()
print("  X P(X=x) Obs.Fr  Ex.Fre   xi ")
print("----------------------------------")
for x in range(7):
    Prob.append(math.exp(-mean)*mean**x/math.factorial(x))
    E.append(Prob[x]*N)
    xi.append((f[x]-E[x])**2/E[x])
    print("%2.2f %2.2f  %4.2f   %3.2f   %3.2f"%(x,Prob[x],f[x],E[x],xi[x]))
print("----------------------------------")
cal_chi2=np.sum(xi)
print("Calculated value of Chi square is %4.2f"%cal_chi2)
tab_chi2=scipy.stats.chi2.ppf(1-.01, df=n)
print("Table value of Chi square at 1  level is %4.2f"%tab_chi2)
if cal_chi2<tab_chi2:
    print("The given data can be fitted in Poissson distribution at 1% LOS")
else:
    print("The given data cannot be fitted in Poisson distribution at 1% LOS")
``` 

# Output : 
 ![image](https://user-images.githubusercontent.com/75235488/168961732-57780624-1e01-4ac5-b3d5-20ebbe9f9178.png)

# Result:
Thus, fitting poisson distribution for the given frequencey distribution is verified.
