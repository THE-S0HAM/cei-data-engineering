# E-Commerce Order Analytics System

A complete **E-Commerce Order Analytics System** developed as part of the **Week 8 Data Engineering Internship Assignment at Celebal Technologies**.

The project demonstrates an end-to-end data engineering workflow starting from raw e-commerce data generation and cleaning, followed by validation, SQLite database creation, SQL-based analytics, reporting, and dynamic edge-case testing.

The project is implemented primarily in a **Jupyter Notebook** and is also deployed as a **live web application hosted on an Azure Virtual Machine**.

🌐 **Live Demo:**  
https://e-com-order-platform.sohamdeshmukh.me/

---

## Project Overview

The E-Commerce Order Analytics System processes raw e-commerce data and converts it into clean, validated, and analysis-ready data.

The complete workflow includes:

```text
Raw E-Commerce Data
        ↓
Data Generation
        ↓
Data Cleaning & Validation
        ↓
SQLite Database
        ↓
SQL Analytics
        ↓
Python + SQL Reporting
        ↓
Dynamic Edge-Case Testing
        ↓
Analytics Dashboard
        ↓
Azure VM Deployment
```

The project was designed to demonstrate practical data engineering concepts using **Python, Pandas, SQLite, SQL, and Jupyter Notebook**, along with deployment of the application on an **Azure Virtual Machine**.

---

# Project Objectives

- Generate realistic synthetic e-commerce data
- Clean and validate raw datasets
- Handle missing and incorrect data
- Validate email addresses
- Validate referential integrity
- Detect invalid business values
- Store cleaned data in SQLite
- Perform SQL-based business analysis
- Apply advanced SQL concepts
- Generate dynamic sales reports
- Perform customer and product analysis
- Detect data quality and edge-case issues
- Deploy the analytics application on Azure
- Provide a simple web interface for accessing the analytics system

---

# What This Project Covers

## Data Engineering

- Synthetic data generation
- Data ingestion
- Data cleaning
- Data validation
- Data quality checks
- Missing value handling
- Data standardization
- Referential integrity
- Issue reporting
- Edge-case testing

## Database

- SQLite database creation
- Table creation
- Data loading
- Primary and foreign-key relationships
- SQL querying

## SQL Analytics

- Aggregations
- Joins
- Subqueries
- CTEs
- CASE expressions
- Window functions
- `DENSE_RANK`
- `LAG`
- `NTILE`
- `FIRST_VALUE`
- `LAST_VALUE`
- Running totals
- Cumulative analysis

## Business Analytics

- Revenue analysis
- Customer segmentation
- Customer retention
- Cohort analysis
- Return analysis
- Product ranking
- Frequently bought together products
- Year-over-year revenue comparison
- Daily, weekly, and monthly sales reporting

## Deployment

- Azure Virtual Machine
- Web application deployment
- Production-hosted analytics application

---

# Project Architecture

```text
                         ┌─────────────────────┐
                         │   Raw CSV Dataset   │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ Data Cleaning &     │
                         │ Validation (Pandas) │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ Cleaned CSV Files   │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ SQLite Database     │
                         │ ecommerce.db        │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ SQL Analytics       │
                         │ & Window Functions  │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ Python + SQL        │
                         │ Reporting           │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ Edge Case & Data    │
                         │ Quality Testing     │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ Analytics Web App   │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │   Azure VM Hosting  │
                         └─────────────────────┘
```

---

# Project Structure

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

# Project Workflow

The project is divided into five major phases.

```text
Phase 1
Data Generation
       ↓
Phase 2
Data Cleaning & Validation
       ↓
Phase 3
SQL Analysis
       ↓
Phase 4
Python + SQL Reporting
       ↓
Phase 5
Dynamic Edge-Case Testing
```

---

# Phase 1 - Data Generation

The `data_generation.py` script generates synthetic e-commerce datasets.

The generated dataset contains:

| Dataset | Records |
|---|---:|
| Customers | 800 |
| Products | 640 |
| Orders | 1,000 |
| Order Items | 3,000 |

The generated data intentionally contains several data quality issues to simulate real-world datasets.

Examples include:

- Invalid email addresses
- Missing customer IDs
- Different date formats
- Extra spaces in product names
- Negative quantities representing returns
- Invalid discount values
- Zero quantities
- Future order dates
- Invalid order references

The generated raw datasets are stored in:

```text
data/raw/
```

---

# Phase 2 - Data Cleaning & Validation

The Jupyter Notebook loads the raw datasets using Pandas and performs data cleaning and validation.

Important functions include:

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

- Cleaning order dates
- Handling missing customer IDs
- Removing unnecessary spaces
- Standardizing product names
- Validating email addresses
- Checking invalid order references
- Validating discount values
- Detecting zero quantities
- Detecting future order dates

The cleaned datasets are stored in:

```text
data/cleaned/
```

A consolidated issue report is generated as:

```text
output/issue_report.csv
```

---

# Phase 3 - SQLite Database & SQL Analysis

The cleaned datasets are loaded into:

```text
output/ecommerce.db
```

The SQLite database contains four primary tables:

```text
customers
products
orders
order_items
```

The project performs **16 SQL-based analytical tasks**.

## Basic SQL Analysis

1. Revenue per category
2. Top 10 customers
3. Monthly order count
4. Customers without delivered orders
5. Products with more returns than purchases
6. Return rate per category

## Advanced SQL Analysis

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

The project provides a dynamic reporting function that supports:

```text
Daily
Weekly
Monthly
```

The user provides:

```text
Report Type
Start Date
End Date
```

The reporting system generates:

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

The report dynamically queries the SQLite database and generates the requested results.

---

# Phase 5 - Dynamic Edge-Case Testing

The final phase performs data quality and edge-case checks on the actual datasets.

The checks are implemented dynamically so they can operate on the data passed to the functions rather than depending on one fixed dataset.

## Edge Cases Checked

### 1. Unknown Order ID

Checks whether an `order_items` record references an order that does not exist.

### 2. Discount Greater Than 100%

Identifies invalid discount values.

### 3. Quantity Equal to Zero

Identifies order items where the quantity is zero.

### 4. Future Order Date

Checks whether an order contains a date later than the current date.

The results are stored in:

```text
output/edge_case_report.csv
```

---

# Output Files

After running the project, the main outputs include:

```text
data/cleaned/
│
├── customers_cleaned.csv
├── products_cleaned.csv
├── orders_cleaned.csv
└── order_items_cleaned.csv
```

Database:

```text
output/
└── ecommerce.db
```

Validation reports:

```text
output/
├── issue_report.csv
└── edge_case_report.csv
```

---

# Technologies Used

| Technology | Purpose |
|---|---|
| Python | Data processing and application logic |
| Pandas | Data cleaning and validation |
| SQLite | Relational data storage |
| SQL | Data analysis |
| Jupyter Notebook | Development and analysis |
| Azure VM | Application hosting |
| HTML/CSS/JavaScript | Web interface |

---

# SQL Concepts Demonstrated

The project provides practical implementation of:

```text
SELECT
WHERE
GROUP BY
HAVING
ORDER BY
JOIN
LEFT JOIN
CASE
SUBQUERY
CTE
WINDOW FUNCTIONS
DENSE_RANK
LAG
NTILE
FIRST_VALUE
LAST_VALUE
SUM() OVER()
```

---

# Business Insights

The system supports analysis of:

```text
Revenue
Orders
Customers
Products
Returns
Customer Segmentation
Customer Retention
Cohort Analysis
Product Rankings
Product Relationships
Year-over-Year Growth
```

These analyses demonstrate how cleaned transactional data can be transformed into useful business insights.

---

# Deployment

The project has been deployed as a live web application on a **Microsoft Azure Virtual Machine**.

The deployment allows users to access the project through a web browser without manually running the Jupyter Notebook.

### Hosting

```text
Cloud Platform : Microsoft Azure
Compute        : Azure Virtual Machine
Application    : E-Commerce Order Analytics System
```

### Live Application

🌐 **https://e-com-order-platform.sohamdeshmukh.me/**

---

# Running the Project Locally

## 1. Clone the Repository

```bash
git clone <repository-url>
cd WEEK-8
```

## 2. Install Dependencies

```bash
pip install -r requirements.txt
```

## 3. Generate Raw Data

```bash
python src/data_generation.py
```

The generated files will be stored in:

```text
data/raw/
```

## 4. Open the Jupyter Notebook

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
Data Validation
      ↓
SQLite Database Creation
      ↓
SQL Analysis
      ↓
Python + SQL Reporting
      ↓
Edge-Case Testing
```

---

# Live Demo

The complete project is available online:

**E-Commerce Order Analytics System**

🌐 https://e-com-order-platform.sohamdeshmukh.me/

The live deployment demonstrates the project beyond the notebook environment by providing a browser-accessible interface for the analytics workflow.

---

# Learning Outcomes

Through this project, the following practical skills were developed:

- Working with raw datasets
- Data cleaning using Pandas
- Data validation
- Data quality analysis
- Relational database design
- SQLite integration
- SQL analytics
- Advanced SQL window functions
- CTE-based analysis
- Customer segmentation
- Cohort analysis
- Business reporting
- Dynamic edge-case handling
- Generating validation reports
- Deploying a data application on Azure

---

# Author

**Soham Deshmukh**

Data Engineering Intern  
**Celebal Technologies**

### Week 8 Internship Assignment / Mini Project

**E-Commerce Order Analytics System**

🌐 Live Demo:  
https://e-com-order-platform.sohamdeshmukh.me/
