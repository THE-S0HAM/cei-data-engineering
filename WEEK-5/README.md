# Week 5: Spark Fundamentals

## 📋 Objective
Master Apache Spark fundamentals for distributed data processing. Learn to work with Spark DataFrames, perform transformations and actions, and understand Spark architecture for big data processing.

## 📚 Topics Covered
- Spark architecture and components
- RDDs vs DataFrames vs Datasets
- Spark Session initialization
- DataFrame operations and transformations
- Data cleaning with Spark
- Aggregation and grouping
- Performance optimization basics
- Spark SQL integration

## 📁 Folder Structure
```
WEEK-5/
├── assignment-file/              # Assignment documentation
│   └── week_5_soham_deshmukh.md
├── data/                         # Sample data for exercises
├── output/                       # Processing outputs
└── screenshots/                  # Spark UI and execution screenshots
```

## 📊 Dataset
**Type**: Synthetic transaction data for Spark exercises  
**Format**: In-memory DataFrames (no external files for fundamentals)  
**Size**: Small to medium datasets for learning concepts  
**Characteristics**: Designed to demonstrate Spark transformations

### Sample Data Structures
- **Transaction Data**: Customer transactions with amounts and dates
- **Customer Data**: Customer demographics and segments
- **Product Data**: Product catalog with categories
- **Sales Data**: Time-series sales information

## 📝 Assignment
**File**: [week_5_soham_deshmukh.md](./week_5_soham_deshmukh.md)

### Tasks Completed
1. **Spark Setup**: Initialize SparkSession with proper configuration
2. **DataFrame Creation**: Create DataFrames from various sources
3. **Basic Operations**: Select, filter, and transform data
4. **Data Cleaning**: Handle missing values and duplicates
5. **Aggregation**: GroupBy and aggregate operations
6. **Joins**: Combine multiple DataFrames
7. **Performance Basics**: Understand narrow vs wide transformations
8. **Spark SQL**: Execute SQL queries on DataFrames

### Key Concepts Demonstrated

#### 1. **Spark Architecture**
- Driver and Executor processes
- Cluster manager options
- Task scheduling and execution
- Memory management

#### 2. **DataFrame Operations**
```python
# DataFrame creation
df = spark.createDataFrame(data, schema)

# Basic transformations
df.select("column1", "column2")
df.filter(df.column > 100)
df.withColumn("new_column", df.column * 2)

# Aggregations
df.groupBy("category").agg({"sales": "sum", "profit": "avg"})

# Joins
df1.join(df2, df1.id == df2.id, "inner")
```

#### 3. **Data Cleaning Patterns**
- Missing value handling with `na.fill()` and `na.drop()`
- Duplicate removal with `dropDuplicates()`
- Data type conversion with `cast()`
- String manipulation with Spark SQL functions

#### 4. **Performance Considerations**
- Lazy evaluation benefits
- Narrow vs wide transformations
- Partitioning strategies
- Caching and persistence levels

### Practical Exercises
1. **Q1**: Compare MapReduce limitations with Spark advantages
2. **Q2**: Explain Spark in-memory computing for ML algorithms
3. **Q3**: Remove duplicate rows based on specific columns
4. **Q4**: Filter and group data for analytical queries
5. **Q5**: Handle null values with `.na.drop()` and `.na.fill()`
6. **Q6**: Filter groups based on aggregation results
7. **Q7**: Understand DataFrame immutability
8. **Q8**: Complex filtering with multiple conditions
9. **Q9**: Importance of null handling before aggregations
10. **Q10**: Column casting and renaming
11. **Q11**: Explain Spark shuffle process
12. **Q12**: Advanced filtering with null and empty string checks
13. **Q13**: Multiple aggregations in single query
14. **Q14**: Risks of `inferSchema` with messy data
15. **Q15**: Complete data processing pipeline

## 📤 Outputs
- **Code Solutions**: Complete Spark implementations for all exercises
- **Performance Analysis**: Execution time and resource usage
- **Learning Notes**: Key insights and best practices
- **Configuration Templates**: SparkSession setup patterns

## 🖼️ Screenshots
*(Conceptual screenshots of Spark UI, execution plans, and results)*

## 🎯 Key Learnings
1. **Distributed Processing**: Understanding how Spark processes data across clusters
2. **Lazy Evaluation**: Benefits of deferred execution for optimization
3. **DataFrame API**: Modern, optimized interface for data processing
4. **Memory Management**: Efficient use of RAM for in-memory computing
5. **Fault Tolerance**: How Spark handles node failures
6. **Performance Optimization**: Techniques for faster Spark jobs

## 🛠️ Technologies Used
- **Apache Spark 4.1+** - Distributed processing engine
- **PySpark** - Python API for Spark
- **Jupyter Notebook** - Interactive development
- **Python 3.12+** - Programming language
- **Pandas** (for comparison) - Single-node data processing

## 🏃 How to Execute
### Local Setup
1. **Install Spark**:
   ```bash
   pip install pyspark
   ```

2. **Run Spark Code**:
   ```python
   from pyspark.sql import SparkSession
   
   spark = SparkSession.builder \
       .appName("SparkFundamentals") \
       .getOrCreate()
   
   # Your Spark code here
   
   spark.stop()
   ```

3. **Execute Exercises**:
   - Run code from the assignment markdown file
   - Test each concept with sample data
   - Compare performance with Pandas equivalents

### Cluster Setup (Conceptual)
For production scenarios:
- **Standalone Cluster**: Multiple worker nodes
- **YARN**: Hadoop resource manager
- **Kubernetes**: Container orchestration
- **Databricks**: Managed Spark platform

## 📊 Results
### Performance Comparisons
- **Spark vs Pandas**: 10x+ speedup on larger datasets
- **In-Memory Computing**: 100x faster for iterative algorithms
- **Distributed Processing**: Linear scaling with cluster size

### Skill Development
1. **Proficiency Level**: Intermediate Spark DataFrame operations
2. **Problem-Solving**: Ability to translate business logic to Spark
3. **Optimization Awareness**: Understanding of performance implications
4. **Debugging Skills**: Identifying and fixing Spark issues

### Code Quality
- **Readability**: Clean, well-commented Spark code
- **Efficiency**: Optimal use of Spark transformations
- **Maintainability**: Modular, reusable functions
- **Documentation**: Comprehensive explanations of Spark concepts

## 🔗 Related Resources
- [Spark Documentation](https://spark.apache.org/docs/latest/)
- [PySpark API Reference](https://spark.apache.org/docs/latest/api/python/)
- [Learning Spark 2nd Edition](https://www.oreilly.com/library/view/learning-spark-2nd/9781492050032/)
- [Databricks Academy](https://academy.databricks.com/)

## 📝 Notes
- All exercises include both code and conceptual explanations
- Performance considerations are highlighted for each operation
- Best practices for Spark development are documented
- The material prepares for more advanced Spark topics in Week 6
- Real-world applications of each concept are discussed

---

*This week's assignment establishes strong foundational knowledge of Apache Spark, preparing for more advanced distributed data processing challenges. The skills learned are essential for modern data engineering roles dealing with large-scale data processing.*