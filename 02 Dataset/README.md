# Dataset

This folder contains the datasets used throughout the project.

| Dataset | Records | Description |
|----------|--------:|-------------|
| **Hotel_Booking_Raw_Data.csv** | 119,390 | Original hotel booking dataset before any cleaning or transformation. |
| **Hotel_Booking_Cleaned_Data.csv** | 119,390 | Dataset prepared for analysis after data validation, data type corrections, duplicate checks, null value handling, date preparation, and standardization in Power Query. |

## Data Cleaning Summary

The cleaned dataset was prepared using **Power Query** in Power BI. The following transformations were performed:

- Validated and corrected data types.
- Checked for duplicate records.
- Handled missing (null) values where applicable.
- Merged date components to create a proper date field.
- Standardized categorical values for consistency.
- Removed unnecessary fields used only for data preparation.
- Prepared the dataset for data modeling, DAX calculations, and dashboard development.

> **Note:** The cleaned dataset serves as the source for both the **Operational Dashboard** and the **Commercial Impact Dashboard** included in this project.
```
