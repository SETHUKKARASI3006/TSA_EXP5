# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose
```

```
data = pd.read_csv("/content/education_vs_income_econometrics_samples.csv")
```

```
decomposition = seasonal_decompose(data['x_education_years'], model='additive',period=2)
```

```
plt.figure(figsize=(10, 12))
plt.subplot(411)
plt.plot(data['x_education_years'], label='Years')
plt.legend(loc='upper left')
plt.title('Years')

plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')

plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')

plt.tight_layout()
plt.show()
```

### OUTPUT:
FIRST FIVE ROWS:

<img width="571" height="239" alt="image" src="https://github.com/user-attachments/assets/86824be1-21fd-46b4-9e9b-d228d8c5a62b" />

PLOTTING THE DATA:

<img width="989" height="295" alt="image" src="https://github.com/user-attachments/assets/44c0b482-5bd5-41a7-ba67-48e997f87293" />

SEASONAL PLOT REPRESENTATION :

<img width="989" height="297" alt="image" src="https://github.com/user-attachments/assets/e2120674-ddad-4acd-bf67-feeedc308f0c" />

TREND PLOT REPRESENTATION :

<img width="989" height="297" alt="image" src="https://github.com/user-attachments/assets/5c9e843c-985b-448a-a988-b4b0b43dafcb" />

RESIDUAL REPRESENTATION:

<img width="989" height="297" alt="image" src="https://github.com/user-attachments/assets/029e6355-3582-404a-87e4-132e7e38d486" />

### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
