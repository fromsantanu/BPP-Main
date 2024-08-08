# Chapter 9: Date and Time Manipulation
## 9.1 Working with Datetime Objects
Pandas provides powerful capabilities for working with datetime objects, allowing for easy manipulation and analysis of date and time data.

### Creating a DataFrame with datetime objects:

```python
import pandas as pd

data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Date': ['2021-01-01', '2021-02-01', '2021-03-01'],
    'Salary': [50000, 60000, 70000]
}
df = pd.DataFrame(data)

# Converting the 'Date' column to datetime
df['Date'] = pd.to_datetime(df['Date'])
print(df)
print(df.dtypes)
```

### Extracting date components:

```python
# Extracting year, month, and day
df['Year'] = df['Date'].dt.year
df['Month'] = df['Date'].dt.month
df['Day'] = df['Date'].dt.day
print(df)
```

### Performing datetime arithmetic:

```python
# Adding days to the date
df['Date_plus_10_days'] = df['Date'] + pd.Timedelta(days=10)
print(df)

# Calculating the difference between dates
df['Date_diff'] = df['Date'] - pd.Timestamp('2021-01-01')
print(df)
```

## 9.2 Date Range Generation
Pandas can generate sequences of dates easily using the date_range function.

### Generating a date range:

```python
# Generating a range of dates
date_range = pd.date_range(start='2021-01-01', end='2021-01-10')
print(date_range)

# Generating a range of dates with a specific frequency
date_range_freq = pd.date_range(start='2021-01-01', periods=10, freq='D')
print(date_range_freq)
```

### Creating a DataFrame with a date range index:

```python
# Creating a DataFrame with a date range index
df_date_range = pd.DataFrame({
    'Value': range(10)
}, index=pd.date_range(start='2021-01-01', periods=10, freq='D'))
print(df_date_range)
```

## 9.3 Resampling and Frequency Conversion
Resampling allows you to change the frequency of your time series data. This can be useful for downsampling (reducing frequency) or upsampling (increasing frequency).

### Creating a time series DataFrame:

```python
# Creating a time series DataFrame
date_rng = pd.date_range(start='2021-01-01', periods=100, freq='D')
df_time_series = pd.DataFrame({
    'Value': range(100)
}, index=date_rng)
print(df_time_series)
```

### Resampling to a lower frequency (downsampling):

```python
# Resampling to monthly frequency and calculating the sum
df_monthly = df_time_series.resample('M').sum()
print(df_monthly)
```

### Resampling to a higher frequency (upsampling):

```python
# Resampling to hourly frequency and forward filling missing values
df_hourly = df_time_series.resample('H').ffill()
print(df_hourly)

### Frequency conversion:

```python
# Converting frequency from daily to weekly and calculating the mean
df_weekly = df_time_series.asfreq('W', method='pad')
print(df_weekly)
```

By the end of this chapter, you should be proficient in manipulating and analyzing date and time data in Pandas. These skills are crucial for handling time series data and performing time-based analysis.
