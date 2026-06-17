## Business Rules Applied

### Missing Region

* Identified 25 records with missing region values.
* Replaced missing values with "Unknown".
* Flagged affected records in the quality report.

### Missing Ship Mode

* Identified 21 records with missing ship mode values.
* Replaced missing values with "Unknown".
* Flagged affected records in the quality report.

### Missing Discount

* Identified 18 records with missing discount values.
* Replaced missing discounts with 0 where quantity and unit price were available.

### Invalid Discounts

* Negative discount values were flagged as invalid.
* No discounts exceeded the maximum allowed range.

### Shipping Validation

* Identified 21 records where ship date occurred before order date.
* Flagged these records as invalid shipping records.

### Cancelled Orders

* 145 cancelled orders were retained in the dataset.
* Excluded from completed sales reporting.

### Failed Payments

* 69 failed-payment records were retained.
* Excluded from completed sales reporting.

### Refunded Transactions

* 71 refunded transactions were retained.
* Included in a separate refund summary for reporting.

### Duplicate Records

* Exact duplicate records were removed during the duplicate handling stage.
* Conflicting duplicate records were retained and flagged for review.

### Shipping Validation:
- Calculated shipping_delay_days as ship_date_clean minus order_date_clean.
- Records with negative shipping delay were flagged as "Invalid Shipping Record".
- These records were retained in the dataset for auditability but excluded from clean-record analysis.
