# Week 1: Pandas Data Cleaning

## 📋 Objective
Master data cleaning and preprocessing techniques using Python's Pandas library. Learn to handle real-world data quality issues including missing values, duplicates, data type mismatches, and inconsistent formatting.

## 📚 Topics Covered
- Data loading and inspection
- Handling missing values
- Removing duplicates
- Data type conversion
- String manipulation and cleaning
- Data merging and joining
- Exporting cleaned data

## 📁 Folder Structure
```
WEEK-1/
├── Assignment/                    # Main assignment notebook
│   └── WEEK1_Soham_Deshmukh.ipynb
├── Dataset/                       # Raw and processed datasets
│   ├── backpacks.csv             # Sample product data
│   ├── cleaned_dataset.csv       # Processed dataset
│   ├── Combined_dataset.csv      # Merged dataset
│   └── [other product CSVs]      # Additional product categories
├── Output/                        # Generated outputs
└── Images/                        # Visualizations and screenshots
```

## 📊 Dataset
**Source**: Synthetic e-commerce product data  
**Files**: Multiple CSV files for different product categories  
**Size**: ~1000-5000 records per category  
**Key Columns**: Product ID, Name, Category, Price, Rating, Stock, Brand, Features

### Data Quality Issues
- Missing values in multiple columns
- Duplicate records
- Inconsistent data types
- Mixed date formats
- Inconsistent categorical values
- Outliers in numerical columns

## 📝 Assignment
**File**: [WEEK1_Soham_Deshmukh.ipynb](./Assignment/WEEK1_Soham_Deshmukh.ipynb)

### Tasks Completed
1. **Data Loading**: Load multiple CSV files into Pandas DataFrames
2. **Data Inspection**: Check shape, info, and descriptive statistics
3. **Missing Value Handling**: Identify and treat missing values appropriately
4. **Duplicate Removal**: Detect and remove duplicate records
5. **Data Type Conversion**: Convert columns to appropriate data types
6. **String Cleaning**: Standardize text data (case, whitespace, special characters)
7. **Data Merging**: Combine multiple datasets into a unified DataFrame
8. **Data Export**: Save cleaned data to new CSV files

### Key Functions Used
- `pd.read_csv()` - Data loading
- `df.info()`, `df.describe()` - Data inspection
- `df.isnull().sum()` - Missing value detection
- `df.dropna()`, `df.fillna()` - Missing value treatment
- `df.duplicated()`, `df.drop_duplicates()` - Duplicate handling
- `df.astype()` - Data type conversion
- `str.lower()`, `str.strip()` - String cleaning
- `pd.concat()`, `pd.merge()` - Data merging
- `df.to_csv()` - Data export

## 📤 Outputs
- **cleaned_dataset.csv**: Processed dataset with quality issues resolved
- **Combined_dataset.csv**: Merged dataset from multiple product categories
- **Visualizations**: Data quality assessment charts
- **Summary Statistics**: Before/after comparison metrics

## 🖼️ Screenshots
*(Screenshots of data quality visualizations and cleaning process)*

## 🎯 Key Learnings
1. **Data Quality Assessment**: Systematic approach to evaluating data quality
2. **Missing Value Strategies**: When to impute vs. when to remove
3. **Data Type Importance**: Correct data types enable proper analysis
4. **String Standardization**: Importance of consistent text formatting
5. **Memory Optimization**: Efficient data handling techniques
6. **Reproducible Workflows**: Creating reusable data cleaning pipelines

## 🛠️ Technologies Used
- **Python 3.12+**
- **Pandas 2.0+**
- **NumPy** for numerical operations
- **Matplotlib/Seaborn** for visualization (if used)
- **Jupyter Notebook** for interactive development

## 🏃 How to Execute
1. Navigate to the WEEK-1 directory
2. Open the Jupyter notebook:
   ```bash
   jupyter notebook Assignment/WEEK1_Soham_Deshmukh.ipynb
   ```
3. Run cells sequentially
4. Ensure datasets are in the correct relative paths

### Dependencies
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

## 📊 Results
### Before Cleaning
- Multiple missing values across columns
- Duplicate records present
- Inconsistent data types
- Mixed formatting in text fields

### After Cleaning
- Complete dataset with no missing values in key columns
- Unique records only
- Consistent data types throughout
- Standardized text formatting
- Ready for analysis and modeling

### Quality Metrics
- **Missing Values**: Reduced from X% to 0% in key columns
- **Duplicates**: Removed Y duplicate records
- **Data Types**: All columns converted to appropriate types
- **Memory Usage**: Reduced by Z% through optimization

## 🔗 Related Resources
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Data Cleaning with Pandas Tutorial](https://pandas.pydata.org/docs/getting_started/intro_tutorials/06_calculate_statistics.html)
- [Real Python Data Cleaning Guide](https://realpython.com/python-data-cleaning-numpy-pandas/)

## 📝 Notes
- All data transformations are documented in the notebook
- Original datasets are preserved in the Dataset folder
- Cleaning decisions are justified with comments
- The workflow is reproducible and can be applied to similar datasets

---

*This week's assignment demonstrates foundational data cleaning skills essential for any data engineering or data science workflow. The techniques learned here form the basis for more advanced data processing in subsequent weeks.*