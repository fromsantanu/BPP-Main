# Chapter 4: Data Input and Output

## 4.1 Reading and Writing CSV Files

### Reading CSV files:

```python
import pandas as pd

# Reading a CSV file
df = pd.read_csv('data.csv')
print(df)
```

### Writing CSV files:

```python
# Writing to a CSV file
df.to_csv('output.csv', index=False)
```

## 4.2 Reading and Writing Excel Files

### Reading Excel files:

```python
# Reading an Excel file
df_excel = pd.read_excel('data.xlsx', sheet_name='Sheet1')
print(df_excel)
```

### Writing Excel files:

```python
# Writing to an Excel file
df.to_excel('output.xlsx', sheet_name='Sheet1', index=False)
```

## 4.3 Reading and Writing JSON Files

### Reading JSON files:

```python
# Reading a JSON file
df_json = pd.read_json('data.json')
print(df_json)
```
### Writing JSON files:

```python
# Writing to a JSON file
df.to_json('output.json', orient='records', lines=True)
```

## 4.4 Reading and Writing SQL Databases
To read from and write to SQL databases, you need to have a database connector installed, such as sqlite3 for SQLite or SQLAlchemy for other databases.

### Reading from an SQL database:

```python
import sqlite3

# Connecting to a SQLite database
conn = sqlite3.connect('data.db')

# Reading from a SQL database
df_sql = pd.read_sql_query('SELECT * FROM table_name', conn)
print(df_sql)

# Closing the connection
conn.close()
```

### Writing to an SQL database:

```python
from sqlalchemy import create_engine

# Creating an SQLAlchemy engine
engine = create_engine('sqlite:///data.db')

# Writing to a SQL database
df.to_sql('table_name', engine, if_exists='replace', index=False)
```

By the end of this chapter, you should be able to efficiently read from and write to various file formats and SQL databases using Pandas. This ability to handle diverse data sources is essential for effective data analysis and manipulation.
