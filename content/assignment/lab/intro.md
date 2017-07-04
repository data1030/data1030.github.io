---
title: "Intro to Data Science"
date: 2017-09-08T03:17:08-07:00
draft: false
category: lab
---

Here's an intro assignment I've been working on using a dataset from kaggle.

# Lab: Intro to Pandas and the Data Science Process

Due: 6/15/2016

Prompt: TBD

## Part 0: Overview

In this assignment, you will learn how to use the Python Data Analysis Library (pandas) to transform, analyze, and visualize data. Begin below by importing the relevant modules. Be sure to delete or comment out the
```python
raise NotImplementedError()
```
statements.


```python
import pandas
```

## Part 1: Data Processing

### 1.1 Reading data
Data is often stored in comma-separated values (CSV) files like `API_ILO_country_YU.csv`.

<strong>_Task:_ Use the documentation for <a href="https://pandas.pydata.org/pandas-docs/stable/generated/pandas.read_csv.html"><code>pandas.read_csv()</code></a> to help you load your file to a variable called `dataframe`.

Hint: `pandas.read_csv` only has 1 required argument.</strong


```python
# YOUR CODE HERE
raise NotImplementedError()
# dataframe = ...
```


    -----------------------------------------------------------------

    NotImplementedError             Traceback (most recent call last)

    <ipython-input-2-906cfa5a80c4> in <module>()
          1 # YOUR CODE HERE
    ----> 2 raise NotImplementedError()
          3 # dataframe = ...


    NotImplementedError: 



```python
### TEST CASES: RUN TO CHECK

import numpy as np
assert type(dataframe) is pandas.core.frame.DataFrame
assert dataframe.ndim is 2
assert dataframe.shape[0] is 219
assert dataframe.shape[1] is 7

test_top = np.array([['Afghanistan', 'AFG', 20.6000003815, 20.8999996185, 19.7000007629,
        21.1000003815, 20.7999992371],
       ['Angola', 'AGO', 10.800000190699999, 10.6999998093, 10.6999998093,
        10.6000003815, 10.5],
       ['Albania', 'ALB', 25.7999992371, 27.0, 28.2999992371,
        28.7000007629, 29.2000007629],
       ['Arab World', 'ARB', 25.0222141591, 28.1175156719, 29.1132120157,
        29.335306043600003, 29.7045691168],
       ['United Arab Emirates', 'ARE', 9.8000001907, 9.8000001907,
        9.8000001907, 9.8999996185, 10.0],
       ['Argentina', 'ARG', 19.5, 18.7999992371, 18.3999996185,
        19.7000007629, 21.2999992371],
       ['Armenia', 'ARM', 38.2999992371, 38.7000007629, 35.0, 32.5,
        35.0999984741],
       ['Australia', 'AUS', 11.399999618499999, 11.399999618499999,
        11.699999809300001, 12.199999809300001, 13.100000381500001],
       ['Austria', 'AUT', 8.8000001907, 8.1999998093, 8.6999998093,
        9.1000003815, 9.1999998093],
       ['Azerbaijan', 'AZE', 14.600000381500001, 14.5, 14.300000190699999,
        13.399999618499999, 13.600000381500001]], dtype='object')

assert np.array_equal(dataframe.values[0:10], test_top)

# Prints the data
dataframe
```


    -----------------------------------------------------------------

    NameError                       Traceback (most recent call last)

    <ipython-input-3-9cc3f3d72abf> in <module>()
          2 
          3 import numpy as np
    ----> 4 assert type(dataframe) is pandas.core.frame.DataFrame
          5 assert dataframe.ndim is 2
          6 assert dataframe.shape[0] is 219


    NameError: name 'dataframe' is not defined


### 1.2 Viewing data

Congrats. You've successfully loaded the data into an object called a `Dataframe`. For now, think of it as a two dimensional table. Lets see what some `Dataframe` methods print:

    dataframe
    dataframe.columns
    dataframe.head()
    dataframe.head(10)
    dataframe.tail(4)
    dataframe.nlargest(5, '2014')
    dataframe.nsmallest(8, '2011')
    
<strong>_Task:_ Comment below why `dataframe.nlargest(5, 2014)` results in `KeyError: 2014` while `dataframe.nlargest(5, '2014')` does.

Hint: look at the data types of the columns. </strong>


```python
# YOUR CODE HERE
raise NotImplementedError()
```

### 1.3 Data Transformation

Even with only 219 rows, this table is a bit hard to read. Let's use `Dataframe` methods to find subsets of the data what we want. Try out the following methods:

#### Column selection:
    
    dataframe['2010'] - Single column selection
    dataframe[['Country Name', '2011', '2012']] - Multiple column selection
    dataframe.iloc[:, 3] - 4rd column
    dataframe.iloc[:, 2:5] - columns 3 to 5
    
#### Row selection:
    
    dataframe.iloc[191] - 192th row
    dataframe.iloc[0:10] - First 10 rows
    dataframe[dataframe['2010'] > 40] - Boolean conditions, rows where 2010 column value is greater than 40
    
#### Combinations:

    dataframe.iloc[12:14, 0:4]
    dataframe[['Country Name', '2011', '2012']][dataframe['2012'] < 10]
    dataframe[dataframe['2012'] < 10].iloc[1:3, 2:5]

<strong>_Task_: Find the _country name_ and _country code_ of all rows where:

* the 2010 unemployment rate is higher than 2014 unemployment rate, and
* the 2014 unemployment rate is above 20%</strong>


```python
# YOUR CODE HERE
raise NotImplementedError()
```

## Part 2: Data Analysis

You've ingested the data. Now it's time to make discoveries.


### 2.1 Initial Exploration

All of these numbers, where to start. How can we quickly find interesting trends? Maybe graphs can help.

<strong>_Task:_ Plot the graph with [`pandas.DataFrame.plot`](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.plot.html)
</strong>


```python
%matplotlib inline

# Run code to plot
dataframe.plot(kind='bar')
```

<strong>Task: There's clearly too many rows being graphed. Show a more manageble number of countries (say the first 10). Then, label the x axis.</strong>




```python
%matplotlib inline
# YOUR CODE HERE
raise NotImplementedError()
```

Now that we have a readable chart, we can start looking for interesting observations.

One of the labels `'Arab World'`. While clearly this is not a country name, there is definitely a noticeable trend going on. Our end goal is to communicate how events in the Arab World have effected unemployment.

### 2.2 Research and Domain Knowledge

Before we can do analysis we should make sure this trend is meaningful. Use Google, Wikipedia, etc. to help you figure out.

Here are some questions to get you started:

* Is the youth unemployment rate high? Maybe `dataframe.describe()` can tell us something.

* By how much does unemployment increase during these 5 years, approximately? Is this difference big enough for us to look into

* What is the Arab World? What countries are in this block?

* What major events occurred around 2010-2014?

This section is ungraded.

SPACE TO WRITE NOTES


```python
# SPACE TO TRY OUT CODE
# EX: dataframe.describe()
# EX: dataframe[dataframe['Country Name'] == 'Arab World']
```

## Part 3: Data Communication

How is unemployment related to the Arab Spring? What caused the spike?

_Task_: Write a short report (~2 paragraphs) about the data and what it tells us.

YOUR ANSWER HERE

## Summary

### Pandas

#### Modules

    import pandas as pd

#### I/O

    pd.read_csv()
    df.to_csv()

#### Indexing

    df[column_name]
    df[[column1, column2, ...]]
    df.iloc[a:b,c:d]
    df[boolean condition]

#### Exploration

    df.describe()
    df.plot()
