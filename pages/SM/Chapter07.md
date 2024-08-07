Chapter 7: Time Series Analysis
Time Series Decomposition
Time series decomposition involves breaking down a time series into its constituent components: trend, seasonal, and residual.

Example: Time Series Decomposition
Let's use a hypothetical time series dataset to demonstrate decomposition.

python
Copy code
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Creating a sample time series
np.random.seed(0)
date_range = pd.date_range(start='1/1/2020', periods=100, freq='M')
data = np.random.randn(100).cumsum() + np.arange(100) * 0.5
df = pd.DataFrame(data, index=date_range, columns=['Value'])

# Time series decomposition
decomposition = seasonal_decompose(df['Value'], model='additive', period=12)

# Plotting the decomposed components
decomposition.plot()
plt.show()
Autoregressive (AR) Models
Autoregressive (AR) models use the dependency between an observation and a number of lagged observations.

Example: AR Model
python
Copy code
from statsmodels.tsa.ar_model import AutoReg

# Creating a sample time series
np.random.seed(0)
data = np.random.randn(100).cumsum() + np.arange(100) * 0.5
df = pd.DataFrame(data, columns=['Value'])

# Fitting the AR model
model = AutoReg(df['Value'], lags=1).fit()

# Summary of the model
print(model.summary())

# Making predictions
predictions = model.predict(start=len(df), end=len(df) + 10, dynamic=False)
print(predictions)

# Plotting the predictions
plt.plot(df['Value'], label='Original')
plt.plot(predictions, label='Predicted', color='red')
plt.legend()
plt.show()
Moving Average (MA) Models
Moving Average (MA) models use the dependency between an observation and a residual error from a moving average model applied to lagged observations.

Example: MA Model
python
Copy code
from statsmodels.tsa.arima.model import ARIMA

# Creating a sample time series
np.random.seed(0)
data = np.random.randn(100).cumsum() + np.arange(100) * 0.5
df = pd.DataFrame(data, columns=['Value'])

# Fitting the MA model
model = ARIMA(df['Value'], order=(0, 0, 1)).fit()

# Summary of the model
print(model.summary())

# Making predictions
predictions = model.predict(start=len(df), end=len(df) + 10, dynamic=False)
print(predictions)

# Plotting the predictions
plt.plot(df['Value'], label='Original')
plt.plot(predictions, label='Predicted', color='red')
plt.legend()
plt.show()
ARIMA and SARIMA Models
ARIMA (Autoregressive Integrated Moving Average) models are a generalization of AR and MA models. SARIMA (Seasonal ARIMA) models extend ARIMA by modeling seasonal effects.

Example: ARIMA Model
python
Copy code
# Creating a sample time series
np.random.seed(0)
data = np.random.randn(100).cumsum() + np.arange(100) * 0.5
df = pd.DataFrame(data, columns=['Value'])

# Fitting the ARIMA model
model = ARIMA(df['Value'], order=(1, 1, 1)).fit()

# Summary of the model
print(model.summary())

# Making predictions
predictions = model.predict(start=len(df), end=len(df) + 10, dynamic=False, typ='levels')
print(predictions)

# Plotting the predictions
plt.plot(df['Value'], label='Original')
plt.plot(predictions, label='Predicted', color='red')
plt.legend()
plt.show()
Example: SARIMA Model
python
Copy code
from statsmodels.tsa.statespace.sarimax import SARIMAX

# Creating a sample time series
np.random.seed(0)
data = np.random.randn(100).cumsum() + np.arange(100) * 0.5
df = pd.DataFrame(data, columns=['Value'])

# Fitting the SARIMA model
model = SARIMAX(df['Value'], order=(1, 1, 1), seasonal_order=(1, 1, 1, 12)).fit()

# Summary of the model
print(model.summary())

# Making predictions
predictions = model.predict(start=len(df), end=len(df) + 10, dynamic=False)
print(predictions)

# Plotting the predictions
plt.plot(df['Value'], label='Original')
plt.plot(predictions, label='Predicted', color='red')
plt.legend()
plt.show()
Forecasting and Prediction
Time series forecasting involves using models to predict future values based on past observations.

Example: Forecasting with ARIMA
python
Copy code
# Creating a sample time series
np.random.seed(0)
data = np.random.randn(100).cumsum() + np.arange(100) * 0.5
df = pd.DataFrame(data, columns=['Value'])

# Fitting the ARIMA model
model = ARIMA(df['Value'], order=(1, 1, 1)).fit()

# Making predictions
predictions = model.predict(start=len(df), end=len(df) + 10, dynamic=False, typ='levels')
print(predictions)

# Plotting the predictions
plt.plot(df['Value'], label='Original')
plt.plot(predictions, label='Predicted', color='red')
plt.legend()
plt.show()
Example: Forecasting with SARIMA
python
Copy code
# Creating a sample time series
np.random.seed(0)
data = np.random.randn(100).cumsum() + np.arange(100) * 0.5
df = pd.DataFrame(data, columns=['Value'])

# Fitting the SARIMA model
model = SARIMAX(df['Value'], order=(1, 1, 1), seasonal_order=(1, 1, 1, 12)).fit()

# Making predictions
predictions = model.predict(start=len(df), end=len(df) + 10, dynamic=False)
print(predictions)

# Plotting the predictions
plt.plot(df['Value'], label='Original')
plt.plot(predictions, label='Predicted', color='red')
plt.legend()
plt.show()
In this chapter, we covered the basics of time series analysis, including decomposition, autoregressive (AR) models, moving average (MA) models, ARIMA and SARIMA models, and forecasting. We provided examples to demonstrate how to perform these analyses using Python's statsmodels library and how to interpret the results.
