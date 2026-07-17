---
title: 'Day 2 morning - Programming in Python: Introduction, Variables, and DataFrames'
layout: home
nav_order: 3
---

# Plotting and Programming in Python: Introduction, Variables, and DataFrames

**Based on:** Software Carpentry, *Plotting and Programming in Python*, Gapminder instructor materials: <https://swcarpentry.github.io/python-novice-gapminder/instructor/index.html>

**Notebook format:** Markdown notebook with explanatory text and Python code blocks. You can paste sections into a Jupyter Notebook, or use this as a teaching handout.

---

## Learning Goals

By the end of this notebook, learners should be able to:

1. Explain what JupyterLab and Jupyter Notebooks are used for.
2. Create and run code cells and Markdown cells.
3. Store values in Python variables and use those variables in calculations.
4. Display output with `print()`.
5. Understand common variable-related errors, especially `NameError`.
6. Use string indexing and slicing.
7. Import the Pandas library.
8. Read Gapminder CSV files into Pandas DataFrames.
9. Inspect DataFrame structure with `.info()`, `.columns`, `.T`, and `.describe()`.
10. Select rows, columns, and individual values using `.loc` and `.iloc`.
11. Filter tabular data using Boolean conditions.

---

## Required Setup

This lesson assumes that learners have Python 3 installed and have downloaded the Gapminder lesson data. The expected folder structure is:

```text
project-folder/
├── data/
│   ├── gapminder_gdp_oceania.csv
│   ├── gapminder_gdp_europe.csv
│   ├── gapminder_gdp_americas.csv
│   └── gapminder_all.csv
└── notebook.ipynb
```

In a Jupyter Notebook, your notebook should be started from the same top-level folder that contains the `data/` directory. That is why examples use paths such as:

```python
'data/gapminder_gdp_oceania.csv'
```

Let's start by using the same JupyterLite server as yesterday: [ngs-docs.github.io/2026-summer-bcp-101-jupyterlite-demo/](https://ngs-docs.github.io/2026-summer-bcp-101-jupyterlite-demo/)

---

# Part 1 — Introduction to JupyterLite (Again), JupyterLab and Notebooks

## 1.1 The Difference between JupyterLite and JupyterLab

JupyterLite and JuypterLab are two different tools that we'll be using throughout this workshop.

JupyterLab is the notebook workspace where we will write and run Python code. It lets us open notebooks, write notes, run code cells, view results, and work with data files all in one place.

JupyterLite is a browser-based version of Jupyter that lets us use JupyterLab without installing anything on our computer. Instead of setting up Python and Jupyter locally, we can open a link in a web browser and start working right away.

In this workshop, we will be using JupyterLab notebooks through JupyterLite. That means the notebook interface will look like JupyterLab, but it will run directly in the browser using JupyterLite.

## 1.2 What is JupyterLab?

JupyterLab is an interactive environment for writing, running, and documenting code. It lets you combine:

- Python code
- output from that code
- tables
- plots
- explanatory text
- Markdown notes

This makes it especially useful for data analysis, because you can keep the code, results, and interpretation together in one document.

A Jupyter Notebook is made of **cells**. The two main cell types are:

| Cell type | Purpose |
|---|---|
| Code cell | Runs Python code |
| Markdown cell | Stores formatted notes, headings, lists, links, and explanations |

## 1.3 Starting JupyterLab

We'll use JupyterLite to open a JupyerLab notebook. We can use this [link](https://ngs-docs.github.io/2026-summer-bcp-101-jupyterlite/) to directly access JupyterLite. It can also be found on our Github pages [here](https://github.com/ngs-docs/2026-summer-bcp-101-jupyterlite) and opened by clicking the link. From there, we'll open a JupyterLab notebook using the first icon under Notebook. 

![bcp101_jupyterlab](https://hackmd.io/_uploads/S1j9E0FZMe.jpg)

This launches a local server and opens JupyterLab in your web browser. The browser is the interface, but the Python code runs through the Jupyter server and kernel.

## 1.4 Managing a Notebook

Once opened, we can see our notebook on the right, and a few buttoms on the right. The first, shaped like a folder, is our directory which is where our notebook is housed. It is currently named "Untitled.ipynb", but we can rename it by right-clicking on the file and selecting "Rename". Let's rename it to something more intuitive, like:

```text
bcp101_day2_morning_intro_python.ipynb
```

## 1.5 Command Mode vs. Edit Mode

Jupyter notebooks have two important modes:

| Mode | How to enter | What it does |
|---|---|---|
| Command mode | Press `Esc` | Lets you manage cells |
| Edit mode | Press `Enter`/`Return` | Lets you type inside a cell |

Useful shortcuts in Command mode:

| Shortcut | Action |
|---|---|
| `a` | Add a cell above |
| `b` | Add a cell below |
| `x` | Delete selected cell |
| `z` | Undo last cell action |
| `m` | Convert cell to Markdown |
| `y` | Convert cell to Code |
| `Shift` + `Enter` | Run selected cell |

## 1.6 Markdown Basics

Markdown is a lightweight way to format text. Try putting the following into a Markdown cell:

```markdown
# My Gapminder Notebook

## Goals

- Learn basic Python syntax
- Store values in variables
- Read tabular data with Pandas
- Select rows and columns from a DataFrame

[Software Carpentry](https://software-carpentry.org)
```

When you run the Markdown cell, Jupyter renders it as formatted text.

### Practice: Markdown Cell

Create a Markdown cell with:

1. A level-1 heading with the title of your notebook.
2. A short paragraph describing what Gapminder data contains.
3. A bullet list of three things you want to learn.

---

# Part 2 — Variables and Assignment

## 2.1 What is a Variable?

A **variable** is a name that stores a value. In Python, the assignment operator `=` assigns the value on the right to the variable name on the left.

```python
age = 42
first_name = 'Ahmed'
```

Here:

- `age` stores the integer value `42`
- `first_name` stores the string value `'Ahmed'`

There are some rules about what can and cannot be a variable. For example, Python variable names:

- can contain letters, numbers, and underscores
- cannot start with a number
- are case-sensitive
- should be meaningful

Valid examples:

```python
age = 42
first_name = 'Ahmed'
gdp_per_capita = 10039.59
sample_count = 12
```

Invalid or poor examples:

```python
# Invalid: starts with a number
1st_name = 'Ahmed'

# Valid, but not descriptive
x = 42

# Valid, but confusing because capitalization matters. These are two different variables. 
Age = 42
age = 55
```

## 2.2 Variable Types 

In Python, variables can store different kinds of information. The kind of information stored in a variable is called its **type**.

For example, a variable can store a number, a word, a sentence, or a true/false value. Python uses the value assigned to the variable to figure out what type it is.

Some common variable types are:

| Type    | Name    | Description                   | Example                  |
| ------- | ------- | ----------------------------- | ------------------------ |
| `int`   | integer | A whole number                | `year = 2024`            |
| `float` | float   | A number with a decimal point | `life_expectancy = 72.5` |
| `str`   | string  | Any amount of text made up of characters, such as letters, numbers, punctuation, or spaces           | `country = "Canada"`, `long_sentence = "This is also a string."`     |
| `bool`  | boolean | A true or false value         | `is_large = True`        |


Each variable stores a different type of information. The variable `year` stores a whole number, `life_expectancy` stores a decimal number, `country` and `long_sentence` store text, and `is_large` stores a true/false value.

We can check the type of a variable using the `type()` function:

```python
type(country)
```

This will show us that `country` is a string, or `str`, because it stores text. Importantly, if we assign a number in quotations, then it becomes a string and not an integer, or `int`, as shown below.

```python
is_number = 1
type(is_number)
```
```python
is_string = "1"
type(is_string)
```

Understanding variable types is useful because Python treats different types of information in different ways. For example, Python can do math with numbers, but text values need to be handled differently.


## 2.3 Displaying Values with `print()`

The `print()` function displays values as text.

```python
age = 42
first_name = 'Ahmed'

print(first_name, 'is', age, 'years old.')
```

Expected output:

```text
Ahmed is 42 years old
```

`print()` automatically adds spaces between comma-separated items and moves to a new line at the end.

### Storing Strings with Other Variables

In the printed statement `Ahmed is 42 years old`, we used several variables alongside some text. But what if we wanted to store this in another variable? If we tried to put this in a variable, such as:

```python
variable = first_name, 'is', age, 'years old.'
```

It would return this as a list of different elements instead of a single printed statement. 

```python
(first_name, 'is', age, 'years old.')
```

If we wanted to keep these as one string, we can use a **f-string** which lets us call the value that the variable is storing instead of the variable itself. It is denoted with a particular syntax as shown here:

```python
f"{first_name} is {age} years old."
```

## 2.4 Variables Must Exist Before Use

If you try to use a variable before assigning it, Python raises a `NameError`.

```python
print(last_name)
```

Expected error:

```text
NameError: name 'last_name' is not defined
```

This often means one of two things:

1. The variable was never created.
2. The variable name was misspelled.

### Important Jupyter Note: Execution Order Matters

In a notebook, Python remembers cells that have already been run. The order in which cells are **executed** matters more than the order in which they appear.

For example, this cell will fail if run first:

```python
print(myval)
```

But this cell creates the variable:

```python
myval = 1
```

If you run the assignment cell first and then run `print(myval)`, it works. To check that a notebook runs cleanly from top to bottom, use the icon showing two arrows. If you have over it, it says "Restart the kernal and run all cells". This ensures everything is ran in the correct order. 


## 2.5 Updating Variables

Variables can be used in calculations.

```python
age = 42
age = age + 3
print('Age in three years:', age)
```

Expected output:

```text
Age in three years: 45
```

This line:

```python
age = age + 3
```

means: take the current value of `age`, add `3`, and assign the result back to `age`.

## 2.6 Creating a List

What if we have multiple values? Could we assign them to a single variable? We can using a **list**. Lists are useful when we want to keep related pieces of information together.

For example, we could store several country names in one list:

```python
countries = ["Canada", "Mexico", "United States", "Brazil"]
```

This list contains four values. Each value in a list is called an **element**.

Lists are written using square brackets `[]`, and each element is separated by a comma. The elements are the same types we just discussed (integer, float, string, boolean), and can be different from each other in the same list. 

```python
lucky_items = ["rabbit's foot", "four-leaf clover", 42]
```

However, most of the time we use lists to store values that are related to each other so it's good practice to keep them as the same type.

## 2.7 Accessing Elements Through Indices 

Each element in a list has a position, called an **index**.

In Python, counting starts at **0**, not 1. This means the first element is at index `0`, the second element is at index `1`, and so on.

```python
countries = ["Canada", "Mexico", "United States", "Brazil"]

countries[0]
```

This gives us:

```python
"Canada"
```

We can use a different index to get a different element:

```python
countries[2]
```

This gives us:

```python
"United States"
```

Even though `"United States"` is the third item in the list, it has index `2` because Python starts counting at 0.

### Negative Indexing

Python can also count from the end of a list using **negative numbers**.

```python
countries[-1]
```

This gives us the last element:

```python
"Brazil"
```

We can also get the second-to-last element:

```python
countries[-2]
```

This gives us:

```python
"United States"
```

Negative indexing is useful when we want to access values at the end of a list without knowing exactly how long the list is.

## 2.9 Adding and Removing Elements from a List

After we create a list, we can change it by adding or removing elements.

For these examples, let's continue with our list of countries:

```python
countries = ["Canada", "Mexico", "United States", "Brazil"]
```

### Adding an Element

We can add a new element to the end of a list using `.append()`.

```python
countries.append("China")
```

Now the list contains five countries:


```python
["Canada", "Mexico", "United States", "Brazil", "China"]
```

Note that the `.append()` method changes the original list. It does not create a new list.

### Removing an Element

We can remove an element from a list using `.remove()`.

```python
countries.remove("Mexico")
```

Now the list no longer contains `"Mexico"`:

```python
countries
```

```python
["Canada", "United States", "Brazil", "China"]
```

When using `.remove()`, we give Python the value that we want to remove. Notice that we didn't have to specify the location, but we can by using that element's index and `.pop()`. This would give the same result:

```python
countries.pop(1)
```

## 2.10 Operations on Lists Using Functions

After we created our list, we often want to perform some calculation or modify the values somehow. Fortunately, we can easily do this with **functions**. These are the special commands we've been calling to do each operation. Here, we'll explore some available for lists, but a bigger list is available [here](https://docs.python.org/3.14/tutorial/datastructures.html).

We will start with a list of life expectancy values:

```python
life_expectancies = [72.5, 80.1, 67.9, 75.4]
```

This list contains four numbers of the data type `float`. Each number is one element in the list.

### Get Length of List Using `len()`

We can use `len()` to count how many elements are in a list.

```python
len(life_expectancies)
```

This gives us:

```python
4
```

This list has four values.

### Add Values Together Using `sum()`

We can use `sum()` to add all of the values in a list.

```python
sum(life_expectancies)
```

This gives us:

```python
295.9
```

This is the total of all values in the list.


### Find the Smallest and Largest Values 

We can use `min()` to find the smallest value in a list.

```python
min(life_expectancies)
```

This gives us:

```python
67.9
```

The smallest life expectancy value in the list is `67.9`.

Similarly, we can use `max()` to find the largest value in a list. 

```python
max(life_expectancies)
```

This gives us:

```python
80.1
```

This is the largest value in the list. 

## 2.11 Additional Operations on Lists  

Even if the function doesn't exist, we can easily perform the calculation by combining existing functions with another operation. For example, Python does not have a built-in `average()` function, but we can calculate an average using `sum()` and `len()`.

```python
average_life_expectancy = sum(life_expectancies) / len(life_expectancies)
average_life_expectancy
```

This gives us:

```python
73.975
```

This calculation adds all values together and then divides by the number of values.


### Modifying Each Value in a List Using `for` Loops

Sometimes we want to do the same calculation to every value in a list or modify it in a particular way. If there isn't an existing function, we can perform this using a `for` loop, which loops through each element in our list and performs the same operation. 

For example, we might print every element one at a time. To do this, we'll need to follow a basic syntax to setup our `for` loop. 

First, we need a temporary variable to represent each element in our `for` loop. Because we can't perform the operation on the entire list, we'll need to call each element one at a time. Here, we call this temporary variable `value`, and specify that we want every element in our list using:

```python
for value in life_expectancies
```

Next, we need to perform the operation to every element. It uses the same structure as our other operations, but we have to indent the operation to specify that the operation is occuring within the for loop. We also add a colon to the first line. 

```python
for value in life_expectancies:
    print("I will live", value, "years.")
```

This should print: 

```python
I will live 72.5 years.
I will live 80.1 years.
I will live 67.9 years.
I will live 75.4 years.
```

Suppose we wanted to keep each of these print statements as another list. To do that, we'll need to create an empty list, and append each element to it. We'll also use the **f-string** to reference the value that variable is representing, and not just the variable itself. 

```python
life_expectancies_sentence = []

for value in life_expectancies:
    life_expectancies_sentence.append(f"I will live {value} years.")
```

If we looked out our new list:
```
life_expectancies_sentence
```

We would see it now contains our modified strings.

```python
['I will live 72.5 years.',
 'I will live 80.1 years.',
 'I will live 67.9 years.',
 'I will live 75.4 years.']
```

The original list did not change. We created a new list with the results.

## 2.12 Practice: Variables

*Woah, we covered a lot!* 

Let's try a few exercises and see how well we do. 

### Exercise 1 — Create and Print Variables

Create variables for:

- your first name
- your favorite organism
- the number of samples in a small dataset

Then print a sentence using all three variables.

### Exercise 2 — Working with Lists

Given this list of country names:

```python
countries = ["Canada", "Mexico", "United States", "Brazil"]
```

Predict the result of each expression:

```python
countries[0]
countries[2]
countries[-1]
countries[0:2]
countries[2:]
countries[:]
```

---

# Part 3 — Reading Tabular Data into Pandas DataFrames

## 3.1 What is Pandas?

Pandas is a Python library for working with tabular data. It is especially useful for CSV files, spreadsheets, and datasets where observations are arranged in rows and variables are arranged in columns.

The standard import is:

```python
import pandas as pd
```

The alias `pd` is a common convention that makes Pandas commands shorter to type.

## 3.2 What is a DataFrame?

A **DataFrame** is a two-dimensional table.

- Rows usually represent observations.
- Columns usually represent variables.
- Each column has a name.
- Different columns can contain different data types.

For Gapminder GDP data:

- each row is a country
- each column is GDP per capita for a particular year

## 3.3 Discrete and Continuous Data

When we work with data, it is helpful to think about what kind of information each column contains.

**Discrete data** are values that represent separate categories or countable groups. In the Gapminder dataset, `country` is discrete because each value is a separate country name, such as `Albania` or `Denmark`. The `continent` column in `gapminder_all.csv` is also discrete because each value belongs to a category, such as `Europe`, `Asia`, or `Americas`.

**Continuous data** are numeric values that can be measured on a scale. In the Gapminder dataset, columns such as `gdpPercap_1952` or `gdpPercap_2007` are continuous because GDP per capita can take many possible numeric values, including values with decimals.

A simple way to remember the difference is:

| Data type | Meaning | Gapminder example |
|---|---|---|
| Discrete | Separate categories or countable values | `country`, `continent` |
| Continuous | Measured numeric values | `gdpPercap_1952`, `gdpPercap_2007` |

This distinction matters because we often summarize and plot discrete and continuous data in different ways.


## 3.4 Read a CSV File

Read the Oceania GDP data:

```python
import pandas as pd

# Read the CSV file into a DataFrame
data_oceania = pd.read_csv('data/gapminder_gdp_oceania.csv')

# Display the DataFrame
print(data_oceania)
```

This creates a DataFrame variable named `data_oceania`.

## 3.5 File Paths and Common Errors

The path:

```python
data/gapminder_gdp_oceania.csv
```

means:

1. Start in the current working directory.
2. Go into the `data/` folder.
3. Open the file named `gapminder_gdp_oceania.csv`.

If the file path is wrong, you may see:

```text
FileNotFoundError: [Errno 2] No such file or directory
```

To debug this:

```python
import os
print(os.getcwd())
print(os.listdir())
print(os.listdir('data'))
```

## 3.6 Use `index_col` for Row Labels

By default, Pandas gives rows numeric labels: `0`, `1`, `2`, and so on. These are called **indexes**, and are unique for each row. However, numbers aren't very informative to describing what's in each row, so we should change the index. For this data, it is more useful to use the `country` column as the row index. Although you can do for any column, it's good practice to use indexes that are unique.

```python
data_oceania_country = pd.read_csv(
    'data/gapminder_gdp_oceania.csv',
    index_col='country'
)

print(data_oceania_country)
```

Now the country names are row labels instead of regular values in a column.

## 3.7 Inspect a DataFrame with `.info()`

Use `.info()` to summarize the structure of a DataFrame.

```python
data_oceania_country.info()
```

This tells you:

- the object type
- the number of rows
- the number of columns
- the column names
- how many non-null values each column contains
- the data type of each column
- memory usage

## 3.8 Inspect Column Names with `.columns`

The `.columns` attribute stores the column labels.

```python
print(data_oceania_country.columns)
```

Notice that `.columns` does **not** use parentheses. It is an attribute, not a function.

Compare:

```python
# Attribute: no parentheses
print(data_oceania_country.columns)

# Function: uses parentheses
print(data_oceania_country.describe())
```

## 3.9 Summary Statistics with `.describe()`

Use `.describe()` to calculate summary statistics for numerical columns. Notice that it handles which the different data types automatically. Neat!

```python
data_oceania_country.describe()
```

This reports values such as:

- count
- mean
- standard deviation
- minimum
- quartiles
- maximum

## 3.10 Preview Rows with `.head()` and `.tail()`

Read the Americas dataset:

```python
data_americas = pd.read_csv(
    'data/gapminder_gdp_americas.csv',
    index_col='country'
)
```

Show the first five rows:

```python
data_americas.head()
```

Show the first three rows:

```python
data_americas.head(n=3)
```

Show the last three rows:

```python
data_americas.tail(n=3)
```

## 3.11 Writing a DataFrame to a CSV File

Use `.to_csv()` to save a DataFrame.

```python
data_americas.to_csv('processed_americas.csv')
```

This writes the file to the directory where your notebook session is running.

## 3.12 Practice: Reading Data

### Exercise 3 — Read Europe Data

Read the Europe Gapminder GDP data and use `country` as the row index.

### Exercise 4 — Inspect the DataFrame

Use commands to answer:

1. How many rows are in the Europe dataset?
2. How many columns are in the Europe dataset?
3. What are the column names?
4. What data type is stored in the GDP columns?

---

# Part 4 — Working with Pandas DataFrames

## 4.1 Load the Europe Dataset

```python
import pandas as pd

data = pd.read_csv('data/gapminder_gdp_europe.csv', index_col='country')
```

Use `.head()` to confirm that the file loaded correctly:

```python
data.head()
```

## 4.2 Select By Position with `.iloc`

Use `.iloc` when you want to select by integer position.

```python
print(data.iloc[0, 0])
```

This means:

- row position `0`
- column position `0`

Because Python uses zero-based indexing, this selects the first row and first column.

## 4.3 Select by label with `.loc`

Use `.loc` when you want to select by row and column labels.

```python
print(data.loc['Albania', 'gdpPercap_1952'])
```

This selects the value for Albania in 1952.

## 4.4 Select an Entire Row

Use `:` to mean “everything” along an axis.

```python
print(data.loc['Albania', :])
```

This selects all columns for Albania.

The shorter version also works:

```python
print(data.loc['Albania'])
```

## 4.5 Select an Entire Column

```python
print(data.loc[:, 'gdpPercap_1952'])
```

This selects all rows for the column `gdpPercap_1952`.

A common shortcut for selecting a single column is:

```python
print(data['gdpPercap_1952'])
```

## 4.6 Select Ranges of Rows and Columns

Select rows from Italy through Poland and columns from 1962 through 1972:

```python
subset = data.loc['Italy':'Poland', 'gdpPercap_1962':'gdpPercap_1972']
print(subset)
```

**Warning:** There's an important distinction:

| Selection method | Slice behavior |
|---|---|
| `.iloc` | stop position is excluded |
| `.loc` | stop label is included |

For example:

```python
print(data.iloc[0:2, 0:2])
```

includes row positions `0` and `1`, and column positions `0` and `1`.

But:

```python
print(data.loc['Albania':'Belgium', 'gdpPercap_1952':'gdpPercap_1962'])
```

includes `Belgium` and `gdpPercap_1962` because `.loc` includes the ending labels.

## 4.7 Calculate Statistics on a Subset

Once you select a subset, you can analyze it.

```python
subset = data.loc['Italy':'Poland', 'gdpPercap_1962':'gdpPercap_1972']

print(subset.max())
print(subset.min())
print(subset.mean())
```

These calculations are applied column by column.

## 4.8 Use Comparisons to Create Boolean Masks

A comparison such as `subset > 10000` is applied to every value in the DataFrame.

```python
subset = data.loc['Italy':'Poland', 'gdpPercap_1962':'gdpPercap_1972']

print(subset > 10000)
```

This returns a DataFrame of `True` and `False` values.

## 4.9 Use a Boolean Mask to Filter Values

You can use the Boolean DataFrame as a mask.

```python
high_gdp = subset[subset > 10000]
print(high_gdp)
```

Values that meet the condition are kept. Values that do not meet the condition become `NaN`, which means “Not a Number.” Many summary operations ignore `NaN` values.

```python
high_gdp.describe()
```

## 4.10 Filter Rows Using a Column Value

Load the combined Gapminder dataset:

```python
all_data = pd.read_csv('data/gapminder_all.csv', index_col='country')
```

Select only countries in the Americas:

```python
americas = all_data[all_data['continent'] == 'Americas']
americas.head()
```

Break the filtering expression into pieces:

```python
is_americas = all_data['continent'] == 'Americas'
print(is_americas.head())

americas = all_data[is_americas]
americas.head()
```

This is often easier for learners to understand because the Boolean condition is stored in a named variable.

## 4.11 Drop Rows or Columns

Drop a row by label:

```python
americas_without_puerto_rico = americas.drop('Puerto Rico')
```

Drop a column by label:

```python
americas_gdp_only = americas_without_puerto_rico.drop('continent', axis=1)
```

Use `axis=1` when dropping a column. Rows are the default axis.

## 4.12 Save Results

Just like before, we'll save this dataframe as a CSV in our local directory. 

```python
americas_gdp_only.to_csv('americas_gdp_only.csv')
```

## 4.13 Practice: DataFrame Selection

### Exercise 5 — Individual Value

Find the GDP per capita of Serbia in 2007.

### Exercise 6 — Column Selection

Select GDP per capita for all European countries in 1982.

### Exercise 7 — Row Selection

Select GDP per capita for Denmark for all years.

### Exercise 8 — Range Selection

Select GDP per capita for all countries for years after 1985.

### Exercise 9 — Growth Ratio

Calculate GDP per capita in 2007 divided by GDP per capita in 1952 for each European country.

### Exercise 10 — Boolean Filtering

Create a subset of European countries where GDP per capita in 2007 is greater than 30,000.

---

# Part 5 — Resources

## Common Errors

| Error | Likely cause | Fix |
|---|---|---|
| `NameError` | Variable was not created or was misspelled | Re-run assignment cell; check spelling |
| `FileNotFoundError` | Wrong path or notebook started in wrong folder | Check `os.getcwd()` and `os.listdir()` |
| `KeyError` | Row or column label does not exist | Check `data.index` or `data.columns` |
| Confusing `.loc` and `.iloc` | Mixing labels with positions | Use `.loc` for names; `.iloc` for numbers |
| Unexpected old value | Notebook cells run out of order | Restart kernel and run all cells |

---

# Part 6 — Answer Key

## Exercise 1 Example

```python
first_name = 'Cassie'
favorite_organism = 'Ralstonia solanacearum'
sample_count = 12

print(first_name, 'is analyzing', sample_count, 'samples of', favorite_organism)
```

Expected output:

```text
Cassie is analyzing 12 samples of Ralstonia solanacearum
```

## Exercise 2 Answer

```python
countries = ["Canada", "Mexico", "United States", "Brazil"]

print(countries[0])
print(countries[2])
print(countries[-1])
print(countries[0:2])
print(countries[2:])
print(countries[:])
```

Expected output:

```python
Canada
United States
Brazil
['Canada', 'Mexico']
['United States', 'Brazil']
['Canada', 'Mexico', 'United States', 'Brazil']
```

## Exercise 3 Answer

```python
import pandas as pd

data_europe = pd.read_csv('data/gapminder_gdp_europe.csv', index_col='country')
data_europe.head()
```

## Exercise 4 Answer

```python
data_europe.info()
print(data_europe.columns)
print(data_europe.shape)
print(data_europe.dtypes)
```

## Exercise 5 Answer

```python
print(data_europe.loc['Serbia', 'gdpPercap_2007'])
```

## Exercise 6 Answer

```python
data_europe['gdpPercap_1982']
```

## Exercise 7 Answer

```python
data_europe.loc['Denmark', :]
```

## Exercise 8 Answer

```python
data_europe.loc[:, 'gdpPercap_1987':]
```

Note: the dataset uses 5-year intervals. Because there is no exact `gdpPercap_1985` column, `gdpPercap_1987` is the first available column after 1985.

## Exercise 9 Answer

```python
data_europe['gdpPercap_2007'] / data_europe['gdpPercap_1952']
```

## Exercise 10 Answer

```python
high_2007 = data_europe[data_europe['gdpPercap_2007'] > 30000]
high_2007
```

---

# Source and attribution

This notebook is adapted from the Software Carpentry lesson **Plotting and Programming in Python**, specifically the Gapminder instructor materials for:

- Summary and Schedule: <https://swcarpentry.github.io/python-novice-gapminder/instructor/index.html>
- Running and Quitting: <https://swcarpentry.github.io/python-novice-gapminder/instructor/01-run-quit.html>
- Variables and Assignment: <https://swcarpentry.github.io/python-novice-gapminder/instructor/02-variables.html>
- Reading Tabular Data into DataFrames: <https://swcarpentry.github.io/python-novice-gapminder/instructor/07-reading-tabular.html>
- Pandas DataFrames: <https://swcarpentry.github.io/python-novice-gapminder/instructor/08-data-frames.html>

Original Carpentries materials are licensed under **CC BY 4.0** by the authors. This adapted notebook should retain attribution when reused or modified.
