# E-commerce Data Cleaning and Preprocessing using Python

## Project Overview

This project focuses on cleaning and preprocessing a messy e-commerce orders dataset using Python and Pandas. The objective is to improve data quality by identifying and handling missing values, duplicate records, inconsistent text entries, invalid numerical values, incorrect dates, and inaccurate customer contact information.

The notebook follows a data-cleaning workflow that transforms raw order data into a more consistent dataset suitable for further analysis.

## Technologies Used

Python was used as the programming language, with Pandas for data manipulation, inspection, cleaning, and transformation. Jupyter Notebook was used to execute the workflow step by step.

## Project Workflow

### 1. Data Loading and Inspection

The project begins by loading the `ecommerce_orders_messy.csv` dataset into a Pandas DataFrame. The dataset is inspected to understand its dimensions, column data types, missing values, duplicate records, and unique values in categorical columns.

### 2. Text Standardization

Inconsistent text values are standardized to improve consistency across the dataset. This includes formatting customer names and product names, correcting product category labels, standardizing order statuses and payment methods, and normalizing city and state names.

### 3. Data Type Conversion

Numerical columns, including quantity, unit price, discount percentage, total amount, and rating, are converted to appropriate numeric types. Date values are parsed using multiple date formats, with invalid dates handled as missing values.

### 4. Data Validation

The notebook checks for invalid quantities, unit prices, discount percentages, customer ratings, future order dates, and delivery dates that occur before order dates. Invalid values are marked as missing for subsequent handling.

Ratings are also removed from records whose order status is not `Delivered`, following the rule implemented in the notebook.

### 5. Email and Phone Number Cleaning

Email addresses are validated using a regular expression, and invalid entries are marked as missing. Phone numbers are cleaned by removing non-digit characters and retaining the last ten digits when at least ten digits are available.

### 6. Duplicate Removal

Exact duplicate records are removed first. The dataset is then deduplicated using `order_id`, keeping the first record for each order ID.

### 7. Missing Value Handling

Missing product categories and unit prices are filled using the most frequently occurring values associated with each product name. Missing quantities are filled using the median, while missing discounts are set to zero.

Missing payment methods are labeled `Unknown`, and missing city and state values are also assigned `Unknown`. Missing customer names and email addresses are filled using the most frequent available values associated with each customer ID.

### 8. Total Amount Recalculation

The total amount is recalculated using quantity, unit price, and discount percentage:

`total_amount = quantity × unit_price × (1 − discount_pct / 100)`

The calculated amount is rounded to two decimal places.

### 9. Final Validation and Export

After the cleaning operations, the notebook checks missing values and duplicate order IDs again. The resulting DataFrame is exported to `ecommerce_orders_cleaned.csv` without including the DataFrame index.

## Input and Output Files

The input file is `ecommerce_orders_messy.csv`, which must be available in the notebook's working directory.

The output file is `ecommerce_orders_cleaned.csv`, containing the cleaned and preprocessed dataset.

## How to Run the Project

1. Install Python and Jupyter Notebook, or use Google Colab.
2. Install Pandas if it is not already available.
3. Upload `swynex.ipynb` and the input CSV file to the same working directory.
4. Execute the notebook cells in order.
5. After successful execution, locate `ecommerce_orders_cleaned.csv` in the working directory.

Install Pandas using:

`pip install pandas`

## Key Learnings

Through this project, I practised inspecting datasets, identifying data quality issues, standardizing categorical values, converting data types, validating numerical and date fields, handling missing values, removing duplicates, cleaning customer contact information, and exporting processed data.

## Conclusion

This project demonstrates a practical application of Python and Pandas for e-commerce data cleaning and preprocessing. It strengthened my understanding of preparing raw datasets for reliable downstream data analysis.

**Skills demonstrated:** Python, Pandas, Data Cleaning, Data Validation, Data Preprocessing, Missing Value Handling, and Data Quality Checks.
