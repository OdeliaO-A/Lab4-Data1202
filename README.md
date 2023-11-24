# Data1202: Lab 4
In this Lab, you will practice using Pandas. By the end of this lab, you will be familiar with the many methods used for Creating columns (default and calculated), concatenating, Appending, Renaming and Reording in Python.

## Table of Contents

<div class="alert alert-block alert-info" style="margin-top: 20px">
In this Lab you will learn:
<ol>
    <li><a href="#p1">Create new columns</a></li>
    <li><a href="#p2">Concatenate dataframes and Append Data</a></li>
    <li><a href="#p3">Rename and Reorder of Columns</a></li>
    <li><a href="#p4">Groupby, Case WHEN and WHERE</a></li>
    <li><a href="#p5">Practice Questions</a></li>
</ol>

Estimated Time Needed: <strong>60 min</strong>
</div>

Import Python Libraries
import pandas as pd
#import numpy as np

<div class="alert alert-block alert-info" style="margin-top: 20px">
    <h1 align=center><a name=p1>Part 1 : Create new Columns (Default and Calculated) </a></h1>
</div>

## Running the tests

Expand the number of columns
pd.set_option('display.max_columns', 500)

# define variables for the csv files, this step is not mandatory 
#but it will help to understand the importing data step in Python

File_1 = "Salaries.csv"

# Read the csv file 
raw_df = pd.read_csv(File_1)

raw_df.head()

be sure that the file is imported

# SETTING A DEFAULT COLUMN VALUE

raw_df["Benchmarks"] = 70000

raw_df.head()

be sure that the column is added

raw_df['Service2'] = 50500

raw_df.head()

# CALCULATE A COLUMN
raw_df["Salary_score"] = round(raw_df["salary"] / raw_df["Benchmarks"],2)
raw_df.head()

raw_df.columns

# DROPPING a COLUMN
# Method 1: Subset the dataframe by including only spescific columns.
Subset_raw_df=raw_df[['rank','discipline','service']]
Subset_raw_df.head()

# Method 2: Use the drop method to drop the salary column.
Subset_raw_df=raw_df.drop(['sex','salary'], axis=1)
Subset_raw_df.head()
#Subset_raw_df
