## Project Overview

This project is a complete **E-Commerce Order Analytics System** built as part of Week 8 of the Data Engineering internship.

The project starts with raw e-commerce data, cleans and validates it, stores the cleaned data in SQLite, and then uses SQL and Python to generate useful business insights.

The complete work is implemented mainly in the **Jupyter Notebook**, with data generation handled separately through `data_generation.py`.

## What This Project Covers

- Synthetic e-commerce data generation
- Data cleaning and validation using Pandas
- Handling missing and incorrect data
- Email validation
- Referential integrity checks
- SQLite database creation
- Basic and advanced SQL queries
- SQL window functions
- CTEs
- Customer segmentation using `NTILE`
- Year-over-year revenue comparison
- Customer cohort analysis
- Running revenue totals
- Product ranking using `DENSE_RANK`
- Customer order gap analysis using `LAG`
- Frequently bought together products
- Daily, weekly, and monthly sales reports
- Dynamic edge-case checking
- Issue and validation reports

---

## Project Structure

```text
WEEK-8/
│
├── README.md
├── requirements.txt
│
├── data/
│   ├── raw/
│   │   ├── customers.csv
│   │   ├── products.csv
│   │   ├── orders.csv
│   │   └── order_items.csv
│   │
│   └── cleaned/
│       ├── customers_cleaned.csv
│       ├── products_cleaned.csv
│       ├── orders_cleaned.csv
│       └── order_items_cleaned.csv
│
├── output/
│   ├── ecommerce.db
│   ├── issue_report.csv
│   └── edge_case_report.csv
│
└── src/
    ├── data_generation.py
    └── Soham_Deshmukh_Week_8.ipynb
```

---

## Project Workflow

The project is completed in five phases.

```text
Raw Data
   ↓
Phase 1 - Data Generation
   ↓
Phase 2 - Data Cleaning & Validation
   ↓
Phase 3 - SQL Analysis
   ↓
Phase 4 - Python + SQL Reporting
   ↓
Phase 5 - Edge Case Testing
```

---

# Phase 1 - Data Generation

The `data_generation.py` file creates synthetic e-commerce data.

The generated data contains:

- 800 customers
- 640 products
- 1,000 orders
- 3,000 order items

The data also contains intentional issues so that the cleaning and validation steps can be tested properly.

Examples include:

- Invalid email addresses
- Missing customer IDs
- Different date formats
- Extra spaces in product names
- Negative quantities representing returns
- Invalid discounts
- Zero quantities
- Future order dates
- Invalid order references

The generated files are stored in:

```text
data/raw/
```

---

# Phase 2 - Data Cleaning and Validation

The notebook loads the raw CSV files and cleans them using Pandas.

The following functions are used:

```text
clean_orders()
clean_products()
validate_emails()
check_unknown_order_ids()
check_invalid_discounts()
check_zero_quantity()
check_future_order_dates()
```

The cleaning process includes:

- Fixing order dates
- Handling missing customer IDs
- Removing extra spaces from product names
- Standardizing product names
- Checking invalid emails
- Checking invalid order references
- Checking invalid discounts
- Checking zero quantities

The cleaned files are saved in:

```text
data/cleaned/
```

An issue report is also generated:

```text
output/issue_report.csv
```

---

# Phase 3 - SQL Analysis

The cleaned data is loaded into:

```text
output/ecommerce.db
```

The database contains four tables:

```text
customers
products
orders
order_items
```

The notebook performs 16 SQL analysis tasks.

## Basic Analysis

1. Revenue per category
2. Top 10 customers
3. Monthly order count
4. Customers without delivered orders
5. Products with more returns than purchases
6. Return rate per category

## Advanced Analysis

7. Running revenue by region
8. Product ranking using `DENSE_RANK`
9. Customer order gaps using `LAG`
10. Multi-level CTE analysis
11. Customer segmentation using `NTILE`
12. Year-over-year revenue comparison
13. First and latest purchased category
14. Cumulative revenue analysis
15. Customer cohort retention
16. Frequently bought together products

---

# Phase 4 - Python + SQL Reporting

The notebook also provides a simple reporting function.

It supports:

```text
daily
weekly
monthly
```

The user provides:

```text
Report Type
Start Date
End Date
```

The report shows:

- Total orders
- Total revenue
- Unique customers
- Top 3 products
- Previous-period revenue
- Revenue percentage change

Example:

```text
Enter report type (daily/weekly/monthly):
Enter start date (YYYY-MM-DD):
Enter end date (YYYY-MM-DD):
```

The report uses the SQLite database created in Phase 3.

---

# Phase 5 - Edge Case Handling

The final phase checks the data for common problems.

The checks are **dynamic** and work on the actual data passed to the functions.

The following cases are checked:

### 1. Unknown Order ID

Checks whether an `order_items` record refers to an order that does not exist.

### 2. Discount Greater Than 100%

Checks for invalid discount values.

### 3. Quantity Equal to Zero

Checks for order items where quantity is zero.

### 4. Future Order Date

Checks whether any order has a date later than the current date.

The results are saved to:

```text
output/edge_case_report.csv
```

---

# Installation

Make sure Python is installed.

Create and activate your virtual environment if required.

Install the packages listed in `requirements.txt`:

```bash
pip install -r requirements.txt
```

---

# How to Run

## Step 1 - Generate Raw Data

From the `WEEK-8` directory:

```bash
python src/data_generation.py
```

This creates the raw CSV files inside:

```text
data/raw/
```

---

## Step 2 - Open the Notebook

Open:

```text
src/Soham_Deshmukh_Week_8.ipynb
```

Run the notebook from the first cell to the last cell.

The notebook performs:

```text
Data Loading
    ↓
Data Cleaning
    ↓
Validation
    ↓
SQLite Loading
    ↓
SQL Analysis
    ↓
Reporting
    ↓
Edge Case Testing
```

---

# Output Files

After running the notebook, the main outputs are:

```text
data/cleaned/
├── customers_cleaned.csv
├── products_cleaned.csv
├── orders_cleaned.csv
└── order_items_cleaned.csv
```

and:

```text
output/
├── ecommerce.db
├── issue_report.csv
└── edge_case_report.csv
```

---

# Technologies Used

- Python
- Pandas
- SQLite
- SQL
- Jupyter Notebook

The project intentionally keeps the implementation simple and uses only the libraries needed for the assignment.

---

# Key SQL Concepts Used

This project gives hands-on practice with:

```text
SELECT
WHERE
GROUP BY
HAVING
ORDER BY
JOIN
LEFT JOIN
CTE
CASE
SUBQUERY
WINDOW FUNCTIONS
DENSE_RANK
LAG
NTILE
FIRST_VALUE
LAST_VALUE
SUM() OVER()
```

It also covers practical analytics such as:

```text
Revenue Analysis
Customer Segmentation
Retention
Cohort Analysis
Return Analysis
Product Pair Analysis
Year-over-Year Growth
```

---

# Author

**Soham Deshmukh**

Data Engineering Intern @ Celebal Technologies

**Week 8 Asssignment/mini project- E-Commerce Order Analytics System**
