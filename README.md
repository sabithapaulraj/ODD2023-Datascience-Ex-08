# Ex-08-Data-Visualization-1
# AIM

To Perform Data Visualization on a complex dataset and save the data to a file.

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
- STEP 1:
 Read the given Data
- STEP 2:
 Clean the Data Set using Data Cleaning Process
- STEP 3:
 Apply Feature generation and selection techniques to all the features of the data set
- STEP 4:
 Apply data visualization techniques to identify the patterns of the data.

# PROGRAM:
```
Developed By: Sabitha P
Reg No: 212222040137
```

# CODE AND OUTPUT
### READING THE GIVEN FILES
```python
import pandas as pd
df=pd.read_csv("/content/Superstore.csv",encoding='unicode_escape')
df.head()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/991662c7-4dcb-4d1d-9aa3-8c3a116c5bbd)
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/ecbd07f5-e1c3-4f26-be7f-e39d432e3830)

### DATA VISUALIZATION USING SEABORN :
```
import seaborn as sns
from matplotlib import pyplot as plt
```
- <B>_LINE PLOT:_</B>
```python
# Line plot - Sales trends over time (using Order Date)
plt.figure(figsize=(9, 6))
sns.lineplot(x='Order Date', y='Sales', data=df)
plt.title('Sales Trends Over Time')
plt.xticks(rotation=45)
plt.show()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/66bd1763-b55c-47ea-a134-d81212c49943)


- <B>_SCATTERPLOT:_</B>
```python
# Scatter plot - Comparing Sales and Profit based on Ship Mode
plt.figure(figsize=(10, 7))
sns.scatterplot(x='Ship Mode', y='Sales', hue='Category', data=df)
plt.title('Sales and Profit Comparison based on Ship Mode')
plt.show()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/755b60d0-eaaa-42af-a811-d752247de784)


- <B>_BOXPLOT:_</B>
```python
# Box plot - Analyzing the distribution of Sales in different Categories
plt.figure(figsize=(9, 6))
sns.boxplot(x='Category', y='Sales', data=df)
plt.title('Distribution of Sales in different Categories')
plt.show()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/04c16751-1837-42ef-b000-75a5de2a597e)


- <B>_VIOLIN PLOT:_</B>
```python
# Violin plot - Examining the distribution of Sales in different Sub-Categories
plt.figure(figsize=(9, 6))
sns.violinplot(x='Sub-Category', y='Sales', data=df)
plt.title('Distribution of Sales in different Sub-Categories')
plt.xticks(rotation=45)
plt.show()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/0e605943-1b3b-44ca-b353-f3e9b450a772)

- <B>_BARPLOT_</B>
```python
# Bar plot - Comparing Sales across different Regions
plt.figure(figsize=(9, 6))
sns.barplot(x='Region', y='Sales', data=df, hue='Segment')
plt.title('Sales Comparison across Regions by Segment')
plt.show()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/b4b242d5-83f9-4d80-a79c-8d4e767cfb68)


- <B>_POINTPLOT_</B>
```python
# Point plot - Comparing Sales for a specific Category
plt.figure(figsize=(10, 6))
sns.pointplot(x='Category', y='Sales', data=df)
plt.title('Comparison of Sales for each Category')
plt.show()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/1912f3f8-e719-4696-82c0-a35774b7e1ed)

- <B>_COUNT PLOT_</B>
```python
# Count plot - Count of orders in each Category
plt.figure(figsize=(10, 6))
sns.countplot(x='Category', data=df, hue='Region')
plt.title('Count of Orders in each Category by Region')
plt.show()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/01b03a4d-c35b-42a1-8664-729a0585ff10)


- <B>_HISTOGRAM_</B>
```python
# Histogram - Ship Mode
plt.figure(figsize=(10, 6))
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
``` 
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/c11cf14d-fdae-44a0-ba80-b7e0931ca7fb)

- <B>_KDE PLOT_</B>
```python
# KDE plot - Kernel Density Estimate for Sales
plt.figure(figsize=(10, 6))
sns.kdeplot(x='Sales', data=df, hue='Category', fill=True)
plt.title('Kernel Density Estimate for Profit by Category')
plt.show()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/98a7e7e2-0783-4e3f-a178-6f2c93b99208)

### DATA VISUALIZATION USING MATPLOTLIB :
- <B>_PLOT_</B>
```python
# PLOT
plt.plot(df['Category'], df['Sales'])
plt.title('Line Plot of Sales by Category')
plt.xlabel('Category')
plt.ylabel('Sales')
plt.show()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/ce08d76e-d9e5-4cde-8930-b98566d1aaea)

- <B>_PIECHART:_</B>
```python
# PIE CHART - Ship Mode Sales
df_ship_mode = df.groupby('Ship Mode')['Sales'].sum()
plt.figure(figsize=(8, 8))
plt.pie(df_ship_mode, labels=df_ship_mode.index, autopct='%0.0f%%', startangle=90)
plt.title('Sales Distribution by Ship Mode')
plt.show()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/7a315017-5987-4d8d-ad49-efbbadf2f7b4)


- <B>_HISTOGRAM:_</B>
```python
# HISTOGRAM - Sub-Category Sales
plt.figure(figsize=(10, 6))
plt.hist(df['Sub-Category'], facecolor="peru", edgecolor="blue", bins=10)
plt.title('Histogram of Sub-Category Sales')
plt.xlabel('Sub-Category')
plt.ylabel('Frequency')
plt.show()
```

![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/efe74ae1-2599-4ccd-a923-503a9d1c4a88)

- <B>_BARGRAPH:_</B> 
```python
# BAR GRAPH - Sales by Category
plt.bar(df['Category'], df['Sales'])
plt.title('Bar Graph of Sales by Category')
plt.xlabel('Category')
plt.ylabel('Sales')
plt.show()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/f0985774-b412-4727-9541-2726608b1bf9)

- <B>_SCATTERPLOT:_</B>
```python
# SCATTER PLOT - Region vs Profit
plt.scatter(df['Region'], df['Sales'], c="blue")
plt.title('Scatter Plot of Region vs Sales')
plt.xlabel('Region')
plt.ylabel('Sales')
plt.show()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/e2cf1324-18dc-41ba-98f1-5a30c9541b3f)

- <B>_BOXPLOT:_</B>
```python
# BOX PLOT - Sales
plt.boxplot(df['Sales'])
plt.title('Box Plot of Sales')
plt.ylabel('Sales')
plt.show()
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/d3638d4e-9496-4122-b5b1-74c5864e4171)

- <B>_HEATMAP:_</B>
```python
# HEATMAP
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
```
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-08/assets/118343379/2597d5cf-41d3-4060-967a-50d0c0c26d79)

# RESULT:
Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.

