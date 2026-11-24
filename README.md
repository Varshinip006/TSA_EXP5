# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 24-11-2026
### Name: Priya Varshini P
### Reg No.: 212224240119


### AIM:

To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### DATASET USED:

myntra_dataset_ByScraping.csv

### SOFTWARE REQURIED:

Google Colab


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

# Step 1: Load the Myntra dataset
data = pd.read_csv('myntra_dataset_ByScraping.csv')

# Step 2: Select the price column
# Remove missing values
data = data.dropna(subset=['price'])

# Convert price column into time-series format
price_data = data['price'].reset_index(drop=True)

# Step 3: Perform seasonal decomposition
decomposition = seasonal_decompose(
    price_data,
    model='additive',
    period=12
)

# Step 4: Plot the decomposition
plt.figure(figsize=(10, 12))

# Original Data
plt.subplot(411)
plt.plot(price_data, label='Product Price')
plt.legend(loc='upper left')
plt.title('Original Product Price')

# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Trend Plot')

# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')

plt.tight_layout()
plt.show()

```


### OUTPUT:

FIRST FIVE ROWS:

PLOTTING THE DATA:

<img width="1232" height="372" alt="image" src="https://github.com/user-attachments/assets/2ab72259-58e8-4eca-a1aa-0b207284a8e4" />


SEASONAL PLOT REPRESENTATION :

<img width="1191" height="385" alt="image" src="https://github.com/user-attachments/assets/d1a83c92-bf92-40f7-ac3c-c1ff30d7ca07" />




TREND PLOT REPRESENTATION :

<img width="1227" height="382" alt="image" src="https://github.com/user-attachments/assets/1aa29e41-0a3a-4854-83b4-14bd097427a9" />



OVERAL REPRESENTATION:

<img width="1231" height="377" alt="image" src="https://github.com/user-attachments/assets/e149d9f4-c144-45c3-9fff-c63906b2bf77" />


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
