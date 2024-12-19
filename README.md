# Global Gaming Sales Data Analysis

## Overview  
This project involves cleaning, analyzing, and visualizing 16,000 rows of global gaming sales data from North America, Europe, and Japan over the past 39 years. The goal is to uncover trends in top-performing genres and platforms to guide investor strategies in the gaming industry.

## Technologies Used  
- **Python (Pandas)**: Data cleaning, standardization, and analysis  
- **Matplotlib, Seaborn**: Data visualization  
- **Jupyter Notebook**: Documentation and analysis workflow

## Key Tasks  
- **Data Cleaning**:  
  Standardized and addressed missing/inconsistent entries in a dataset spanning multiple regions (NA, Europe, Japan).  
- **Trend Analysis**:  
  Analyzed trends in gaming genres and platforms over 39 years.  
- **Visualization**:  
  Created charts to highlight sales trends, platform performance, and historical patterns.

### Summary:
- **Current Status**: I am actively working on analyzing and visualizing trends, with code examples for ongoing analysis.
- **Future Improvements**: The project will expand to include new data points and refined visualizations. 


```python
# Example of Python code used for data cleaning with Pandas
import pandas as pd

# Load the dataset
df = pd.read_csv('gaming_sales_data.csv')


# Fill missing values
df['Genre'].fillna('Unknown', inplace=True)
df['Platform'].fillna('Unknown', inplace=True)

# Convert data types if necessary
df['Year'] = df['Year'].astype(int)

