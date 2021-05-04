# Analysis of Supermarket Sales Data

Company XYZ has 3 major branches across 3 cities. This project is focused on analyzing the sales data of all branches over the course of 3 months in order to understand trends, such as, the category of product that makes more sales. 
It involved: 
    * joining the datasets from all branches, 
    * editing some variables into suitable formats, and 
    * running some tests to make inferences.

# Project Steps

There are 6 major steps involves in this project:

## Loading datasets
All potential libraries for the data analysis were imported at first.

This involved accessing the sales data of all 3 branches of the supermarket and combining them using the [concat] method, to obtain a wholesome dataset. The combined dataset was exported into a new file which was used for the rest of the process.

## Data exploration
Here, dataset was called and read using the [pd.read_csv] command. 
    The first few rows were observed using the [head] method.
    The shape (number of rows and columns) of the dataset was obtained using [df.shape].
    Other information like the column titles, data description, presence of missing values, and overall info were explored using the [df.column, df.describe, df.isnull and df.info] commands, respectively.

## Dealing with datetime features
The info command in the previous step revealed that certain columns (date and time) were not in the right format for analysis. This section was dedicated to correcting the datatype (changing to a datetime format) using the df.to_datetime command.
This was done for both concerned columns. And from the corrected dataset, new columns were created for year, month, day, and hour, by assigning the column name to a specific value. E.g df['Year']=df['Date'].dt.year.

## Generating unique values
In this section, categorical columns (non-numerical and non-datetime) were screened out by selecting only those with 'object' type.
syntax used: categorical_columns = [col for col in DF.columns if DF[col].dtype == 'object']

This command created a new object, categorical_columns, which when called gave a list of all 7 categorical columns in the entire dataset.

From this object, it was easy to identify unique values in each column. [isunique()] method was used for this.
value_counts() method was also used to count the number of data entry that correspond to each unique value in each column.

## Aggregation by groupby
Here, the dataset was grouped by the city and used to get insights on the gross income for each branch/city.
[df.groupby('column_name)] was used.

## Data visualization
This section focused on plotting different kinds of charts to establish the relationship between data values based on different factors.
Charts used in this section includes:
    countplot
    boxplot
    barplot
    stripplot
    pointplot

# Insights

To-Do - Explain the insights you were able to uncover from the analysing the datasets.

# Future Work

I'm not exactly sure right now.

# Standout Section

The instructions in the notebook were helpful and straightforward. In addition to those insructions, I took it a step further by making use of different paarmeters in each method applied, in order to select the best representation for data set.

For instance, the default describe method under the data exploration step focused only on numerical values in the dataset, which means other aspects were not represented. So, I used the include='all' parameter which enabled the display of the statistical summary for all columns in the dataset.

Also, instead of checking for missing values using only df.isnull(), i added .sum() so as to get a summary as opposed to print the huge dataset which displays boolean values for each row.

For the data visualization , I did more than the instruction notebook specified. Since the aim of the analysis was to understand sales trends and determine company growth, I decided to analyse some unlisted relationships to determine if there'll be any useful result to draw conclusions from. All plots in the project are supported with written context to explain the thought process.

# Executive Summary.

The Executive Summary document has been created and added to the rest of the files. It explains the problem statement, the methods of analysis used, the insights obtained, and suggestions for future activities in the company.
