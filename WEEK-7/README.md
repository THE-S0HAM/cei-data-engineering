# Week 7 – Delta Lake MERGE Implementation

## Overview

This project demonstrates how to perform **incremental data processing** using **Apache Spark** and **Delta Lake**. The assignment focuses on implementing the **MERGE (Upsert)** operation to efficiently update existing records and insert new records into a Delta table.

The implementation uses the **Sample Superstore** dataset and follows the Week 7 assignment requirements of the **Celebal Excellence Internship (CEI) – Data Engineering Track**.

---

## Assignment Objective

The main objective of this assignment is to:

- Load a dataset into a Delta Lake table.
- Perform basic data cleaning.
- Create a second dataset to simulate incremental data.
- Apply the Delta Lake **MERGE** operation.
- Validate the final output.
- Understand how Delta Lake supports incremental data processing.

---

## Technologies Used

- Python 3
- Apache Spark (PySpark)
- Delta Lake
- Jupyter Notebook
- Pandas

---

## Project Structure

```text
WEEK-7/
│
├── data/
│   ├── Sample-Superstore.csv
│   └── Superstore_Incremental.csv
│
├── delta/
│   └── superstore/
│
├── notebooks/
│   └── delta_merge_assignment.ipynb
│
├── screenshots/
│   ├── 01_spark_session.png
│   ├── 02_load_dataset.png
│   ├── 03_data_cleaning.png
│   ├── 04_delta_table.png
│   ├── 05_merge_statistics.png
│   ├── 06_merge_operation.png
│   ├── 07_validation.png
│   ├── 08_final_dataset.png
│   ├── 09_updated_records.png
│   └── 10_new_records.png
│
└── README.md
```

---

## Workflow

### Step 1 – Create Spark Session

- Configured Apache Spark with Delta Lake support.
- Verified the Spark session and environment setup.

### Step 2 – Load Dataset

- Loaded the **Sample Superstore** dataset into a PySpark DataFrame.
- Verified the schema and total number of records.

### Step 3 – Data Cleaning

Performed basic preprocessing by:

- Checking duplicate records
- Checking missing values
- Filling missing values (where applicable)
- Standardizing column names
- Converting important columns to appropriate data types

### Step 4 – Create Delta Table

- Saved the cleaned dataset as a Delta Lake table.
- Verified that the Delta table was created successfully.

### Step 5 – Create Incremental Dataset

Created a second dataset to simulate incoming data by:

- Updating existing records
- Creating new records with unique identifiers
- Combining both datasets into a single incremental dataset

### Step 6 – Apply Delta MERGE

Performed the Delta Lake **MERGE** operation to:

- Update existing records
- Insert new records
- Maintain a single updated Delta table

### Step 7 – Validate Results

Validated the final output by:

- Checking total row count
- Checking duplicate records
- Checking null values
- Displaying the final merged dataset

---

## Results

The MERGE operation successfully:

- Updated existing records in the Delta table.
- Inserted new records from the incremental dataset.
- Maintained data consistency using **Row_ID** as the unique merge key.
- Verified the final dataset through row count, duplicate checks, and null value validation.

---

## Screenshots

The repository includes screenshots of each major step performed during the assignment.

| Screenshot | Description |
|------------|-------------|
| 01_spark_session.png | Spark Session initialization |
| 02_load_dataset.png | Dataset loading and schema verification |
| 03_data_cleaning.png | Data cleaning and preprocessing |
| 04_delta_table.png | Delta table creation |
| 05_merge_statistics.png | MERGE operation statistics |
| 06_merge_operation.png | Successful MERGE execution |
| 07_validation.png | Validation of the final dataset |
| 08_final_dataset.png | Final Delta table preview |
| 09_updated_records.png | Updated records after MERGE |
| 10_new_records.png | Newly inserted records |

---

## Learning Outcomes

Through this assignment, I learned how to:

- Configure and use Delta Lake with Apache Spark.
- Create and manage Delta tables.
- Perform incremental data processing using the MERGE operation.
- Handle updates and inserts efficiently using Delta Lake.
- Validate processed data using PySpark DataFrame operations.
- Build a simple end-to-end Delta Lake workflow for batch data processing.

---

## Assignment Summary

In this assignment, I implemented an incremental data processing workflow using **PySpark** and **Delta Lake** with the Sample Superstore dataset. The project covered loading data into a Delta table, performing data cleaning, creating an incremental dataset, applying the Delta Lake **MERGE** operation, validating the results, and displaying the final merged dataset. This assignment provided practical experience in handling incremental data processing and demonstrated how Delta Lake simplifies update and insert operations in modern data engineering workflows.
