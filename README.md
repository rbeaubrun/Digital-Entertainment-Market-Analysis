![Digital-Entertainment-Market-Analysis](https://github.com/rbeaubrun/Digital-Entertainment-Market-Analysis/blob/main/pygaming_photo.webp)

# Global Gaming Sales Data Analysis

## Overview  
This project explores 16,416 rows of global gaming sales data from North America, Europe, and Japan spanning 39 years (1980–2020). By analyzing trends in sales, platforms, and genres, it provides actionable insights for gaming investors to prioritize successful genres and platforms during the gaming boom (2007–2010). Review the full code <a href="https://github.com/rbeaubrun/Digital-Entertainment-Market-Analysis/blob/main/Gaming%20Market%20Analysisv2.ipynb">here.</a>

## Technologies Used  
- **Numpy**: Numerical operations and handling large datasets.
- **Python (Pandas)**: For data cleaning, standardization, and analysis.  
- **Matplotlib, Seaborn**: To create compelling data visualizations.  
- **Jupyter Notebook**: For documenting and analyzing the workflow.

## Key Tasks  
- **Data Cleaning**:  
  - Removed rows with null values.
  - Standardized platform names to ensure consistency, e.g., consolidating variations such as "PS" to "PlayStation" and "X360" to "Xbox 360."
  - Adjusted columns to the correct data types (e.g., converting sales to floats and years to integers).

- **Data Analysis**:  
  - Explored the entire dataset, focusing on the “gaming boom” (2007–2010), which accounted for ~2 billion units in sales.
  - Conducted deep dives across developers, platforms, and genres.  

- **Market Analysis**:  
  - Highlighted the top-selling games and critically acclaimed titles, such as *Wii Sports* and *GTA IV*.  
  - Provided actionable insights for investors in genres like Action and Sports, which accounted for 41% of the market during the gaming boom.  

### Summary of Insights:  
- **Developer Analysis**:  
  - Nintendo led the market with 37% of global sales during the gaming boom.  
- **Platform Trends**:  
  - The PlayStation 2, Xbox 360, and PlayStation 3 were the highest-selling platforms of all time.  
  - Mobile gaming (e.g., Nintendo DS and PlayStation Portable) captured ~30% of the market during its rise in the gaming boom.  
- **Genre Dominance**:  
  - Action and Sports genres accounted for 41% of total sales (~912 million units) during the gaming boom, making them highly lucrative for investors.

## Future Enhancements  
- Use **Natural Language Processing (NLP)** to create personalized game recommendations based on user preferences.  
- Perform **regional analysis** to assess strengths and weaknesses for each market.  
- Enhance the dataset by including the **country of origin** for developers to explore regional influences on gaming trends.


## Example Code:  

## Data Cleaning: Dropping null values
```python
# dropping missing values in Year of Release Column 
df.drop(df[df.Year_of_Release.isnull()].index, inplace = True)
```

## Data Analysis: Calculating mobile market share 
```python
# grouping global sales by year 
top_platforms = gaming_boom.groupby('Platforms_Clean')['Global_Sales'].sum().sort_values(ascending = False).head(8)
top_platforms
# summing market share of mobile platforms: Nintendo DS, PlayStation Portable, and Nintendo Game Cube
mobile_platforms = 497.15 + 154.33 + 3.43
print(f'Mobile Platform Sales: {mobile_platforms}')

# summing total market sales
platforms_sales = top_platforms.sum()
print(f'Total Platform Sales: {platforms_sales}')

#calculating mobile market share 
mobile_share = (mobile_platforms/platforms_sales)*100
print(f'Mobile Platform Market Share: {mobile_share}')
```

## Data Visualization: Plotting best-selling games of all time
```python
# define the x and y variables
x = best_games['Name']
y = best_games['Global_Sales']

# plot grouped table in a seaborn bar plot 
sns.barplot(data = best_games, x = 'Name', y = 'Global_Sales', hue = 'Developer', palette = 'gist_earth')

# format the table 
plt.xticks(fontsize = 20, rotation = 45)
plt.yticks(fontsize = 20)
plt.xlabel('Games', fontsize = 30)
plt.ylabel('Global Sales (M)', fontsize = 30)
plt.title('Best-Selling Games of All Time Sales', fontsize = 40)
plt.legend(fontsize = 20)
plt.show()
```
