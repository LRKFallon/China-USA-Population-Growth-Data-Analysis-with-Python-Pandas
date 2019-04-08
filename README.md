# China-USA-Population-Growth-Data-Analysis-with-Python-Pandas
# Graph 1 shows the absolute population of China and the USA. Graph 2 shows the % population growth of China and the USA.
# Programmed on Jupyter Notebook, in Python, with Pandas.



import pandas as pd from matplotlib import pyplot as plt data = pd.read_csv('countries.csv')

data

### This will display the data frame.
To compare the population growth in the US & China,
the first step is to isolate the data of each.
us = data[data.country == 'United States']

china = data[data.country == 'China']

us china

# GRAPH 1
### Plotting the data:
plt.plot(china.year, china.population / 106, color='r') plt.plot(us.year, us.population / 106, color='b')

### Formatting Graph 1:
plt.legend(['China', 'USA']) plt.xlabel('Year', fontsize=16) plt.ylabel('Population in millions', fontsize=16) plt.title('Absolute Population of China & the USA', fontsize=16, color='g') plt.show()

![01 Graph 1 Absolute Population of China   the USA](https://user-images.githubusercontent.com/48648985/55744744-88672500-5a2d-11e9-809c-7ae67192a4f0.png)

# GRAPH 2
us.population

us.population / us.population.iloc[0] * 100

#### Now the first year is set to 1, and everything is relative to it,
#### as a percentage.
### Plotting the data:
plt.plot(china.year, china.population / china.population.iloc[0] *100, color='r') plt.plot(us.year, us.population / us.population.iloc[0] *100, color='b')

### Plotting Graph 2:
plt.legend(['China', 'USA']) plt.xlabel('Year', fontsize=16) plt.ylabel('Population Growth (First year = 100%)', fontsize=11) plt.title('% Growth in Population of China & the USA)', fontsize=15, color='g') plt.show()
