# ananyadas_bitsom_ba_2511216_part1_data_cleaning

# Part 1: Data Cleaning and Validation using Excel

## Business Problem Summary

A retail company exported order-level sales data from multiple internal systems. The raw dataset contained several data quality issues including inconsistent text formatting, multiple date formats, duplicate records, missing values, invalid discounts, calculation inconsistencies, and order status exceptions.

The objective of this assignment was to transform the raw dataset into a clean, validated, and analysis-ready dataset that can be reliably used for business reporting and decision-making.

---

## Dataset Used

**Source File:** `data/raw_orders.xlsx`

The dataset contains retail order information including:

* Order ID
* Customer Name
* Customer Segment
* Region
* State
* City
* Category
* Sub Category
* Order Date
* Ship Date
* Ship Mode
* Quantity
* Unit Price
* Discount
* Cost
* Sales
* Profit
* Payment Status
* Order Status

A cleaned version of the dataset was created as:

`data/cleaned_orders.xlsx`

---

## Tools Used

* Microsoft Excel
* Excel Formulas
* Pivot Tables
* Conditional Formatting
* Data Validation
* Sorting and Filtering

Key Excel functions used:

* TRIM
* UPPER / PROPER
* SUBSTITUTE
* IF
* IFERROR
* COUNTIF
* COUNTIFS
* TEXT
* YEAR
* DATE
* TEXTJOIN
* ABS

---

## Steps Performed

### 1. Raw Data Preservation

* Preserved the original dataset in `raw_orders.xlsx`
* Created a separate working file `cleaned_orders.xlsx`

### 2. Text Standardization

Cleaned and standardized:

* customer_name
* segment
* region
* state
* city
* category
* sub_category
* ship_mode
* payment_status
* order_status

Actions performed:

* Removed leading/trailing spaces
* Removed extra spaces
* Standardized text casing
* Corrected inconsistent category values
* Replaced missing region and ship mode values with "Unknown"

### 3. Date Standardization

Standardized:

* order_date
* ship_date

Converted multiple date formats into a consistent YYYY-MM-DD format.

Created:

* shipping_delay_days

Validated:

* Missing dates
* Ship dates before order dates
* Invalid shipping records

### 4. Duplicate Handling

Performed duplicate analysis using row-level signatures and Order ID validation.

Results:

* Exact duplicate rows identified and removed
* Duplicate Order IDs analyzed
* Conflicting duplicate records retained and flagged for review

### 5. Business Rule Validation

Applied the following business rules:

* Missing region → filled with "Unknown"
* Missing ship mode → filled with "Unknown"
* Missing discount → standardized to 0 where applicable
* Negative discounts → flagged as invalid
* Discount values standardized
* Ship date before order date → flagged
* Cancelled orders excluded from completed sales reporting
* Failed payment orders excluded from completed sales reporting
* Refunded orders separately summarized

### 6. Calculated Columns Created

Created:

* cleaned_discount
* calculated_sales
* calculated_profit
* profit_margin
* shipping_delay_days
* order_month
* order_year
* data_quality_flag

### 7. Data Quality Reporting

Created:

`outputs/data_quality_report.xlsx`

Report includes:

* Missing value summary
* Duplicate summary
* Invalid discount summary
* Date issue summary
* Order status issue summary
* Sales/profit mismatch summary
* Final clean vs flagged record count

### 8. Pivot Analysis

Created:

`outputs/pivot_summary.xlsx`

Pivot reports include:

* Sales and Profit by Region
* Sales and Profit by Category and Sub-Category
* Order Count by Ship Mode
* Profit Margin by Customer Segment
* Refunded / Cancelled / Failed Orders by Region
* Monthly Sales Trend

Sorting and filtering were applied to selected pivot reports for improved analysis.

---

## Key Outputs

### Clean Dataset

`data/cleaned_orders.xlsx`

### Data Quality Report

`outputs/data_quality_report.xlsx`

### Pivot Summary Report

`outputs/pivot_summary.xlsx`

### Cleaning Log

`outputs/cleaning_log.md`

---

## Business Insights

### Regional Performance

Sales and profit distribution vary significantly by region, indicating opportunities for targeted regional strategies.

### Product Performance

Certain categories and sub-categories contribute disproportionately to total revenue and profit.

### Shipping Operations

Multiple records were identified where ship dates occurred before order dates, highlighting operational or data-entry issues.

### Order Exceptions

Cancelled, refunded, and failed-payment orders represent a meaningful portion of transactions and should be monitored separately from completed sales.

### Data Quality

The dataset contained duplicate records, missing values, inconsistent formats, and invalid discounts that required remediation before analysis.

---

## Assumptions Made

* Missing region values were replaced with "Unknown".
* Missing ship mode values were replaced with "Unknown".
* Missing discount values were treated as 0 when related sales fields were valid.
* Discounts were standardized into a consistent format.
* Negative discounts were treated as invalid records.
* Records with ship dates earlier than order dates were retained but flagged.
* Conflicting duplicate Order IDs were retained and flagged for manual review.
* Cancelled and failed-payment orders were excluded from completed sales summaries but retained in the dataset.

---

## Known Limitations

* Some business rules required assumptions due to lack of source system documentation.
* Conflicting duplicate Order IDs require manual business review.
* Historical source-system validation was outside the scope of this assignment.
* Calculated metrics depend on the accuracy of source quantity, cost, and pricing fields.
* Flagged records were retained for auditability and not automatically corrected.

---

## Screenshots

### Raw Dataset Preview

`screenshots/raw_data_preview.png`

### Cleaned Dataset Preview

`screenshots/cleaned_data_preview.png`

### Pivot Summary 1

`screenshots/pivot_summary_1.png`

### Pivot Summary 2

`screenshots/pivot_summary_2.png`

All screenshots are included in the repository and demonstrate the data cleaning process and final reporting outputs.
