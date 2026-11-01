# econ3916-lab11-sql

# SQL for Economists — Joins, Windows and the Cardinality Trap

## Objective

In this lab, I learned how to use SQL with DuckDB to analyze data and compare SQL operations with pandas.

## Methodology

- I translated pandas operations such as select, filter, sort, groupby, and merge into SQL.
- I used a LEFT JOIN to combine customer and order data and checked how the number of rows changed.
- I compared Welch t-test results before and after the join.
- I used window functions to calculate regional averages and customer rankings without removing individual rows.
- I tested how SQL and pandas handle missing values differently.
- I queried a public NYC taxi dataset using DuckDB without downloading the entire file.
- I used AI to translate three pandas operations into SQL, revised my prompt, and checked the results.

## Key Findings

- A LEFT JOIN increased the dataset from 600 customer rows to 3,612 rows because some customers had multiple orders.
- The Welch t-test results changed after the join because repeated rows affected the estimated difference and standard error. [Add t-statistics and p-values from the notebook.]
- Window functions calculated regional averages and rankings while keeping all 600 customer rows.
- SQL kept only 3 of 5 survey rows when filtering for income not equal to 50,000. It excluded the two missing incomes because comparisons with NULL return unknown. Pandas kept all 5 rows.
- DuckDB queried about 3 million NYC taxi trips over HTTP and returned six grouped rows without downloading the entire dataset.
- In my AI-assisted translation, Steps 3 and 4 matched the pandas row counts at first. Step 7 initially returned only 3 rows instead of 5. After I revised the prompt to include missing incomes, all three row counts matched.
