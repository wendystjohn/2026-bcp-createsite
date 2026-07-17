---
title: 'Day 2 afternoon - Plotting in Python'
layout: home
nav_order: 4
---

# Plotting in Python

Once we've got data ready, we can visualize data in a variety of different ways. Here, we'll walk through some of the utility available through the `matplotlib` library and it's sublibrary `pyplot`.

## Content
- [Part 1: The basics of `matplotlib`](#the-basics-of-matplotlib)
- [Part 2: Plotting from lists](#part-2-plotting-from-lists)
    - [2.1 Line graphs](#21-working-with-paired-continuous-datasets-line-graphs)
    - [2.2 Scatterplots](#22-working-with-paired-continuous-datasets-scatterplots)
    - [2.3 Bar graphs](#23-working-with-combined-discrete-and-continuous-data-bar-graphs)
    - [2.4 Boxplots](#24-working-with-combined-discrete-and-continuous-data-boxplots)
- [Part 3: Plotting from dataframes](#part-3-plotting-from-a-pandas-dataframe)
    - [3.1 Line plots](#31-line-plots-for-trends-within-rows-across-columns)
    - [3.2 Scatterplots](#32-scatter-plots-for-relationships-between-columns)
    - [3.3 Boxplots](#33-boxplots-to-compare-across-discrete-variables)
    - [3.4 Statistics](#34-basic-statistics-with-scipy)
- [Part 4: Exercise answers](#part-4-exercise-answers)

## The basics of `matplotlib`
Plotting in `matplotlib` is oriented around plot objects which have specific layers/components. We generate an initial plot by using the `.plot()` function. Once we have generated a plot, we can modify the components using functions which update the plot currently in the environment. 

Examples of these functions include:
- `.title()` : assign/change title associated with the plot
- `.xlabel()`: assign/change X-axis label
- `.ylabel()`: assign/change Y-axis label
- `.legend()`: assign/change legend

Today, we'll walk through generating some basic plot types, as well as some examples using the `gapminder` dataset. 

If you would like to learn more, extensive [documentation](https://matplotlib.org/stable/users/index.html) is available!

## Part 2: Plotting from lists

### 2.1 Working with paired continuous datasets: line graphs
When dealing with datasets which contain strictly continuous variables (e.g. can be represented on a scale), we'll typically visualize it using either line plots or scatter plots. Let's walk through how we can generate these.

Our first step is to load in the `matplotlib` library. Note that we assign the library the alias `plt`, and so we'll preceed any functions that we call from the 'matplotlib' library with this alias instead. 

```python
#import matplotlib
import matplotlib.pyplot as plt
```

The most straightforward way to define datasets in a plot is to provide lists of datapoints correpsonding to X and Y coordinates on your plot. For example, we can define the two lists as below using:

```python
#create X and Y coordinate lists
XCoords = [0, 1, 2, 3]
YCoords = [0, 1, 2, 3]
```

We can then turn these lists into a line plot using the `.plot()` function, which takes two positional arguments corresponding to the X (first argument) and Y (second argument) coordinates of points on the line. The underlying assumption is that the lists are paired with respect to the order that the numbers appear, i.e. the first elements of list X and list Y correspond with the coordinates of the first point. In this case, the first position would be (0, 0). 

```python
#line plot
plt.plot(XCoords, YCoords)
```
![fig1](https://hackmd.io/_uploads/HJqbwawWfe.png)


We can annotate our plot using:

```python
#annotated line graph
plt.plot(XCoords, YCoords)
plt.title("Line graph") # add main title
plt.xlabel('X coordinates') # add X axis labels
plt.ylabel('Y coordinates') # add Y axis labels
```
![fig2](https://hackmd.io/_uploads/HklQvavbGe.png)

If we wanted to plot multiple datasets on the same plot, we can do so by calling `.plot()` multiple times. Let's first start by creating some additional Y coordinates. We're going to raise every number in the YCoords list to the second and third power, respectively. This is denoted by '**'. 

```python
#get quadratic and cubic Y coodrinates
YCoordsQuad = [y ** 2 for y in YCoords] #take every element of YCoords list to second power
YCoordsCub = [y ** 3 for y in YCoords] #take every element of YCoords list to third power
```

We can now generate a line graph which has separate lines representing each set of Y coordinates. Note that we include a new argument in our `.plot()` calls, `label=`, which lets us assign a unique identifier to each data series. We also explicitly add a legend by calling the `.legend()` function.

```python
#multi-series line graph
plt.plot(XCoords, YCoords, label="Linear") # linear data series
plt.plot(XCoords, YCoordsQuad, label="Quadratic") # quadratic data series
plt.plot(XCoords, YCoordsCub, label="Cubic")
plt.title("Line graph") # add main title
plt.xlabel('X coordinates') # add X axis labels
plt.ylabel('Y coordinates') # add Y axis labels
plt.legend() # add legend
```
![fig3](https://hackmd.io/_uploads/HJkV50wZfe.png)

### 2.2 Working with paired continuous datasets: scatterplots

Line graphs connected all the paired data. If we wanted to plot points themselves, we would use a scatterplot. To do this, we can simply replace the `.plot()` function with the `.scatter()` function. 

```python
#scatter plot
plt.scatter(XCoords, YCoords, label="Linear") # linear data series
plt.scatter(XCoords, YCoordsQuad, label="Quadratic") # quadratic data series
plt.scatter(XCoords, YCoordsCub, label="Cubic")
plt.title("Scatterplot") # add main title
plt.xlabel('X coordinates') # add X axis labels
plt.ylabel('Y coordinates') # add Y axis labels
plt.legend() # add legend
```
![fig4](https://hackmd.io/_uploads/BkBEbJu-fx.png)

### Exercise 11
When trying to generate a line graph, the code below produces an error following the `.plot()` call. What is the most likely source of the error?

```python
#define X axis variable (sampling area)
area = [100, 200, 300, 400, 500, 600, 700, 800, 900, 1000]
#define Y axis variable (species count)
speciesCount = [3, 18, 31, 38, 43, 44, 45]
#scatterplot
plt.scatter(area, speciesCount)
```

### Exercise 12
The multi-series line graph below appears to have a misformatted legend. How might you fix this so that data series can be identified?

```python
#define X axis variable (sampling area)
area = [100, 200, 300, 400, 500, 600, 700, 800, 900, 1000]
#define Y axis variables (species counts)
speciesCount = [3, 18, 31, 38, 43, 44, 45,45,45,45]
speciesCount2 = [15,26,33,39,44,46,46,46,46,46]

#plot
plt.scatter(area, speciesCount) # linear data series
plt.scatter(area, speciesCount2) # quadratic data series
plt.title("Species accumulation curve") # add main title
plt.xlabel(r'Area sampled (km$\mathregular{^2}$)') # add X axis labels
plt.ylabel('Species count') # add Y axis labels
plt.legend(loc="upper left") # add legend in upper left
```
![figExercise13](https://hackmd.io/_uploads/rJL1w5ObGx.png)

### 2.3 Working with combined discrete and continuous data: bar graphs 
So far we've only looked at continuous data, but what if we wanted to combine it with our discrete data? This could include grouping our continuous variables (ex. height of students) with demographic information (ex. gender, grade level) which would be the discrete variables. For datasets which combine discrete and continuous data, bar graphs and boxplots allow for straightforward comparison of a continuous variable across these discrete categories. 

To begin with, let's generate a dataset of continuous variables and discrete variables. Here, we'll assign each of our continuous variables a level which increments sequentially by 1. We will also introduce a new library here, `numpy`, which provides some useful utility for performing various numerical operations.

```python
#import numpy(
import numpy as np

#generate variables
YBar = np.random.randint(low=10,high=20,size=5)# continuous variable (Y): generate 5 random integers between 10 and 20
levels = np.arange(start=0,stop=len(YBar),step=1) # discrete variable (X): generate N evenly spaced integers, where N is the number of elements in the Y array 
```
Note that although we are thinking of our X variable as a discrete variable, we model it here as a integer. The primary reason for this is to simplify the process of changing positions of our bars on the X axis - this will be handy when we plot multiple series. 

To turn this into a barplot, we'll call the `.bar()` function.

```python
# generate barplot
plt.bar(levels, YBar,color='purple') # plot bars
plt.ylabel('Var') # add y axis label
plt.title('Barplot') # add title
plt.xticks(levels, ('Level1', 'Level2', 'Level3', 'Level4', 'Level5')) # change X axis ticks
plt.yticks(np.arange(start=0,stop=20,step=2)) # change Y axis ticks (0 - 20, intervals of 2)
```
![fig5](https://hackmd.io/_uploads/ryrCAeFWGe.png)

We can plot multiple data series in a side-by-side manner by slightly changing the X-axis positioning of our bars. Let's define a variable, `barWidth`, which will describe the relative width of our bars. Since the default width of bars is one, we'll then shift the bars for each series either `barWidth / 2` to the left or right of the X axis tick.

```python
#generate second data series
YBar2 = np.random.randint(low=15,high=25,size=5) # generate 5 random integers between 15 and 25

#define bar width
barWidth = 0.25

#generate multi-series barplot
plt.bar(levels-(barWidth/2), YBar,width=barWidth,color='purple',label='Series1') # plot bars for series 1
plt.bar(levels+(barWidth/2), YBar2,width=barWidth,color='yellow',label='Series2') # plot bars for series 2
plt.ylabel('Var') # add y axis label
plt.title('Multi-series barplot') # add title
plt.xticks(levels, ('Level1', 'Level2', 'Level3', 'Level4', 'Level5')) # change X axis ticks
plt.yticks(np.arange(start=0,stop=30,step=3)) # change Y axis ticks (0 - 30, intervals of 3)
plt.legend() # add legend
```
![fig6](https://hackmd.io/_uploads/SkeiH-Fbfg.png)

We can do other cool things like arrange these vertically to create a stacked bar chart and error bars.

```python
YError1 = np.random.uniform(low=1, high=5, size=5) # randomly sample 5 floats (real numbers) between 1 and 5
YError2 = np.random.uniform(low=1, high=5, size=5) # randomly sample 5 floats (real numbers) between 1 and 5

#generate stacked bar chart
plt.bar(levels, YBar,width=barWidth,yerr=YError1,color='purple',label='Series1') # plot bars for series 1
plt.bar(levels, YBar2,width=barWidth,bottom=YBar,yerr=YError2,color='yellow',label='Series2') # plot bars for series 2
plt.ylabel('Var') # add y axis label
plt.title('Stacked barplot') # add title
plt.xticks(levels, ('Level1', 'Level2', 'Level3', 'Level4', 'Level5')) # change X axis ticks
plt.yticks(np.arange(start=0,stop=20,step=2)) # change Y axis ticks (0 - 40, intervals of 5)
plt.legend()# add legend
```
![fig7](https://hackmd.io/_uploads/SyIHU-FZGx.png)

### Exercise 13
Based on the code associated with the above plot, can you predict what keyword arguments are associated with 
1. Changing the vertical positioning of bars and
2. Adding standard error bars?

### 2.4 Working with combined discrete and continuous data: boxplots

If our discrete levels/categories are associated with distributions, boxplots are a great way to visualize and compare these distributions.

Let's start by sampling from some random normal distributions.

```python
#sampling from random normal distributions
YBox1 = np.random.normal(loc=100,scale=20,size=100) # sample 100 points from normal distribution with mean of 100 and standard deviation of 20
YBox2 = np.random.normal(loc=125,scale=10,size=100) # sample 100 points from normal distribution with mean of 125 and standard deviation of 10
YBox3 = np.random.normal(loc=75,scale=30,size=100) # sample 100 points from normal distribution with mean of 75 and standard deviation of 30
```
### Exercise 14
Complete the code below to sample 500 points from a normal distribution with mean of 30 and standard deviation of 6.
```python
np.____.____(____=6,____=500,____=30)
```

We'll then put these generated lists within another list. This creates a nested list because the lists are nested in another list.

```python
# nest list in list
YBoxAll = [YBox1,YBox2,YBox3]
```

When we generate our boxplots, each array within the nested list will now be treated as a separate data series.

```python
#generate boxplot
plt.boxplot(YBoxAll, tick_labels=['SeriesA', 'SeriesB', 'SeriesC']) # plot data series
plt.ylabel('Var') # Y axis label
plt.title('Boxplot') # Main title
```
![fig8](https://hackmd.io/_uploads/S1vwQzKbGx.png)

By default, the horizontal lines inside each of our boxes represent median values of our distributions, with the lower and upper bounds of the box defining the 25th and 75th percentiles, respectively. Whiskers stretch out to either the most extreme datapoint, or 1.5x the inter-quartile range (whichever is less).

We can combine the `.boxplot()` function and the `.scatter()` function to overlay our raw data points on top of the boxplot.

```python
plt.boxplot(YBoxAll, tick_labels=['SeriesA', 'SeriesB', 'SeriesC'])# plot data series as boxplot
plt.scatter([1]*100,YBoxAll[0], color='skyblue') # add points from first data series, give them all the same X coordinate (1)
plt.scatter([2]*100,YBoxAll[1], color='skyblue') # add points from second data series, give them all the same X coordinate (2)
plt.scatter([3]*100,YBoxAll[2], color='skyblue') # add points from second data series, give them all the same X coordinate (3)
plt.ylabel('Var') # Y axis label
plt.title('Boxplot with overlayed points') # Main title
```
![fig9](https://hackmd.io/_uploads/B1yjVGKbGx.png)

You'll notice that our points are all overlaying one another, which doesn't look very pretty. We can make this a little better by adding some small variance to the X axis coordinates of our data points (a "jitter"). At the same time, we'll also make the points a little smaller and add some transparancy to them setting an `alpha` parameter.

```python
plt.boxplot(YBoxAll, tick_labels=['SeriesA', 'SeriesB', 'SeriesC']) # plot data series as boxplot
plt.scatter(np.random.uniform(low=0.75,high=1.25,size=100), # add points from first data series, scatter them around X coord (1)
            YBoxAll[0],alpha=0.5,s=10, color='skyblue'), #add transparency (alpha=0.5), change size (s=10)
plt.scatter(np.random.uniform(low=1.75,high=2.25,size=100), # add points from second data series, scatter them around X coord (2)
            YBoxAll[1],alpha=0.5,s=10, color='skyblue') # add transparency (alpha=0.5), change size (s=10)
plt.scatter(np.random.uniform(low=2.75,high=3.25,size=100), # add points from third data series, scatter them around X coord (3)
            YBoxAll[2],alpha=0.5,s=10, color='skyblue')# add transparency (alpha=0.5), change size (s=10)
plt.ylabel('Var')# Y axis label
plt.title('Boxplot with overlayed and jittered points')# main title
```
![fig10](https://hackmd.io/_uploads/BJSCUGFWzl.png)

### Exercise 15
In the above boxplot, how might we change the 'breadth' over which our raw data points are scattered on the X axis?

## Part 3: Plotting from a Pandas dataframe
Everything we've worked through has been oriented around  datasets represented as lists. What is actually probably more common is for us to work with datasets stored as dataframes, so let's see how we might translate some of what we've done so far into this context!

Let's start by loading in the `gapminder` dataset we've previously worked with.

```python
#import pandas library
import pandas as pd

#load in data
dat = pd.read_csv('data/gapminder_all.csv', index_col='country')
```

### 3.1: Line plots for trends within rows across columns
We can pull out specific columns and rows to plot specific subsets of data. In this case, let's plot the trends in GDP over time for the United States and United Kingdom. 

```python
#extract columns
US_UK_GDP=dat.loc[['United States','United Kingdom'], 'gdpPercap_1952':'gdpPercap_2007'].T # subset to US and UK GDP columns, transpose so that rows are GDP and columns are countries
US_UK_GDP.index = US_UK_GDP.index.str.replace('gdpPercap_', '') # make rownames a little more tidy, substring to just year
```

Note that we transpose our series after subsetting. This is an important step, as `matplotlib` expects columns to correspond to different series.

Let's generate a line plot in a similar fashion to how we've done before!

```python
#line plot of gdp over time
plt.plot(US_UK_GDP.index, # use index of series (year) as X coordinates
         US_UK_GDP.loc[:,'United States'], # define series as US column
         label='United States')
plt.plot(US_UK_GDP.index, # use index of series (year) as X coordinates
         US_UK_GDP.loc[:,'United Kingdom'], # define series as UK column
         label='United Kingdom')
plt.title("Trends in GDP over time") # add main title
plt.xlabel('Year') # add X axis labels
plt.ylabel('GDP per capita ($)') # add Y axis labels
plt.legend() # add legend
```
![fig11](https://hackmd.io/_uploads/r1aOImKbGg.png)

When working with dataframes, we also have the option of calling the `.plot()` function on the dataframe itself, which simplifies things greatly. Note that we now don't have to worry about defining and plotting series separately, as columns will automatically be interpreted as separate series.

```python
#line plot of GDP over time
US_UK_GDP.plot() #plot all series
plt.title("Trends in GDP over time") # add main title
plt.xlabel('Year') # add X axis labels
plt.ylabel('GDP per capita ($)') # add Y axis labels
plt.legend() # add legend
```
![fig12](https://hackmd.io/_uploads/SJIFwmFbzl.png)

This allows us to generate complex, multi-series plots quickly and easily. For example, we can now visualize GDP trends across all European nations in a fairly straightforward manner.
```python
#extract Europe columns
EuropeGDP=dat.loc[dat['continent'] == 'Europe', 'gdpPercap_1952':'gdpPercap_2007'].T
EuropeGDP.index = EuropeGDP.index.str.replace('gdpPercap_', '') # tidy rownames

#plot trends
EuropeGDP.plot() # plot all series
plt.title("Trends in GDP over time") # add main title
plt.xlabel('Year') # add X axis labels
plt.ylabel('GDP per capita ($)') # add Y axis labels
plt.legend(bbox_to_anchor=(1.05, 1), loc='upper left',ncol=3) #shift legend outside of plot, spread series labels across three columns
```
![fig13](https://hackmd.io/_uploads/HyYdKmFZfl.png)

### Exercise 16
Complete the code below to generate a line graph visualizing trends in life expectancy for countries with GDP per capita in 2007 that is greater than or equal to $30000.

```python
#extract columns
lifeExp=dat.loc[_________, _________].___
lifeExp.index = lifeExp.index.str.replace('_______', '') # tidy rownames

#plot trends
lifeExp.plot() # plot all series
plt.title("Trends in life expectancy") # add main title
plt.____('Year') 
plt.____('Life expectancy (years)')
plt.legend(bbox_to_anchor=(1.05, 1), loc='upper left',____=3) 
```

### 3.2: Scatter plots for relationships between columns

We sometimes will be interested in the relationships between different continuous variables that are present in our dataframes, and scatterplots are a great way to pick up on any correlations that might exist.

We can generate scatter plots from our dataframe columns by adding `.scatter()` to our `df.plot` call. For example, let's take a look at how we might visualize the relationship between GDP and life expectancy in 2007.

```python
#generate scatterplot
dat.plot.scatter(x="gdpPercap_2007", y="lifeExp_2007", title="GDP per capita vs. life expectancy")
plt.xlabel('GDP per capita ($)') 
plt.ylabel('Life expectancy (years)')
```
![fig14](https://hackmd.io/_uploads/S1wc74K-fe.png)

For more complicated scenarios, we can always resort back to `plt.scatter()`. Below, we expand on the above plot by coloring based on continent of origin and point sizes scaled by transformed population size.

```python 
#iterate through continents and plot
for continent in dat['continent'].unique():
    plt.scatter(x=dat.loc[dat['continent'] == continent,"gdpPercap_2007"], # GDP for current continent
                y=dat.loc[dat['continent'] == continent,"lifeExp_2007"], # life expectancy for current continent
                s=dat.loc[dat['continent'] == continent,"pop_2007"]/100000, # scale point size based on transformed population size for current continent
                alpha=0.25,label=continent) # set transparency (alpha=0.25) and label

#customize plot
plt.title("Trends in life expectancy across continents") # add main title
plt.xlabel('GDP per capia ($)')  # add x axis label
plt.ylabel('Life expectancy (years)') #add y axis label
leg = plt.legend(loc='lower right') #legend
# Override the size (s) of each point inside the legend box to 30 points
for handle in leg.legend_handles:
    handle.set_sizes([30])
```
![fig15](https://hackmd.io/_uploads/SyMmXSYWzx.png)

### 3.3 Boxplots to compare across discrete variables

Finally, we may want to compare some of our continuous variables across discrete variables. For example, below we compare two continuous variables (GDP at 2 separate time points) across continents. We first start by building nested lists corresponding with each of our continuous variables, then plot each as a separate series.

``` python
#build nested lists corresponding with continents
pop1952List=dat.groupby('continent')['gdpPercap_1952'].apply(list).tolist()
pop2007List=dat.groupby('continent')['gdpPercap_2007'].apply(list).tolist()

#Plot first series (GDP 1952) with left offset
box1952 = plt.boxplot(pop1952List, positions=np.arange(5) - 0.15, 
                         widths=0.25, patch_artist=True,)

#Plot second series (GDP 2007) with a right offset
box2007 = plt.boxplot(pop2007List, positions=np.arange(5) + 0.15, 
                           widths=0.25, patch_artist=True)

#Add fill color
for box in box1952['boxes']:
    box.set_facecolor('purple')
for box in box2007['boxes']:
    box.set_facecolor('yellow')

#customize plot
plt.xticks(np.arange(5),dat['continent'].unique()) # set  tick positions and labels
plt.xlim(-1, 5) # X axis limits
plt.ylabel("GDP per capita ($)") # Y axis label
plt.title("GDP across continents and time") # add main title
plt.legend([box1952['boxes'][0], box2007['boxes'][0]], ['1952', '2007']) # Legend
```
![fig16](https://hackmd.io/_uploads/BkvpgLY-zg.png)

### 3.4 Basic statistics with `scipy`
In addition to generating plots, libraries available in Python also facilitate easy application of various statistical analyses. Here, let's walk through a couple things that we can do in the `scipy` library, using out `gapminder` data frame as an example dataset.

#### Mean, variance and standard deviation
We've previously learnt in our morning session how to calculate some basic statistics on a subset of columns from a dataframe. We can also calculate statistics on a single column as well.

```python
#calculate mean, min, max on 
pop2007Max = dat['pop_2007'].max()
pop2007Min = dat['pop_2007'].min()
pop2007Mean = dat['pop_2007'].mean()

#print variables
print('2007 population size minimum:',pop2007Min,
      '\n2007 population size maximum:',pop2007Max,
      '\n2007 population size mean:',pop2007Mean)
```

Notice above in the print statement that we include a **control character**, `\n`, which inserts a new line into the print statement. These control characters can be inserted within print statements to generate complex outputs like above.

With the help of `scipy`, we can start to calculate additional statistics, like standard deviation. The way that this is implemented in the library is through the `.tstd` function, which calculates standard deviation, excluding values outside of a defined range (set by the `limits` argument). 

Here, let's calculate the standard deviation of the 2007 population size column, excluding any values falling below the 5th percentile and above the 95th percentile.

```python
#get percentile values using np.percentile
lowerBound = np.percentile(dat['pop_2007'], 5) #5th percentile
upperBound = np.percentile(dat['pop_2007'], 95) #95

#import stats module from scipy library
from scipy import stats

#calculate standard deviation
stats.tstd(dat['pop_2007'],limits=(lowerBound,upperBound))
```

We can also perform analyses across pairs of columns such as linear regression, using just a single command! For example, let's look at the relationship between population size at the first timepoint (1952) and at the last timepoint (2007). 

```python
#perform linear regression, save to variable
regressPopSize = stats.linregress(dat['pop_1952'],dat['pop_2007'])
```

From this object, we can pull out statistics that are of interest to us, like the slope and intercept of our regression line, as well as the Pearson correlation coefficient between our two datasets!

```python
#slope
print("Slope:",regressPopSize.slope)
#intercept
print("Intercept:",regressPopSize.intercept)
#correlation
print("Correlation:",regressPopSize.rvalue)
```

We can plot this linear trend line alongside our scatterplot as below.

```python
plt.scatter(x=dat['pop_1952'], y=dat['pop_2007'])
#add trendline
plt.plot(dat['pop_1952'], regressPopSize.slope * dat['pop_1952'] + regressPopSize.intercept, 
         color="red", linestyle=':')
plt.title("Correaltion between population size in 1952 and 2007") # add main title
plt.xlabel('1952 population size')  #X axis label
plt.ylabel('2007 population size') #Y axis label
plt.text(x=3e8, y=0.6e9, s=f"Pearson's R: {round(regressPopSize.rvalue,2)}") #add Pearson's R
```

For more formal hypothesis testing, `scipy` also has functions associated with a variety of different statistical tests. For example, below we perform a two sample T-test comparing starting and ending GDP per capita.

```python
#perform t test on 1952 and 2007 population sizes (Unequal variance)
gdpTTest = stats.ttest_ind(dat['gdpPercap_1952'], dat['gdpPercap_2007'], equal_var=False)
#print statement
print(f"T-statistic: {gdpTTest.statistic}, P-value: {gdpTTest.pvalue}")
```

## Part 4: Exercise answers
### Exercise 11 
The lists associated with X and Y coordinates don't have the same length - one list has more elements than the other. Because `.plot()` assumes a paired structure in its lists, it isn't able to reconcile lists with unequal lengths. Intuitively, this makes sense because there is now no clear, logical way to map elements across lists.

### Exercise 12
The legend isn't being displayed correctly because no labels were assigned to the data series in the `.scatter()` call. If we rerun the code with labels added, the legend will be present in the upper left corner (where the white square box currently is).

### Exercise 13
1. To change the Y coordinate where main bars begin, we can use the `bottom` argument. Setting `bottom` equal to the values of the other series stacks bars on top of one another.
2. Symetrical error bars for main bars can be added using the `yerr` argument. The expected input is an array or list of the same length as the number of bars

### Exercise 14
```python
np.random.normal(scale=6,size=500,loc=30)
```

### Exercise 15
The breadth of our jitter is controlled based on the `low` and `high` arguments that we provide to our `np.random.uniform()` calls. 

By moving the values assigned to these arguments closer to the true X coordinate they are centered around, we can move the lower and upper bounds of our possible X coordinates closer to that central coordinate, narrowing the spread of our points. 

### Exercise 16
```python
#extract columns
lifeExp=dat.loc[dat['gdpPercap_2007'] >= 30000, 'lifeExp_1952':'lifeExp_2007'].T
lifeExp.index = lifeExp.index.str.replace('lifeExp_', '') # tidy rownames

#plot trends
lifeExp.plot() # plot all series
plt.title("Trends in life expectancy") # add main title
plt.xlabel('Year') 
plt.ylabel('Life expectancy (years)')
plt.legend(bbox_to_anchor=(1.05, 1), loc='upper left',ncol=3) 
```


