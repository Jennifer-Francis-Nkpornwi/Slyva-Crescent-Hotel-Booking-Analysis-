# Data Cleaning Summary

## Project
**Hotel Booking & Commercial Impact Analysis**

## Tool Used
**Microsoft Power BI – Power Query**

---

# Objective

The objective of the data cleaning process was to prepare the raw hotel booking dataset for accurate analysis, data modeling, and dashboard development. The dataset was reviewed for data quality issues, validated, and transformed to ensure reliable business insights.

The dataset contained **119,390 booking records** from both a **City Hotel** and a **Resort Hotel**, covering bookings made between **1 July 2015** and **31 August 2017**.

---

# Data Cleaning Approach

A systematic data quality assessment was carried out before analysis. The process focused on validating data integrity, correcting inconsistencies, and creating additional fields required for reporting.

---

# Data Cleaning Activities

## 1. Data Inspection

The dataset was reviewed to understand its structure before transformation.

The following checks were performed:

- Confirmed the total number of records.
- Reviewed all available columns.
- Assessed whether each field was relevant to the analysis.
- Identified missing values.
- Verified that data types matched their intended use.

**Outcome**

The dataset was suitable for analysis after minor cleaning and transformation.

---

## 2. Data Type Validation

All columns were reviewed to ensure appropriate data types had been assigned.

| Column | Data Type |
|---------|-----------|
| hotel | Text |
| is_canceled | Whole Number |
| lead_time | Whole Number |
| arrival_date_year | Whole Number |
| arrival_date_month | Text |
| arrival_date_day_of_month | Whole Number |
| adults | Whole Number |
| children | Whole Number |
| babies | Whole Number |
| adr | Decimal Number |
| country | Text |

**Outcome**

Correct data types ensured accurate calculations, aggregations, and visualizations throughout the analysis.

---

## 3. Missing Value Treatment

Column Quality was enabled to identify missing (null) values across the dataset.

The following actions were taken:

| Column | Issue Identified | Action Taken | Business Justification |
|---------|------------------|--------------|------------------------|
| children | Null values | Replaced with **0** | Missing values indicated that no children accompanied the booking. |
| country | Null values | Replaced with **"Unknown"** | The actual country could not be determined without introducing assumptions. |
| agent | Large number of null values | Replaced with **0** | Many bookings were made directly without travel agents. |
| company | Large number of null values | Replaced with **0** | Many guests booked independently rather than through corporate accounts. |

**Outcome**

Missing values were handled while preserving the integrity and completeness of the dataset.

---

## 4. Duplicate Validation

Duplicate records were assessed across the dataset.

### Actions Performed

- Selected all columns.
- Checked for duplicate booking records.
- Compared row counts before and after duplicate validation.

**Outcome**

No meaningful duplicate records requiring removal were identified. The total record count remained unchanged.

---

## 5. Feature Engineering

To support analysis and KPI development, additional calculated columns were created.

### Total Guests

**Formula**

```text
[adults] + [children] + [babies]
```

**Purpose**

Calculate the total number of guests included in each booking.

---

### Total Nights

**Formula**

```text
[stays_in_weekend_nights] + [stays_in_week_nights]
```

**Purpose**

Calculate the total duration of each stay for reporting and revenue estimation.

---

### Arrival Date

The separate **Year**, **Month**, and **Day** columns were combined into a single **Arrival Date** field.

**Purpose**

Create a proper date field to support calendar modeling, time intelligence, and trend analysis.

---

## 6. Outlier Assessment

The **Average Daily Rate (ADR)** column was sorted in descending order to identify unusually high values.

A significantly higher ADR value was observed compared to the rest of the dataset.

### Action Taken

The record was **retained** because:

- There was no evidence indicating the value was erroneous.
- The project required identifying the highest ADR.
- Removing the value could distort genuine business findings.

---

## 7. Final Validation

Before loading the data into the Power BI model, the dataset was validated to confirm it was ready for analysis.

The following checks were completed:

- ✓ Data types verified
- ✓ Missing values addressed
- ✓ Duplicate validation completed
- ✓ New analytical columns created
- ✓ Arrival Date field generated
- ✓ Dataset prepared for data modeling
- ✓ Dataset prepared for DAX calculations
- ✓ Dataset prepared for dashboard development

---

# Summary of Transformations

| Transformation | Action Performed | Business Value |
|----------------|------------------|----------------|
| Data Inspection | Reviewed dataset structure and quality | Improved understanding of the data before analysis |
| Data Type Validation | Verified and corrected column data types | Ensured accurate calculations and reporting |
| Missing Value Treatment | Replaced null values in selected fields | Improved data completeness while preserving valid records |
| Duplicate Validation | Checked for duplicate records | Confirmed data integrity |
| Total Guests | Created calculated column | Enabled guest composition analysis |
| Total Nights | Created calculated column | Supported stay duration and revenue calculations |
| Arrival Date | Combined Year, Month, and Day into a single date field | Enabled time-based reporting and calendar modeling |
| Outlier Assessment | Reviewed unusually high ADR values and retained valid records | Preserved genuine booking information for business analysis |

---

# Outcome

The cleaned dataset became the single source of truth for the project and was used to develop:

- Operational Dashboard
- Commercial Impact Dashboard
- Executive Summary
- Business Questions & Insights
- Stakeholder Recommendations

The data preparation process ensured that all subsequent analysis was based on a consistent, validated, and reliable dataset, enabling stakeholders to make informed operational and commercial decisions.
