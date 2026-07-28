# Data Cleaning

## Overview

Before analysis, the raw hotel booking dataset was cleaned and transformed using **Power Query in Power BI** to improve data quality, ensure consistency, and prepare the dataset for modeling and visualization.

The objective was to produce a reliable dataset suitable for business analysis and dashboard development.

---

## Data Quality Checks

The following checks were performed before analysis:

- Reviewed data types for all columns.
- Checked for duplicate records.
- Identified missing (null) values.
- Reviewed categorical fields for inconsistencies.
- Validated numerical fields used in KPI calculations.
- Prepared date fields for time-based analysis.

---

## Power Query Transformations

The following transformations were applied:

### 1. Data Type Validation

Assigned appropriate data types to all fields including dates, whole numbers, decimal numbers, and text.

---

### 2. Duplicate Validation

Reviewed the dataset for duplicate booking records.

No duplicate records requiring removal were identified.

---

### 3. Missing Value Review

Checked columns for null values and confirmed that fields required for analysis were suitable for reporting.

---

### 4. Date Preparation

Merged the separate **Year**, **Month**, and **Day** columns into a single Date field 

---

### 5. Data Standardization

Reviewed categorical values for consistency to ensure accurate grouping and reporting across visuals.

---

### 6. Final Validation

Verified that the cleaned dataset was ready for:

- Data Modeling
- DAX Calculations
- Dashboard Development

---

## Data Model

The analysis was built using a **single-table data model** based on the cleaned Hotel Bookings dataset.

As all attributes required for analysis were contained within the source dataset, no additional dimension tables or table relationships were required. This simplified model supported all DAX calculations, KPIs, and dashboard visualizations developed for the project.

---

## Output

The cleaned dataset served as the single source for:

- Operational Dashboard
- Commercial Impact Dashboard
