# AIM: DATA WRANGLING AND PREPROCESSING IN PYTHON


# THEORY:
Data wrangling (or data preprocessing) is the process of cleaning, transforming, and organizing raw data into a structured format suitable for analysis.
In real-world datasets, data is often incomplete, inconsistent, or improperly formatted, so preprocessing becomes a crucial step before applying any analysis or machine learning techniques.

# Handling Missing Values:
Missing data is commonly represented as NaN (Not a Number) in Python libraries like Pandas.

Detecting Missing Values -
isna() → Returns True for missing values
notna() → Returns True for non-missing values
These functions help identify where data is missing.

Counting Missing Values -
df.isna().sum(axis=0) → Counts missing values column-wise
df.isna().sum(axis=1) → Counts missing values row-wise
This helps understand the extent of missing data.

Removing Missing Values -
dropna() → Removes rows containing missing values
dropna(axis=1) → Removes columns containing missing values
This is useful when missing data is minimal and can be safely discarded.

Replacing Missing Values -
fillna(0) → Replaces missing values with a constant
fillna(mean) → Replaces missing values with the column mean
Replacing values is preferred when data loss is not acceptable.

# Data Cleaning:
Raw data may contain incorrect or inconsistent entries such as symbols ("-") or mixed formats.
Replacing Invalid Values
replace("-", np.nan) converts placeholder values into proper missing values (NaN), making them easier to handle.

# Data Type Conversion:
Sometimes numerical data is stored as text (strings), which prevents proper analysis.

pd.to_numeric(column, errors="coerce")

Converts data into numeric format.
Invalid values are converted into NaN.
This ensures that mathematical operations can be performed correctly.

# Handling Missing Values Using Statistical Methods:
Instead of removing missing values, they can be filled using statistical measures:

Mean (Average) → Used for continuous data like Age
Median → Used when data may contain outliers (e.g., Marks)

Example:
fillna(mean) → Smooths data using average
fillna(median) → More robust against extreme values

# Data Standardization:
Categorical data may have inconsistencies such as:
"CSE", "cse", "Cse"

To fix this:

str.upper() converts all text to uppercase
This ensures uniformity and avoids duplication during analysis.

# Date and Time Conversion:
Dates may appear in different formats (e.g., "01-06-2023" vs "10/06/23").

pd.to_datetime() converts values into standard datetime format

errors="coerce" replaces invalid dates with NaT (Not a Time)

Using:
format="mixed" allows multiple date formats
dayfirst=True ensures correct interpretation (DD-MM-YYYY)
This step is important for time-based analysis.


# CONCLUSION:
Data wrangling involves handling missing values, correcting inconsistencies, converting data types, and formatting data properly.
Using tools like Pandas and NumPy, these tasks can be efficiently performed, making the dataset clean and ready for further analysis.



