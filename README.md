# Mall Customer Segmentation Data Analysis

This notebook performs an initial exploratory data analysis and basic data preparation on the 'Mall_Customers' dataset. The goal is to understand customer behavior and prepare the data for further segmentation or machine learning tasks.

## Table of Contents

1.  [Data Loading and Initial Exploration](#data-loading-and-initial-exploration)
2.  [Data Cleaning and Preparation](#data-cleaning-and-preparation)
3.  [Feature Engineering](#feature-engineering)
4.  [Data Filtering](#data-filtering)
5.  [Data Export](#data-export)

---

## 1. Data Loading and Initial Exploration

- The 'Mall_Customers (1).csv' dataset is loaded into a pandas DataFrame.
- Initial data inspection using `head()`, `tail()`, `info()`, `describe()` provides an overview of the data's structure, column types, and basic statistics.
- Missing values are identified using `isnull().sum()` and `isna().sum()/len(data_frame)*100`.

## 2. Data Cleaning and Preparation

- Columns were renamed for clarity: 'CustomerID' to 'ID', 'Gender' to 'Sex', and 'Annual Income (k$)' to 'Salary'.
- The 'Sex' column, originally categorical ('Male', 'Female'), was converted to numerical representation (0 and 1) using `LabelEncoder`.
- The 'Spending Score (1-100)' column was renamed to 'Spending_Score' for easier access.

## 3. Feature Engineering

- A new column, 'Customer_Satisfaction', was created based on the 'Spending_Score'. Customers with a 'Spending_Score' greater than 70 are labeled as 'Satisfied', and others as 'Unsatisfied'.

## 4. Data Filtering

- Subsets of the data were created based on specific criteria:
    - `low_spenders_data`: Customers with a 'Spending_Score' less than 70.
    - `high_earners_low_spenders_data`: Customers with 'Salary' greater than the mean salary and 'Spending_Score' less than 70.

## 5. Data Export

- The prepared `data_frame`, including the new 'Customer_Satisfaction' column, was saved to a new CSV file named 'Prepared_Mall_Customers.csv' in the '/content/' directory, without including the DataFrame index.
