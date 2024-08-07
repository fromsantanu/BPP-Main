Chapter 2: Data Input and Management
Importing Data (CSV, Excel, etc.)
Importing CSV Files
CSV (Comma Separated Values) files are one of the most common formats for storing and exchanging data. You can use the pandas library to import CSV files into a DataFrame, which is the primary data structure in pandas.

python
Copy code
import pandas as pd

# Importing a CSV file
df = pd.read_csv('path_to_your_file.csv')
print(df.head())
Importing Excel Files
Excel files are also widely used for data storage. The pandas library provides functions to read Excel files.

python
Copy code
# Importing an Excel file
df = pd.read_excel('path_to_your_file.xlsx', sheet_name='Sheet1')
print(df.head())
Importing Data from a URL
Sometimes, data is available online, and you can directly import it from a URL.

python
Copy code
# Importing data from a URL
url = 'http://example.com/data.csv'
df = pd.read_csv(url)
print(df.head())
Data Preparation and Cleaning
Removing Unnecessary Columns
Often, datasets contain columns that are not needed for your analysis. You can remove these columns using the drop method.

python
Copy code
# Dropping unnecessary columns
df = df.drop(['Unnecessary_Column1', 'Unnecessary_Column2'], axis=1)
print(df.head())
Renaming Columns
Renaming columns can make your DataFrame more readable and easier to work with.

python
Copy code
# Renaming columns
df = df.rename(columns={'OldColumnName1': 'NewColumnName1', 'OldColumnName2': 'NewColumnName2'})
print(df.head())
Converting Data Types
Ensure that your data is in the correct format for analysis. You can use the astype method to convert data types.

python
Copy code
# Converting data types
df['ColumnName'] = df['ColumnName'].astype('float')
print(df.dtypes)
Handling Missing Data
Checking for Missing Data
First, identify missing data in your DataFrame.

python
Copy code
# Checking for missing data
print(df.isnull().sum())
Removing Rows with Missing Data
If missing data is not significant, you can remove rows containing missing values.

python
Copy code
# Removing rows with missing data
df = df.dropna()
print(df.isnull().sum())
Filling Missing Data
Sometimes, you may want to fill missing data with a specific value, such as the mean or median of the column.

python
Copy code
# Filling missing data with the mean
df['ColumnName'] = df['ColumnName'].fillna(df['ColumnName'].mean())
print(df.isnull().sum())
You can also fill missing data with other methods, such as forward fill or backward fill.

python
Copy code
# Forward fill
df = df.fillna(method='ffill')

# Backward fill
df = df.fillna(method='bfill')
Example: Complete Workflow
Here is a complete example that demonstrates importing a CSV file, preparing and cleaning the data, and handling missing values.

python
Copy code
import pandas as pd

# Step 1: Importing data
df = pd.read_csv('path_to_your_file.csv')
print("Initial DataFrame:")
print(df.head())

# Step 2: Removing unnecessary columns
df = df.drop(['Unnecessary_Column1', 'Unnecessary_Column2'], axis=1)
print("After dropping unnecessary columns:")
print(df.head())

# Step 3: Renaming columns
df = df.rename(columns={'OldColumnName1': 'NewColumnName1', 'OldColumnName2': 'NewColumnName2'})
print("After renaming columns:")
print(df.head())

# Step 4: Converting data types
df['NewColumnName1'] = df['NewColumnName1'].astype('float')
print("After converting data types:")
print(df.dtypes)

# Step 5: Checking for missing data
print("Checking for missing data:")
print(df.isnull().sum())

# Step 6: Handling missing data
# Option 1: Removing rows with missing data
df = df.dropna()
print("After removing rows with missing data:")
print(df.isnull().sum())

# Option 2: Filling missing data with the mean
# df['NewColumnName1'] = df['NewColumnName1'].fillna(df['NewColumnName1'].mean())
# print("After filling missing data with the mean:")
# print(df.isnull().sum())
In this chapter, we covered how to import data from various sources, prepare and clean the data, and handle missing values. These steps are crucial for ensuring that your data is ready for analysis and modeling.
