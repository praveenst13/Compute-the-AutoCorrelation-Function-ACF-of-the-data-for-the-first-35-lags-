# EX.NO:4 Compute-the-AutoCorrelation-Function-ACF-of-the-data-for-the-first-35-lags-
## AIM:
To Write a Program to time series analysis and decomposition on the monthly average temperature of a city/country 

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Procedure:
    1 Import the numpy and matplotlib.pyplot modules.
    2 Find the mean, variance and then implement normalization for the data.
    3 Implement the correlation using necessary logic and obtain the results
    4 Store the results in an array
    5 Represent the result in graphical representation as given below.
  
## Program:
```

import matplotlib.pyplot as plt
import numpy as np

data = np.array([12.0, 24.0, 7.0, 20.0, 7.0, 22.0, 18.0, 22.0, 6.0, 7.0, 20.0, 13.0, 8.0, 5.0, 8.0])

plt.title("Autocorrelation Plot")
plt.xlabel("Lags")
plt.acorr(data, maxlags=14)
print("The Autocorrelation plot for the data is:")


plt.show()

program 2:
data = [12.0, 24.0, 7.0, 20.0, 7.0, 22.0, 18.0, 22.0, 6.0, 7.0, 20.0, 13.0, 8.0, 5.0, 8.0]

# Delay (lag) range that we are interesting in
lags = range(15)

# Pre-allocate autocorrelation table
acorr = len(lags) * [0]

# Mean
mean = sum(data) / len(data)

# Variance
var = sum([(x - mean)**2 for x in data]) / len(data)

# Normalized data
ndata = [x - mean for x in data]
# Go through lag components one-by-one
for l in lags:
    c = 1 # Self correlation

    if (l > 0):
        tmp = [ndata[l:][i] * ndata[:-l][i]
            for i in range(len(data) - l)]

        c = sum(tmp) / len(data) / var
        print(c)
        acorr[l] = c

plt.title("Autocorrelation Plot")
plt.xlabel("Lags")
plt.plot(acorr)
print("The Autocorrelation plot for the data is:")


plt.show()

```
## Output:


![tsf](https://github.com/praveenst13/Compute-the-AutoCorrelation-Function-ACF-of-the-data-for-the-first-35-lags-/assets/118787793/45bc51b9-56c7-4e0e-8b21-e622ac40c01b)


![tsf2](https://github.com/praveenst13/Compute-the-AutoCorrelation-Function-ACF-of-the-data-for-the-first-35-lags-/assets/118787793/5725d9d5-9a1f-4165-8691-2126213db43b)



