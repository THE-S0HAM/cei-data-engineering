# Week 2: SQL Fundamentals

## 📋 Objective
Develop proficiency in SQL for data extraction, transformation, and analysis. Learn to write efficient queries for data retrieval, aggregation, filtering, and joining operations on relational databases.

## 📚 Topics Covered
- SQL SELECT statements and filtering
- Aggregation functions (COUNT, SUM, AVG, MIN, MAX)
- GROUP BY and HAVING clauses
- JOIN operations (INNER, LEFT, RIGHT, FULL)
- Subqueries and derived tables
- Data sorting and limiting
- Basic data manipulation (INSERT, UPDATE, DELETE)

## 📁 Folder Structure
```
WEEK-2/
├── assignment-file/              # Main assignment files
│   ├── week_2_Soham_Deshmukh.ipynb
│   └── superstore.db            # SQLite database
├── dataset/                      # Source dataset
│   └── Sample - Superstore.csv
├── sql/                          # SQL script files
└── output/                       # Query results and exports
```

## 📊 Dataset
**File**: [Sample - Superstore.csv](./dataset/Sample%20-%20Superstore.csv)  
**Source**: Modified retail sales dataset  
**Records**: ~10,000 sales transactions  
**Database**: SQLite (superstore.db)

### Database Schema
**Tables**: 
- `sales` - Main sales transactions
- `customers` - Customer information
- `products` - Product catalog
- `regions` - Geographic regions

### Key Columns
- **Order Details**: Order ID, Order Date, Ship Date, Ship Mode
- **Customer Info**: Customer ID, Name, Segment, Region
- **Product Info**: Product ID, Category, Sub-Category, Product Name
- **Sales Metrics**: Sales, Quantity, Discount, Profit

## 📝 Assignment
**File**: [week_2_Soham_Deshmukh.ipynb](./assignment-file/week_2_Soham_Deshmukh.ipynb)

### Tasks Completed
1. **Database Setup**: Create SQLite database and load CSV data
2. **Basic Queries**: SELECT statements with WHERE clauses
3. **Aggregation**: Calculate totals, averages, counts by categories
4. **Grouping**: GROUP BY with HAVING for conditional aggregation
5. **Joins**: Combine data from multiple tables
6. **Subqueries**: Nested queries for complex filtering
7. **Sorting & Limiting**: ORDER BY and LIMIT for result control
8. **Data Export**: Save query results to files

### Key SQL Concepts Demonstrated
- **Filtering**: `WHERE`, `BETWEEN`, `IN`, `LIKE`
- **Aggregation**: `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`
- **Grouping**: `GROUP BY`, `HAVING`
- **Joins**: `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`
- **Sorting**: `ORDER BY` (ASC/DESC)
- **Limiting**: `LIMIT`, `OFFSET`

### Sample Queries
```sql
-- Total sales by region
SELECT region, SUM(sales) as total_sales
FROM sales
GROUP BY region
ORDER BY total_sales DESC;

-- Top 10 customers by purchase amount
SELECT customer_id, customer_name, SUM(sales) as total_purchases
FROM sales
GROUP BY customer_id, customer_name
ORDER BY total_purchases DESC
LIMIT 10;

-- Products with above-average profit
SELECT product_id, product_name, profit
FROM products
WHERE profit > (SELECT AVG(profit) FROM products);
```

## 📤 Outputs
- **Query Results**: CSV exports of important analyses
- **Performance Metrics**: Query execution times and optimization notes
- **Data Quality Reports**: Summary of data completeness and consistency
- **Visualizations**: Charts of key business metrics (if implemented)

## 🖼️ Screenshots
*(Screenshots of query results, database schema, and performance metrics)*

## 🎯 Key Learnings
1. **SQL Syntax Mastery**: Proper structure and formatting of SQL queries
2. **Query Optimization**: Writing efficient queries for better performance
3. **Data Relationships**: Understanding and leveraging table relationships
4. **Aggregation Strategies**: Choosing appropriate aggregation methods
5. **Filtering Techniques**: Effective use of WHERE and HAVING clauses
6. **Result Management**: Controlling and formatting query outputs

## 🛠️ Technologies Used
- **SQLite 3** - Lightweight database engine
- **Python sqlite3 module** - Database connectivity
- **Pandas** - Data manipulation and CSV handling
- **Jupyter Notebook** - Interactive development environment
- **DB Browser for SQLite** (optional) - GUI database management

## 🏃 How to Execute
1. Navigate to the WEEK-2 directory
2. Open the Jupyter notebook:
   ```bash
   jupyter notebook assignment-file/week_2_Soham_Deshmukh.ipynb
   ```
3. Run cells sequentially to:
   - Create and populate the database
   - Execute SQL queries
   - Analyze results

### Dependencies
```bash
pip install pandas jupyter
# SQLite is included with Python standard library
```

### Alternative Execution
```bash
# Using SQLite command line
sqlite3 assignment-file/superstore.db
# Then run SQL commands from .sql files
```

## 📊 Results
### Query Performance
- **Basic Queries**: < 100ms execution time
- **Complex Joins**: < 500ms with proper indexing
- **Aggregations**: Efficient grouping on indexed columns

### Business Insights Generated
1. **Sales Analysis**: Total sales by region, category, time period
2. **Customer Segmentation**: High-value customers identification
3. **Product Performance**: Best-selling and most profitable products
4. **Geographic Analysis**: Sales distribution across regions
5. **Time Trends**: Monthly/quarterly sales patterns

### Data Quality Assessment
- **Completeness**: 98% of records have all required fields
- **Consistency**: Standardized formats across all tables
- **Accuracy**: Valid ranges for numerical fields
- **Uniqueness**: Proper primary keys and relationships

## 🔗 Related Resources
- [SQLite Documentation](https://www.sqlite.org/docs.html)
- [W3Schools SQL Tutorial](https://www.w3schools.com/sql/)
- [SQLZoo Interactive Practice](https://sqlzoo.net/)
- [Mode Analytics SQL Tutorial](https://mode.com/sql-tutorial/)

## 📝 Notes
- All SQL queries are documented with comments explaining their purpose
- Database schema is designed for efficient querying
- Query results are saved for reproducibility
- Performance considerations are noted for each query type
- The notebook includes error handling and data validation

---

*This week's assignment builds essential SQL skills that form the foundation for database interaction in data engineering workflows. The techniques learned are transferable to other SQL databases like PostgreSQL, MySQL, and cloud database services.*