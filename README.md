# Analyzing Startup Fundraising Deals from Crunchbase

In this guided project by Dataquest (DQ), I analyzed startup investments from [Crunchbase](https://www.crunchbase.com/). My goal in this project is to provide answers to the following questions:
* What proportion of the total amount of funds did the top 10% raise? What about the top 1%? How do these values compare with the proportions of the bottom 10% and bottom 1% raised?
* Which category of startup companies attracted the most investments?
* Which investor contributed the most money across all startups?
* Which investors contributed the most money per startup?
* Which funding round was the most popular? Which was the least popular?

As for practice in handling large data sets in Python, I worked under the following conditions/constraints:
* available memory is limited to 10 MB 
* use a database such as SQLite to represent the data set on disk, then employ pandas to store and work with a subset of the data set in memory (SQL/pandas workflow) 

I performed the following methods in this project:
* Explored the first 5 rows of the dataset and determined the number and pre-assigned data types of the columns
* Determined the number of missing values and the memory footprint of each data column and whole the data set
* Reduced the memory footprint of the data set by:
  - removal of data columns not useful for analysis and with missing values greater than 90%
  - casting of data columns of low cardinality into the categorical type
  - parsing of appropriate data columns into datetime type
  - cleaning and casting of string columns into the categorical type
  - casting of float columns to the integer type
* Loaded the modified data set by chunks into an SQLite database table
* Queried the SQLite database table to return subsets of the data set and used pandas for data analysis

The optimization procedure decreased the overall memory of the data set by 82.6% (from 57 to 9.9 MB) before its migration to SQLite. Using the SQL/pandas workflow, I concluded the following:
* The top 10% of startup companies raised 63% of the total amount of funds; the top 1% raised 22% of the total funds. The contributions of the bottom 10% and 1% of the startup companies are negligible (less than 1% of the total amount of funds).
* `Biotech` companies attracted the most investments, followed by `software` and `cleantech`.
* `Kleiner Perkins Caufield & Byers` contributed the most money across all startups.
* `Sprint Nextel`, `GI Partners`, and `Eagle River Holdings` have contributed the most money per startup.
* `Series A` is the most popular funding round while `crowdfunding` is the least.

For more details, please see the Project7.ipynb notebook and the supporting files (`crunchbase-investments.csv` and `crunchbase.db`). 
