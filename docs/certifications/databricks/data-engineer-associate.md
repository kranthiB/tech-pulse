---
id: certifications/databricks/data-engineer-associate
title: Databricks Data Engineer Associate Certification
sidebar_label: Databricks Data Engineer Associate Certification
previous_page: certifications/databricks/data-analyst-associate
---

<div style="text-align: right;">
    <a href="https://kranthib.github.io/tech-pulse/" style="display: inline-block; padding: 6px 14px; background-color: #2054a6; color: white; text-decoration: none; border-radius: 3px; font-size: 14px; font-weight: 500; transition: background-color 0.3s;">Back to Home →</a>
</div>

# Databricks Data Analyst Associate Certification

Table of contents
=================

<!--ts-->
  * [Preparation Plan](#preparation-plan)
    * [Foundations & Databricks Lakehouse Platform](#foundations--databricks-lakehouse-platform)
    * [ELT with Apache Spark](#elt-with-apache-spark)
    * [Incremental Data Processing](#incremental-data-processing)
    * [Production Pipelines & Data Governance](#production-pipelines--data-governance)
  * [Knowledge Base](#knowledge-base)
    * [Foundations & Databricks Lakehouse Platform](#foundations--databricks-lakehouse-platform-1)
      * [Databricks Fundamentals](#databricks-fundamentals)
      * [Advanced Databricks Features](#advanced-databricks-features)
      * [Assessment Quiz](#assessment-quiz)
      * [Hands-On Exercises](#hands-on-exercises)
      * [Key Takeaways](#key-takeaways)
    * [ELT with Apache Spark](#elt-with-apache-spark-1)
      * [Data Extraction and Basic Transformations](#data-extraction-and-basic-transformations)
      * [Hands-on Exercise: Building an ETL Pipeline](#hands-on-exercise-building-an-etl-pipeline)
      * [Advanced Transformations](#advanced-transformations)
      * [Hands-on Exercise: Advanced Transformations](#hands-on-exercise-advanced-transformations)
      * [Assessment Quiz](#assessment-quiz-1)
      * [Key Takeaways](#key-takeaways-1)
    * [Incremental Data Processing](#incremental-data-processing-1)
      * [Delta Lake and ACID Transactions](#delta-lake-and-acid-transactions)
      * [Delta Lake Operations and Optimizations](#delta-lake-operations-and-optimizations)
      * [Incremental Data Loading](#incremental-data-loading)
      * [Assessment Quiz](#assessment-quiz-2)
      * [Key Takeaways](#key-takeaways-2)
    * [Production Pipelines & Data Governance](#production-pipelines--data-governance-1)
      * [Production Pipelines](#production-pipelines)
      * [Hands-on Exercise: Creating a Production Pipeline](#hands-on-exercise-creating-a-production-pipeline)
      * [Data Governance](#data-governance)
      * [Hands-on Exercise: Implementing Data Governance](#hands-on-exercise-implementing-data-governance)
      * [Assessment Quiz](#assessment-quiz-3)
      * [Key Takeaways](#key-takeaways-3)
        
<!--te-->

# Preparation Plan

## Foundations & Databricks Lakehouse Platform

- Databricks Fundamentals
- Advanced Databricks Features
- Assessment Quiz
- Hands-On Exercises
- Key Takeaways

---

## ELT with Apache Spark

- Data Extraction and Basic Transformations
- Hands-on Exercise: Building an ETL Pipeline
- Advanced Transformations
- Hands-on Exercise: Advanced Transformations
- Assessment Quiz

---

## Incremental Data Processing

- Delta Lake and ACID Transactions
- Delta Lake Operations and Optimizations
- Incremental Data Loading
- Assessment Quiz
- Key Takeaways

---

## Production Pipelines & Data Governance

- Production Pipelines
- Hands-on Exercise: Creating a Production Pipeline
- Data Governance
- Hands-on Exercise: Implementing Data Governance
- Assessment Quiz
- Key Takeaways

---


# Knowledge Base

## Foundations & Databricks Lakehouse Platform

### Databricks Fundamentals

#### Introduction to Databricks

Databricks is a unified data analytics platform that combines data engineering, data science, and business analytics into a single, integrated environment. Founded by the creators of Apache Spark, Databricks provides an enterprise-grade, cloud-based platform that enables organizations to process and analyze massive datasets efficiently.

**Key Components of the Databricks Platform:**

The Databricks platform consists of several integrated components:

1. **Workspace** - The web-based interface where users interact with Databricks
2. **Notebooks** - Interactive documents for writing and executing code
3. **Clusters** - Compute resources that execute the code written in notebooks
4. **Jobs** - Scheduled or triggered execution of notebooks or other code
5. **Data** - Storage and management of datasets in various formats

#### Lakehouse Architecture Fundamentals

The data lakehouse architecture represents a modern approach to data management that combines the best features of data warehouses and data lakes.

**Data Lakehouse vs. Data Warehouse vs. Data Lake:**

| Feature | Data Lake | Data Warehouse | Data Lakehouse |
|---------|-----------|----------------|----------------|
| Data Structure | Unstructured/semi-structured | Highly structured | Supports all data types |
| Schema | Schema-on-read | Schema-on-write | Schema enforcement with flexibility |
| Data Quality | Limited | High | High |
| Performance | Variable | Optimized | Optimized |
| Cost | Lower storage costs | Higher costs | Balance of cost and performance |
| Use Cases | Data science, ML | BI reporting | Unified analytics |

**The Medallion Architecture:**

The medallion architecture is a data organization framework used in the lakehouse that organizes data into three tiers:

1. **Bronze (Raw)** - Contains raw data ingested from various sources with minimal processing
2. **Silver (Validated)** - Data that has been cleansed, conformed, and validated
3. **Gold (Enriched)** - Business-level aggregates and enriched data ready for consumption

**Benefits of the Lakehouse Approach:**

- Eliminates data silos and reduces data duplication
- Provides a single source of truth for all analytics workloads
- Enables both batch and streaming data processing
- Supports diverse workloads including BI, ML, and data science
- Offers ACID transactions through Delta Lake
- Reduces total cost of ownership through unified architecture

#### Databricks Clusters and Runtimes

Clusters are the computational resources that execute your code in Databricks.

**Types of Clusters:**

1. **All-Purpose Clusters** - Interactive clusters used for development, exploration, and ad-hoc analysis
2. **Jobs Clusters** - Created automatically when jobs are triggered and terminated upon completion

**Databricks Runtime (DBR):**

- The Databricks Runtime is a set of software components optimized to run on the Databricks platform
- Includes Apache Spark plus performance improvements and integrations with other systems
- Available in different versions with varying components and features
- Specialized runtime options include:
  - Standard Runtime (includes Spark)
  - Machine Learning Runtime (includes ML libraries)
  - Genomics Runtime (optimized for genomic data)
  - Light Runtime (minimal dependencies)

**Cluster Termination:**

- All-purpose clusters can be configured to automatically terminate after a period of inactivity
- Jobs clusters terminate automatically upon job completion
- Manual termination stops all running operations and releases compute resources
- Termination does not delete any data or notebooks

---

### Advanced Databricks Features

#### Version Control with Databricks Repos

Databricks Repos enables Git-based version control directly within the Databricks workspace.

**Key Features:**

- Direct integration with Git repositories (GitHub, GitLab, Bitbucket, etc.)
- Support for standard Git operations:
  - Clone repositories
  - Create and switch branches
  - Commit changes
  - Pull latest changes
  - Resolve merge conflicts

**CI/CD Workflows with Repos:**

- Enable automated testing of notebooks
- Facilitate collaborative development
- Support deployment pipeline integration
- Maintain versioning history
- Implement proper change management processes

**Limitations Compared to Traditional Git:**

- Some complex Git operations might require using the Git CLI or external tools
- Large file handling differs from standard Git
- Merge conflict resolution has a different interface than traditional Git tools

#### Multi-Language Notebook Development

Databricks notebooks support multiple programming languages, allowing different cell types within the same notebook.

**Supported Languages:**

- Python (default)
- SQL
- Scala
- R

**Language Switching in Notebooks:**

- Use magic commands to switch between languages:
  - `%python` for Python code
  - `%sql` for SQL queries
  - `%scala` for Scala code
  - `%r` for R code

**Notebook Workflows:**

- Notebooks can call other notebooks using the `%run` command
- Example: `%run /path/to/notebook`
- Variables and functions defined in the called notebook become available in the calling notebook
- This enables modular development and code reuse

#### Hands-On Practice: Creating and Managing Databricks Resources

**Exercise 1: Creating a Cluster**

1. Navigate to the "Compute" section in the Databricks workspace
2. Click "Create Cluster"
3. Configure the cluster with these settings:
   - Cluster name: "DE-Training-Cluster"
   - Cluster mode: "Single Node" (for training purposes)
   - Databricks Runtime: Latest ML version
   - Enable autoscaling: No
   - Terminate after: 120 minutes of inactivity
4. Click "Create Cluster"

**Exercise 2: Creating and Using Notebooks**

1. Navigate to "Workspace" in the sidebar
2. Create a new folder named "DE-Training"
3. Within the folder, create a new notebook:
   - Name: "Day1-Exercises"
   - Language: Python
   - Cluster: Connect to your "DE-Training-Cluster"
4. Execute the following commands in separate cells:

```python
# Python cell
print("Hello from Python!")
```

```sql
-- SQL cell (use %sql magic command)
%sql
SELECT "Hello from SQL!" AS greeting
```

```scala
// Scala cell (use %scala magic command)
%scala
println("Hello from Scala!")
```

**Exercise 3: Exploring the Medallion Architecture**

Create a new notebook and implement a simple medallion architecture:

1. Bronze layer: Read sample data
2. Silver layer: Clean and validate data
3. Gold layer: Aggregate for analytics

---

### Assessment Quiz

1. What is the primary advantage of a data lakehouse over a traditional data warehouse?
   - A) Lower cost
   - B) Support for both structured and unstructured data processing
   - C) Proprietary data formats
   - D) Coupled storage and compute

2. In the medallion architecture, which layer contains raw data with minimal processing?
   - A) Gold
   - B) Silver
   - C) Bronze
   - D) Platinum

3. Which type of Databricks cluster automatically terminates after the workload completes?
   - A) All-purpose cluster
   - B) Jobs cluster
   - C) High-concurrency cluster
   - D) Standard cluster

4. How can you switch to writing SQL code in a Python notebook?
   - A) Use the `%sql` magic command
   - B) Create a new notebook with SQL language
   - C) Import SQL library in Python
   - D) Change notebook settings to SQL

5. What does DBR stand for in the Databricks context?
   - A) Databricks Resource
   - B) Database Runtime
   - C) Databricks Runtime
   - D) Distributed Batch Running

6. Which feature enables Git version control in Databricks?
   - A) Workspace
   - B) Repos
   - C) Clusters
   - D) Jobs

7. How can one notebook call another notebook in Databricks?
   - A) Using the import statement
   - B) Using the `%run` command
   - C) Using notebook workflows
   - D) Using the execute command

8. Which statement about Databricks cluster termination is correct?
   - A) Termination deletes all data stored in the cluster
   - B) Termination stops all running operations and releases compute resources
   - C) Clusters can only be terminated manually
   - D) Terminated clusters cannot be restarted

9. What is a key improvement in data quality that the data lakehouse provides over a traditional data lake?
   - A) Support for ACID transactions
   - B) Lower storage costs
   - C) Faster processing
   - D) More storage capacity

10. Which of the following is a valid magic command in Databricks notebooks?
    - A) `#python`
    - B) `@sql`
    - C) `%scala`
    - D) `!r`

#### Assessment Quiz Answers

1. B) Support for both structured and unstructured data processing
2. C) Bronze
3. B) Jobs cluster
4. A) Use the `%sql` magic command
5. C) Databricks Runtime
6. B) Repos
7. B) Using the `%run` command
8. B) Termination stops all running operations and releases compute resources
9. A) Support for ACID transactions
10. C) `%scala`

---

### Hands-On Exercises

Let's proceed with detailed hands-on exercises to reinforce your understanding of the Databricks Lakehouse Platform. These exercises will give you practical experience with the concepts we've covered.

#### Exercise 1: Setting Up Your Databricks Environment

##### Creating and Configuring a Cluster

1. Navigate to the Compute section in the left sidebar of your Databricks workspace
2. Click the "Create Cluster" button
3. Configure your cluster with these settings:
   - Cluster name: DE-Certification-Cluster
   - Cluster mode: Single Node
   - Databricks Runtime Version: Select the latest version (non-ML)
   - Node type: Select a small instance type (e.g., Standard_DS3_v2 on Azure)
   - Terminate after: 120 minutes of inactivity
   - Under Advanced Options > Spark > Configuration, add:
     ```
     spark.sql.shuffle.partitions 8
     spark.sql.adaptive.enabled true
     ```
4. Click "Create Cluster" and wait for it to start (this may take 3-5 minutes)

##### Exploring the Databricks Workspace

While your cluster starts, explore the workspace:

1. Navigate through the left sidebar menus:
   - Data: Browse available data sources and tables
   - Workflows: View job scheduling capabilities
   - Compute: Return to cluster management
   - Catalog: Explore the data catalog (if available)

#### Exercise 2: Working with Notebooks

##### Creating Your First Notebook

1. Click Workspace in the left sidebar
2. Create a new folder called "DE-Certification"
3. In that folder, click "Create" > "Notebook"
4. Name your notebook "Day1-Foundations" and select "Python" as the default language
5. Select your DE-Certification-Cluster

##### Multi-Language Notebook Operations

1. In the first cell, enter and run the following Python code:
   ```python
   # Python cell
   print("Exploring Databricks Runtime Environment")
   
   # Display Spark version
   print(f"Spark Version: {spark.version}")
   
   # Display Databricks Runtime version
   dbutils.notebook.entry_point.getDbutils().notebook().getContext().apiUrl().get()
   ```

2. In a new cell, switch to SQL and run a simple query:
   ```
   %sql
   -- SQL cell
   SELECT current_timestamp() AS current_time, 
          current_user() AS username, 
          'Databricks Lakehouse Platform' AS platform
   ```

3. In another cell, try Scala:
   ```
   %scala
   // Scala cell
   println("Scala is the native language of Apache Spark")
   val sparkVersion = spark.version
   println(s"Current Spark version: $sparkVersion")
   ```

4. In another cell, switch back to Python and use a display command:
   ```python
   # Create a simple DataFrame
   data = [("Bronze", "Raw data"), 
           ("Silver", "Cleaned data"), 
           ("Gold", "Business-ready data")]
   
   medallic_df = spark.createDataFrame(data, ["Layer", "Description"])
   display(medallic_df)
   ```

#### Exercise 3: Implementing a Simple Medallion Architecture

Let's create a new notebook to implement a basic medallion architecture:

1. Create a new notebook called "Medallion-Architecture-Demo"
2. Run the following cells in sequence:

##### Step 1: Generate Sample Data (Bronze Layer)

```python
# Generate sample sales data
from pyspark.sql import functions as F
import random
from datetime import datetime, timedelta

# Create a sample dataset with some inconsistencies and issues
data = []
start_date = datetime(2023, 1, 1)

# Generate 100 sample records
for i in range(100):
    # Create some data quality issues randomly
    if random.random() < 0.1:
        # Some records have null values
        customer_id = None
    else:
        customer_id = f"CUST-{random.randint(1, 20):04d}"
    
    # Some dates are missing
    if random.random() < 0.05:
        date = None
    else:
        date = (start_date + timedelta(days=random.randint(0, 60))).strftime("%Y-%m-%d")
    
    # Some product IDs have different formats
    if random.random() < 0.15:
        product_id = f"prod-{random.randint(1, 50)}"
    else:
        product_id = f"PROD-{random.randint(1, 50):03d}"
    
    # Some quantities are invalid (negative)
    if random.random() < 0.08:
        quantity = -random.randint(1, 10)
    else:
        quantity = random.randint(1, 10)
    
    # Some prices have incorrect decimal places or are zero
    if random.random() < 0.07:
        price = round(random.random() * 100, random.randint(0, 4))
    else:
        price = round(random.random() * 100, 2)
    
    data.append((customer_id, date, product_id, quantity, price))

# Create a DataFrame
bronze_df = spark.createDataFrame(data, ["customer_id", "date", "product_id", "quantity", "price"])

# Save as a Delta table
bronze_df.write.format("delta").mode("overwrite").saveAsTable("bronze_sales")

# Display the bronze data
print("Bronze Layer Data (Raw):")
display(spark.table("bronze_sales"))
```

##### Step 2: Clean and Validate Data (Silver Layer)

```python
# Read from the bronze layer
bronze_data = spark.table("bronze_sales")

# Clean and validate the data
silver_data = (bronze_data
    # Filter out records with null customer_id or date
    .filter(F.col("customer_id").isNotNull() & F.col("date").isNotNull())
    
    # Standardize product_id format
    .withColumn("product_id", 
        F.when(F.col("product_id").startswith("prod-"), 
               F.concat(F.lit("PROD-"), F.lpad(F.regexp_extract(F.col("product_id"), "prod-(\d+)", 1), 3, "0")))
        .otherwise(F.col("product_id")))
    
    # Ensure quantity is positive
    .withColumn("quantity", 
        F.when(F.col("quantity") <= 0, None)
        .otherwise(F.col("quantity")))
    
    # Ensure price has exactly 2 decimal places and is positive
    .withColumn("price", 
        F.when(F.col("price") <= 0, None)
        .otherwise(F.round(F.col("price"), 2)))
    
    # Convert date string to date type
    .withColumn("date", F.to_date(F.col("date")))
    
    # Add a month column for aggregation in gold layer
    .withColumn("month", F.date_format(F.col("date"), "yyyy-MM"))
)

# Save as a Delta table
silver_data.write.format("delta").mode("overwrite").saveAsTable("silver_sales")

# Display the silver data
print("Silver Layer Data (Cleaned and Validated):")
display(spark.table("silver_sales"))
```

##### Step 3: Create Aggregated Business Views (Gold Layer)

```python
# Read from the silver layer
silver_data = spark.table("silver_sales")

# Create monthly sales summary by product
gold_monthly_product_sales = (silver_data
    .groupBy("month", "product_id")
    .agg(
        F.count("*").alias("transaction_count"),
        F.sum("quantity").alias("total_quantity"),
        F.sum(F.col("quantity") * F.col("price")).alias("total_sales_amount"),
        F.avg("price").alias("average_price")
    )
    .orderBy("month", "product_id")
)

# Save as a Delta table
gold_monthly_product_sales.write.format("delta").mode("overwrite").saveAsTable("gold_monthly_product_sales")

# Create customer spending summary
gold_customer_summary = (silver_data
    .groupBy("customer_id")
    .agg(
        F.countDistinct("date").alias("active_days"),
        F.count("*").alias("transaction_count"),
        F.sum(F.col("quantity") * F.col("price")).alias("total_spend"),
        F.max("date").alias("last_purchase_date")
    )
    .orderBy(F.col("total_spend").desc())
)

# Save as a Delta table
gold_customer_summary.write.format("delta").mode("overwrite").saveAsTable("gold_customer_summary")

# Display the gold layer tables
print("Gold Layer Data - Monthly Product Sales:")
display(spark.table("gold_monthly_product_sales"))

print("Gold Layer Data - Customer Summary:")
display(spark.table("gold_customer_summary"))
```

#### Exercise 4: Running Notebooks from Another Notebook

1. Create a new notebook called "Master-Notebook"
2. Use the %run command to execute our previous notebooks:

```python
# Run the Medallion Architecture notebook
%run /DE-Certification/Medallion-Architecture-Demo

# Now we can work with the tables created in that notebook
print("Accessing Gold Layer tables from the master notebook:")
display(spark.sql("SELECT * FROM gold_monthly_product_sales LIMIT 5"))
```

#### Exercise 5: Working with Databricks Repos (Version Control)

If your Databricks workspace has Repos enabled:

1. Click on "Repos" in the left sidebar
2. Click "Add Repo"
3. For this exercise, you can:
   - Clone a sample repository from GitHub (e.g., https://github.com/databricks-industry-solutions/media-data-lakehouse)
   - Or create a new repo connected to your GitHub (if you have an account)
4. Explore the repository structure
5. Make a small change to a file, commit it, and push (if connected to your personal repo)


---

### Key Takeaways

- The Databricks Lakehouse Platform combines the best features of data warehouses and data lakes
- The medallion architecture (Bronze, Silver, Gold) provides a structured approach to data processing
- Databricks supports multiple programming languages within the same notebook
- Clusters can be configured for different workloads (all-purpose vs. jobs)
- Delta Lake tables provide ACID transactions, improving data reliability
- Databricks Repos enables Git-based version control for your code

---

## ELT with Apache Spark

### Data Extraction and Basic Transformations

#### Data Extraction Techniques

Apache Spark provides versatile capabilities for extracting data from various sources. The Databricks platform enhances these capabilities with optimized readers and connectors.

##### Extracting Data from Files

Spark supports multiple file formats, each with specific readers:

```python
# Reading CSV files
csv_df = spark.read.format("csv") \
    .option("header", "true") \
    .option("inferSchema", "true") \
    .load("/path/to/file.csv")

# Reading Parquet files
parquet_df = spark.read.parquet("/path/to/directory")

# Reading JSON files
json_df = spark.read.json("/path/to/file.json")

# Reading from a directory of files
directory_df = spark.read.format("csv") \
    .option("header", "true") \
    .option("inferSchema", "true") \
    .load("/path/to/directory/*.csv")
```

##### Extracting Data from JDBC Sources

Connecting to relational databases:

```python
jdbc_df = spark.read \
    .format("jdbc") \
    .option("url", "jdbc:postgresql://server:port/database") \
    .option("dbtable", "schema.table") \
    .option("user", "username") \
    .option("password", "password") \
    .load()
```

#### Temporary Tables, Views, and CTEs

Spark SQL offers different ways to reference datasets:

##### Temporary Views

```python
# Creating a temporary view
df.createOrReplaceTempView("temp_view_name")

# Using the temporary view
result = spark.sql("SELECT * FROM temp_view_name WHERE column > 10")
```

Temporary views exist only within the current Spark session.

##### Global Temporary Views

```python
# Creating a global temporary view
df.createOrReplaceGlobalTempView("global_view_name")

# Accessing the global temporary view
result = spark.sql("SELECT * FROM global_temp.global_view_name")
```

Global temporary views exist across all sessions within the same Spark application.

##### Common Table Expressions (CTEs)

CTEs provide a way to write auxiliary statements for use in a larger query:

```sql
-- Using a CTE
WITH revenue_data AS (
  SELECT product_id, SUM(amount) as total_revenue
  FROM sales
  GROUP BY product_id
)
SELECT p.name, r.total_revenue
FROM products p
JOIN revenue_data r ON p.id = r.product_id
ORDER BY r.total_revenue DESC
```

#### Transformation Fundamentals with Spark SQL

Spark SQL provides a comprehensive set of functions for data manipulation:

##### Basic Transformations

```python
# Filtering data
filtered_df = df.filter(df.age > 25)
# SQL equivalent
spark.sql("SELECT * FROM people WHERE age > 25")

# Selecting columns
selected_df = df.select("name", "age", "department")
# SQL equivalent
spark.sql("SELECT name, age, department FROM people")

# Adding new columns
enhanced_df = df.withColumn("age_group", 
                          when(df.age < 18, "minor")
                         .when(df.age < 65, "adult")
                         .otherwise("senior"))
# SQL equivalent
spark.sql("""
  SELECT *, 
    CASE 
      WHEN age < 18 THEN 'minor'
      WHEN age < 65 THEN 'adult'
      ELSE 'senior'
    END as age_group
  FROM people
""")
```

##### Aggregations

```python
# Grouping and aggregating
agg_df = df.groupBy("department").agg(
    avg("salary").alias("avg_salary"),
    count("*").alias("employee_count"),
    sum("salary").alias("total_salary")
)

# SQL equivalent
spark.sql("""
  SELECT 
    department, 
    AVG(salary) as avg_salary,
    COUNT(*) as employee_count,
    SUM(salary) as total_salary
  FROM people
  GROUP BY department
""")
```

#### Working with DataFrames and Tables

##### Converting DataFrames to Delta Tables

```python
# Saving as a managed Delta table
df.write.format("delta").saveAsTable("database_name.table_name")

# Saving as an external Delta table
df.write.format("delta").option("path", "/path/to/data").saveAsTable("database_name.table_name")

# Overwriting data
df.write.format("delta").mode("overwrite").saveAsTable("database_name.table_name")

# Appending data
df.write.format("delta").mode("append").saveAsTable("database_name.table_name")
```

##### Reading from Delta Tables

```python
# Reading a Delta table
table_df = spark.read.table("database_name.table_name")

# Alternative syntax
table_df = spark.table("database_name.table_name")

# SQL equivalent
table_df = spark.sql("SELECT * FROM database_name.table_name")
```

---

### Hands-on Exercise: Building an ETL Pipeline

Let's create a basic ETL pipeline that extracts data from a CSV file, transforms it, and loads it into a Delta table:

1. First, we'll create sample data:

```python
# Create a sample dataset
from pyspark.sql import functions as F

# Generate sample customer data
data = [
    (1, "John Smith", "1980-05-15", "New York", 35000),
    (2, "Mary Johnson", "1992-07-22", "Los Angeles", 42000),
    (3, "James Brown", "1975-11-03", "Chicago", 55000),
    (4, "Patricia Davis", "1988-03-29", "Houston", 67000),
    (5, "Robert Miller", None, "Philadelphia", 48000),
    (6, "Linda Wilson", "1990-09-12", "Phoenix", None),
    (7, "Michael Moore", "1982-04-08", "San Antonio", 51000),
    (8, "Elizabeth Taylor", "1985-12-25", "San Diego", 44000),
    (9, "William Anderson", "1978-02-17", "Dallas", 39000),
    (10, "Jennifer Thomas", "1995-06-10", None, 61000)
]

# Create DataFrame and save as CSV
columns = ["customer_id", "name", "birthdate", "city", "annual_income"]
customer_df = spark.createDataFrame(data, columns)
customer_df.write.mode("overwrite").csv("/tmp/customer_data", header=True)

print("Sample data created successfully")
```

2. Now, let's build an ETL pipeline:

```python
# EXTRACT: Read data from CSV
raw_df = spark.read.format("csv") \
    .option("header", "true") \
    .option("inferSchema", "true") \
    .load("/tmp/customer_data")

print("Extracted data:")
display(raw_df)

# TRANSFORM: Clean and enhance the data
transformed_df = raw_df \
    .withColumn("birthdate", F.to_date(F.col("birthdate"))) \
    .withColumn("age", F.floor(F.months_between(F.current_date(), F.col("birthdate")) / 12)) \
    .withColumn("city", F.when(F.col("city").isNull(), "Unknown").otherwise(F.col("city"))) \
    .withColumn("annual_income", F.when(F.col("annual_income").isNull(), 0).otherwise(F.col("annual_income"))) \
    .withColumn("income_bracket", 
               F.when(F.col("annual_income") < 40000, "Low")
                .when(F.col("annual_income") < 60000, "Medium")
                .otherwise("High"))

print("Transformed data:")
display(transformed_df)

# LOAD: Save as a Delta table
transformed_df.write.format("delta").mode("overwrite").saveAsTable("customer_data")

print("Data loaded into Delta table 'customer_data'")

# Verify the data
print("Data in Delta table:")
display(spark.table("customer_data"))
```

---

### Advanced Transformations

#### Data Deduplication Techniques

Duplicated data is a common issue in data engineering. Spark provides several methods for handling duplicates:

##### Identifying Duplicates

```python
# Count duplicates
duplicate_counts = df.groupBy("id").count().filter("count > 1")

# SQL equivalent
spark.sql("""
  SELECT id, COUNT(*) as count
  FROM table_name
  GROUP BY id
  HAVING COUNT(*) > 1
""")
```

##### Removing Duplicates

```python
# Remove complete duplicates
deduplicated_df = df.distinct()

# SQL equivalent
spark.sql("SELECT DISTINCT * FROM table_name")

# Remove duplicates based on specific columns
deduplicated_df = df.dropDuplicates(["id", "transaction_date"])

# SQL equivalent
spark.sql("""
  WITH ranked_data AS (
    SELECT *,
      ROW_NUMBER() OVER (PARTITION BY id, transaction_date ORDER BY id) as rn
    FROM table_name
  )
  SELECT * FROM ranked_data WHERE rn = 1
""")
```

#### Data Validation Techniques

Validating data quality is crucial in ETL processes:

##### Primary Key Validation

```python
# Check if id column contains unique values
id_counts = df.groupBy("id").count()
duplicate_ids = id_counts.filter("count > 1")

if duplicate_ids.count() > 0:
    print("Primary key constraint violated")
    display(duplicate_ids)
else:
    print("Primary key constraint satisfied")
```

##### Foreign Key Validation

```python
# Check if all product_ids exist in the products table
product_ids_in_orders = orders_df.select("product_id").distinct()
valid_product_ids = products_df.select("id").distinct()

invalid_product_ids = product_ids_in_orders.join(
    valid_product_ids,
    product_ids_in_orders["product_id"] == valid_product_ids["id"],
    "left_anti"
)

if invalid_product_ids.count() > 0:
    print("Foreign key constraint violated")
    display(invalid_product_ids)
else:
    print("Foreign key constraint satisfied")
```

#### Working with Complex Data Types

##### Handling Timestamps

```python
# Converting string to timestamp
df = df.withColumn("event_time", F.to_timestamp(F.col("event_time_string")))

# Extracting components from timestamps
df = df.withColumn("year", F.year("event_time")) \
       .withColumn("month", F.month("event_time")) \
       .withColumn("day", F.dayofmonth("event_time")) \
       .withColumn("hour", F.hour("event_time"))

# Calculating date differences
df = df.withColumn("days_since_purchase", 
                  F.datediff(F.current_date(), F.col("purchase_date")))
```

##### Working with JSON and Nested Structures

```python
# Parsing JSON string into struct
df = df.withColumn("json_data", F.from_json(F.col("json_string"), schema))

# Accessing nested fields
df = df.withColumn("customer_name", F.col("json_data.customer.name"))

# Exploding arrays into multiple rows
df = df.withColumn("item", F.explode("items"))

# JSON schema definition example
from pyspark.sql.types import StructType, StructField, StringType, ArrayType, IntegerType

schema = StructType([
    StructField("customer", StructType([
        StructField("name", StringType()),
        StructField("email", StringType())
    ])),
    StructField("items", ArrayType(StructType([
        StructField("item_id", StringType()),
        StructField("quantity", IntegerType())
    ])))
])
```

#### SQL User-Defined Functions (UDFs)

SQL UDFs allow for custom logic within SQL queries:

```sql
-- Creating a SQL UDF
CREATE OR REPLACE FUNCTION calculate_tax(amount DOUBLE)
RETURNS DOUBLE
RETURN amount * 0.07;

-- Using the UDF
SELECT item_name, price, calculate_tax(price) as tax_amount
FROM items;
```

#### Control Flow in Spark SQL

The CASE WHEN statement provides conditional logic in Spark SQL:

```sql
-- Using CASE WHEN for conditional logic
SELECT 
  customer_id,
  total_purchase,
  CASE 
    WHEN total_purchase < 100 THEN 'Low Value'
    WHEN total_purchase < 1000 THEN 'Medium Value'
    ELSE 'High Value'
  END as customer_segment
FROM customer_purchases;
```

---

### Hands-on Exercise: Advanced Transformations

Let's work with a more complex scenario involving nested data and deduplication:

```python
# Create sample order data with duplicates and nested structures
from pyspark.sql.types import *
import json

# Sample order data with JSON
order_data = [
    (1, "2023-01-15", '{"customer": {"id": 101, "name": "John Doe"}, "items": [{"id": "A1", "qty": 2}, {"id": "B3", "qty": 1}]}'),
    (2, "2023-01-16", '{"customer": {"id": 102, "name": "Jane Smith"}, "items": [{"id": "C2", "qty": 3}]}'),
    (1, "2023-01-15", '{"customer": {"id": 101, "name": "John Doe"}, "items": [{"id": "A1", "qty": 2}, {"id": "B3", "qty": 1}]}'),  # Duplicate
    (3, "2023-01-17", '{"customer": {"id": 103, "name": "Bob Johnson"}, "items": [{"id": "A1", "qty": 1}, {"id": "D4", "qty": 4}]}'),
    (4, "2023-01-18", '{"customer": {"id": 101, "name": "John Doe"}, "items": [{"id": "E5", "qty": 2}]}')
]

# Define the schema for the JSON data
json_schema = StructType([
    StructField("customer", StructType([
        StructField("id", IntegerType()),
        StructField("name", StringType())
    ])),
    StructField("items", ArrayType(StructType([
        StructField("id", StringType()),
        StructField("qty", IntegerType())
    ])))
])

# Create DataFrame
order_df = spark.createDataFrame(order_data, ["order_id", "order_date", "order_details"])

# Save as table
order_df.write.format("delta").mode("overwrite").saveAsTable("raw_orders")

print("Sample order data created:")
display(spark.table("raw_orders"))

# Now process the data with various transformations
processed_df = spark.table("raw_orders")

# 1. Remove duplicates
deduplicated_df = processed_df.dropDuplicates(["order_id", "order_date", "order_details"])
print(f"Removed {processed_df.count() - deduplicated_df.count()} duplicate orders")

# 2. Parse the JSON data
parsed_df = deduplicated_df.withColumn("order_details_parsed", 
                                    F.from_json(F.col("order_details"), json_schema))

# 3. Extract nested fields
extracted_df = parsed_df \
    .withColumn("customer_id", F.col("order_details_parsed.customer.id")) \
    .withColumn("customer_name", F.col("order_details_parsed.customer.name")) \
    .withColumn("items", F.col("order_details_parsed.items"))

# 4. Convert order_date to date type
date_df = extracted_df \
    .withColumn("order_date", F.to_date(F.col("order_date"))) \
    .withColumn("order_day", F.dayofweek(F.col("order_date"))) \
    .withColumn("order_month", F.month(F.col("order_date")))

print("After parsing JSON and extracting fields:")
display(date_df.select("order_id", "order_date", "customer_id", "customer_name", "items"))

# 5. Explode the items array into separate rows
exploded_df = date_df \
    .withColumn("item", F.explode("items")) \
    .withColumn("item_id", F.col("item.id")) \
    .withColumn("quantity", F.col("item.qty")) \
    .drop("items", "item", "order_details", "order_details_parsed")

print("After exploding items array:")
display(exploded_df)

# 6. Save the processed data
exploded_df.write.format("delta").mode("overwrite").saveAsTable("processed_orders")

print("Data saved to 'processed_orders' table")
```

Let's also demonstrate working with pivots and user-defined functions:

```python
# Create sample sales data
sales_data = [
    ("2023-01", "Electronics", 12500),
    ("2023-01", "Clothing", 8300),
    ("2023-01", "Home Goods", 5600),
    ("2023-02", "Electronics", 14200),
    ("2023-02", "Clothing", 9100),
    ("2023-02", "Home Goods", 6200),
    ("2023-03", "Electronics", 13800),
    ("2023-03", "Clothing", 8900),
    ("2023-03", "Home Goods", 7100)
]

sales_df = spark.createDataFrame(sales_data, ["month", "category", "revenue"])
sales_df.write.format("delta").mode("overwrite").saveAsTable("monthly_sales")

print("Monthly sales data:")
display(spark.table("monthly_sales"))

# Create a SQL UDF for calculating tax
spark.sql("""
CREATE OR REPLACE FUNCTION calculate_tax(amount DOUBLE)
RETURNS DOUBLE
RETURN amount * 0.08;
""")

# Use the UDF in a query
spark.sql("""
SELECT month, category, revenue, calculate_tax(revenue) AS tax
FROM monthly_sales
ORDER BY month, category
""").show()

# Create a pivot table
pivoted_sales = spark.sql("""
SELECT *
FROM monthly_sales
PIVOT (
    SUM(revenue) FOR category IN ('Electronics', 'Clothing', 'Home Goods')
)
ORDER BY month
""")

print("Pivoted sales data:")
display(pivoted_sales)
```

---

### Assessment Quiz

1. When reading a CSV file in Spark, which option is used to treat the first row as column headers?
   - A) `firstRowHeader`
   - B) `header`
   - C) `hasHeader`
   - D) `includeHeader`

2. What is the difference between a temporary view and a global temporary view in Spark?
   - A) Temporary views persist across Spark sessions, global temporary views don't
   - B) Global temporary views are accessible across all sessions in the same Spark application
   - C) Temporary views can only be used in SQL, global temporary views can be used in both SQL and DataFrame API
   - D) There is no difference; they are synonyms

3. Which Spark function can you use to handle duplicate records in a dataset?
   - A) `removeDuplicates()`
   - B) `dropDuplicates()`
   - C) `deduplicate()`
   - D) `distinctRows()`

4. How can you extract the year from a date column in Spark SQL?
   - A) `EXTRACT(YEAR FROM date_column)`
   - B) `year(date_column)`
   - C) `date_column.getYear()`
   - D) `date_part('year', date_column)`

5. Which function would you use to convert a JSON string into a structured column in Spark?
   - A) `parse_json`
   - B) `json_parse`
   - C) `from_json`
   - D) `to_struct`

6. When would you use the `explode` function in Spark?
   - A) To split a string column into multiple parts
   - B) To convert array elements into separate rows
   - C) To expand a DataFrame by duplicating records
   - D) To decompress compressed data

7. What does the following SQL query do?
   ```sql
   WITH ranked_data AS (
     SELECT *, ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY order_date DESC) as rn
     FROM orders
   )
   SELECT * FROM ranked_data WHERE rn = 1
   ```
   - A) Selects all orders
   - B) Selects the most recent order for each customer
   - C) Selects the first order for each customer
   - D) Selects orders with duplicate customer IDs

8. How would you create a SQL UDF to calculate a 5% discount on a price?
   - A) `CREATE FUNCTION discount(price DOUBLE) RETURN price * 0.95`
   - B) `CREATE OR REPLACE FUNCTION discount(price DOUBLE) RETURNS DOUBLE RETURN price * 0.95`
   - C) `CREATE UDF discount(price DOUBLE) AS price * 0.95`
   - D) `DEFINE FUNCTION discount(price DOUBLE) AS price * 0.95`

9. What is the correct way to check if a column contains any null values in Spark?
   - A) `df.filter(df.column.isNull()).count() > 0`
   - B) `df.select(df.column).isNull().any()`
   - C) `df.where("column IS NULL").count() > 0`
   - D) Both A and C are correct

10. Which statement creates a pivot table from a DataFrame in Spark SQL?
    - A) `SELECT * FROM table ROTATE (sum(value) FOR category IN ('A', 'B', 'C'))`
    - B) `SELECT * FROM table PIVOT (sum(value) FOR category IN ('A', 'B', 'C'))`
    - C) `SELECT * FROM table CROSS TAB (sum(value) FOR category IN ('A', 'B', 'C'))`
    - D) `SELECT * FROM table TRANSFORM (sum(value) FOR category IN ('A', 'B', 'C'))`

#### Answers to Assessment Quiz:

1. B) `header`
2. B) Global temporary views are accessible across all sessions in the same Spark application
3. B) `dropDuplicates()`
4. B) `year(date_column)`
5. C) `from_json`
6. B) To convert array elements into separate rows
7. B) Selects the most recent order for each customer
8. B) `CREATE OR REPLACE FUNCTION discount(price DOUBLE) RETURNS DOUBLE RETURN price * 0.95`
9. D) Both A and C are correct
10. B) `SELECT * FROM table PIVOT (sum(value) FOR category IN ('A', 'B', 'C'))`

---

### Key Takeaways

1. Spark provides versatile capabilities for extracting data from various sources, including files and databases.
2. Transformations in Spark can be performed using both the DataFrame API and Spark SQL.
3. Temporary views and CTEs help create modular and readable data transformation pipelines.
4. Data deduplication and validation are essential steps in ensuring data quality.
5. Spark offers powerful functions for handling complex data types, including timestamps and nested structures.
6. User-defined functions extend SQL's capabilities for custom transformations.
7. The PIVOT operation transforms row data into columnar format for reporting.

---

## Incremental Data Processing

### Delta Lake and ACID Transactions

#### Delta Lake Fundamentals

Delta Lake is an open-source storage layer that brings reliability to data lakes. As a key technology in the Databricks Lakehouse platform, Delta Lake provides critical enterprise features for data management.

##### What is Delta Lake?

Delta Lake is a storage layer that sits on top of your existing data lake, providing:

- ACID transactions for reliable data operations
- Schema enforcement and evolution capabilities
- Time travel (data versioning)
- Audit history of all changes
- Unified batch and streaming data processing

##### Delta Lake Architecture

Delta Lake stores data as Parquet files but adds a transaction log that tracks all changes to the table. This architecture consists of:

1. **Data Files**: Parquet-formatted files containing the actual data
2. **Delta Log**: A transaction log (stored in the `_delta_log` directory) that records all operations performed on the table
3. **Checkpoint Files**: Periodic snapshots of the table state for faster access

When a Delta table is queried, the Delta Lake engine consults the transaction log to determine which data files to read, ensuring a consistent view of the data.

#### ACID Transactions in Delta Lake

ACID transactions are a set of properties that guarantee reliability in database operations:

- **Atomicity**: Operations either complete entirely or not at all
- **Consistency**: Transactions bring the database from one valid state to another
- **Isolation**: Concurrent transactions produce the same results as if executed sequentially
- **Durability**: Committed transactions remain saved even during system failures

Delta Lake implements these properties through its transaction log mechanism:

```python
# Example of an atomic operation
# This entire operation either succeeds or fails as a unit
df.write.format("delta").mode("overwrite").save("/path/to/delta-table")
```

##### Benefits of ACID Transactions

1. **Data Consistency**: Ensures data is always in a valid state even during concurrent operations
2. **Failure Recovery**: Maintains data integrity even if operations fail midway
3. **Concurrency Control**: Allows multiple users to access and modify data simultaneously
4. **Reliable Streaming**: Enables exactly-once processing semantics for streaming data

#### Data and Metadata Management

##### Understanding Data vs. Metadata

- **Data**: The actual values stored in your tables (rows and columns)
- **Metadata**: Information about the data, including:
  - Schema definitions
  - Partitioning information
  - Table properties
  - File locations
  - Statistics for query optimization

In Databricks, metadata is stored in the metastore, which can be:
- The Hive metastore (traditional)
- Unity Catalog (enterprise grade with enhanced governance)

##### Managed vs. External Tables

Databricks supports two types of Delta tables:

1. **Managed Tables**:
   - Both data and metadata are managed by Databricks
   - When you drop a managed table, both the data and metadata are deleted
   - The data is stored in the default Databricks storage location

2. **External Tables**:
   - Databricks manages only the metadata
   - The data is stored in a location you specify
   - When you drop an external table, only the metadata is deleted; the data remains intact

```sql
-- Creating a managed table
CREATE TABLE managed_table (id INT, name STRING);

-- Creating an external table
CREATE TABLE external_table (id INT, name STRING)
LOCATION '/path/to/external/storage';
```

To identify if a table is managed or external:

```sql
-- Check if a table is managed or external
DESCRIBE EXTENDED table_name;
```

Look for the `Type` property (managed or external) and the `Location` property.

#### Hands-On Exercise: Delta Lake Operations

Let's build a practical exercise to explore Delta Lake fundamentals:

```python
# Create a sample dataset
data = [(1, "Product A", 10.5, "2023-01-01"),
        (2, "Product B", 20.75, "2023-01-02"),
        (3, "Product C", 15.0, "2023-01-03"),
        (4, "Product D", 8.25, "2023-01-04"),
        (5, "Product E", 12.99, "2023-01-05")]

columns = ["id", "product_name", "price", "created_date"]
df = spark.createDataFrame(data, columns)

# Save as a managed Delta table
df.write.format("delta").mode("overwrite").saveAsTable("products_managed")

# Save as an external Delta table
external_path = "/tmp/delta/products_external"
df.write.format("delta").mode("overwrite").option("path", external_path).saveAsTable("products_external")

print("Created both managed and external Delta tables")

# Examine table information
print("\nManaged Table Information:")
display(spark.sql("DESCRIBE EXTENDED products_managed"))

print("\nExternal Table Information:")
display(spark.sql("DESCRIBE EXTENDED products_external"))

# Inspect Delta log structure
print("\nDelta Log Structure:")
display(dbutils.fs.ls(external_path + "/_delta_log"))

# Make modifications to track history
# Add a new product
new_product = [(6, "Product F", 22.5, "2023-01-06")]
new_df = spark.createDataFrame(new_product, columns)
new_df.write.format("delta").mode("append").saveAsTable("products_managed")

# Update a product price
spark.sql("UPDATE products_managed SET price = 11.99 WHERE id = 1")

# View table history
print("\nTable History:")
display(spark.sql("DESCRIBE HISTORY products_managed"))

# Time travel query
print("\nData as of Version 0:")
display(spark.sql("SELECT * FROM products_managed VERSION AS OF 0"))

print("\nCurrent data (latest version):")
display(spark.sql("SELECT * FROM products_managed"))
```
---

### Delta Lake Operations and Optimizations

#### Table History and Time Travel

Delta Lake's transaction log enables powerful versioning capabilities:

```sql
-- View the history of a Delta table
DESCRIBE HISTORY delta_table;

-- Query a specific version of a table
SELECT * FROM delta_table VERSION AS OF 3;

-- Query a table as of a specific timestamp
SELECT * FROM delta_table TIMESTAMP AS OF '2023-01-15T00:00:00.000Z';

-- Restore a table to a previous version
RESTORE TABLE delta_table TO VERSION AS OF 3;
```

#### Optimizing Delta Tables

Delta Lake provides several operations to optimize table performance:

##### Z-Ordering

Z-ordering is a technique that co-locates related data in the same files, improving query performance by reducing the amount of data that needs to be read:

```sql
-- Z-order by one or more columns
OPTIMIZE delta_table
ZORDER BY (date_column, region_column);
```

Benefits of Z-Ordering:
- Improves filtering and join performance
- Particularly useful for high-cardinality columns frequently used in query predicates
- Makes data skipping more effective

##### VACUUM and Data Retention

The `VACUUM` command permanently removes files no longer needed by the Delta table:

```sql
-- Remove files not needed for versions older than 7 days
VACUUM delta_table RETAIN 7 DAYS;
```

By default, Delta Lake retains 30 days of history. This can be configured through table properties:

```sql
-- Set retention period to 90 days
ALTER TABLE delta_table 
SET TBLPROPERTIES ('delta.logRetentionDuration' = '90 days');
```

##### OPTIMIZE for File Compaction

Small files can degrade query performance. The `OPTIMIZE` command compacts small files into larger ones:

```sql
-- Compact small files without reordering data
OPTIMIZE delta_table;
```

#### Advanced Table Features

##### Generated Columns

Generated columns are automatically calculated from other columns:

```sql
-- Create a table with a generated column
CREATE TABLE sales (
  id INT,
  amount DOUBLE,
  tax DOUBLE GENERATED ALWAYS AS (amount * 0.07)
);
```

##### Table Comments and Properties

Add documentation and configure behavior through comments and properties:

```sql
-- Add a comment to a table
COMMENT ON TABLE sales IS 'Daily sales transactions';

-- Add a comment to a column
COMMENT ON COLUMN sales.amount IS 'Sale amount in USD';

-- Set table properties
ALTER TABLE sales 
SET TBLPROPERTIES (
  'delta.autoOptimize.optimizeWrite' = 'true',
  'delta.autoOptimize.autoCompact' = 'true'
);
```
---

### Incremental Data Loading

#### Overwrite Operations

##### CREATE OR REPLACE TABLE

This operation replaces a table with a new definition:

```sql
-- Create or replace a table
CREATE OR REPLACE TABLE customer_data
AS SELECT * FROM customer_source WHERE region = 'Europe';
```

##### INSERT OVERWRITE

This operation replaces existing data while preserving the table schema and properties:

```sql
-- Overwrite all data in the table
INSERT OVERWRITE TABLE customer_data
SELECT * FROM customer_source WHERE region = 'North America';
```

Differences between these approaches:

- `CREATE OR REPLACE TABLE` recreates the entire table, potentially changing the schema
- `INSERT OVERWRITE` preserves the table structure and only replaces the data

#### MERGE Operations

The `MERGE` statement is a powerful tool for upserting data (insert, update, or delete in a single atomic operation):

```sql
-- Basic MERGE operation
MERGE INTO target_table
USING source_table
ON target_table.id = source_table.id
WHEN MATCHED THEN
  UPDATE SET 
    target_table.column1 = source_table.column1,
    target_table.column2 = source_table.column2
WHEN NOT MATCHED THEN
  INSERT (id, column1, column2)
  VALUES (source_table.id, source_table.column1, source_table.column2);
```

Benefits of MERGE:
- Atomic updates (all-or-nothing)
- Efficient handling of inserts and updates in a single operation
- Support for conditional logic
- Eliminates the need for staging tables

#### COPY INTO

The `COPY INTO` command is a simple, idempotent way to load data incrementally:

```sql
-- Load data incrementally from a directory
COPY INTO target_table
FROM '/path/to/source/files'
FILEFORMAT = CSV
FORMAT_OPTIONS ('header' = 'true', 'inferSchema' = 'true')
COPY_OPTIONS ('mergeSchema' = 'true');
```

Key features:
- Loads only new files not previously ingested
- Tracks loaded files to avoid duplication
- Simpler than MERGE for basic ingestion patterns
- Supports various file formats (CSV, JSON, Parquet, etc.)

#### Delta Live Tables (DLT)

Delta Live Tables provides a declarative framework for building reliable data pipelines:

##### Components of a DLT Pipeline

1. **Target**: The database where tables will be created
2. **Notebook Libraries**: Notebooks containing the transformation logic
3. **Configuration**: Settings for the pipeline execution

##### Pipeline Types

- **Triggered Pipelines**: Run on demand or on a schedule
- **Continuous Pipelines**: Process data as it arrives (near real-time)

##### Auto Loader

Auto Loader simplifies streaming ingestion from file sources:

```python
# Using Auto Loader in Python
spark.readStream.format("cloudFiles")
  .option("cloudFiles.format", "json")
  .option("cloudFiles.schemaLocation", "/path/to/schema")
  .load("/path/to/source/files")
```

Features:
- Efficiently processes new files as they arrive
- Handles schema inference and evolution
- Scales to millions of files without listing directories

##### Data Quality Constraints

DLT supports data quality validation through constraints:

```python
# Table with constraints
@dlt.table(
  comment="Validated customer data",
  table_properties={"quality": "silver"}
)
@dlt.expect_or_drop("valid_id", "id IS NOT NULL")
@dlt.expect_or_fail("valid_email", "email LIKE '%@%.%'")
def validated_customers():
  return spark.table("raw_customers").filter("age > 0")
```

Constraint handling options:
- `@dlt.expect_or_drop`: Drop records that violate the constraint
- `@dlt.expect_or_fail`: Fail the pipeline if any record violates the constraint
- `@dlt.expect`: Track violations without affecting the pipeline

##### Change Data Capture (CDC)

CDC processes data changes from source systems:

```python
# Apply CDC changes
@dlt.table
def customers_target():
  return (
    dlt.apply_changes(
      target = "customers_target",
      source = "customers_raw_stream",
      keys = ["customer_id"],
      sequence_by = "operation_timestamp",
      ignore_null_updates = False,
      apply_as_deletes = "operation = 'DELETE'"
    )
  )
```

Benefits:
- Efficiently processes change data from databases
- Supports insert, update, and delete operations
- Maintains a consistent target state

#### Hands-On Exercise: Incremental Data Processing

Let's implement a comprehensive incremental processing example:

```python
# Set up sample data
from pyspark.sql import functions as F
from datetime import datetime, timedelta

# Create initial customer data
base_customers = [
    (1, "John Doe", "john@example.com", "New York"),
    (2, "Jane Smith", "jane@example.com", "Los Angeles"),
    (3, "Mike Johnson", "mike@example.com", "Chicago"),
    (4, "Lisa Brown", "lisa@example.com", "Houston"),
    (5, "David Wilson", "david@example.com", "Phoenix")
]

# Save as initial table
customers_df = spark.createDataFrame(base_customers, ["id", "name", "email", "city"])
customers_df.write.format("delta").mode("overwrite").saveAsTable("customers")

print("Initial customer data created:")
display(spark.table("customers"))

# Create updates (some new, some modified records)
customer_updates = [
    (3, "Michael Johnson", "michael@example.com", "Chicago"),  # Modified
    (4, "Lisa Brown", "lisa@example.com", "Dallas"),  # Modified
    (6, "Sarah Lee", "sarah@example.com", "Miami"),  # New
    (7, "Robert Chen", "robert@example.com", "Seattle")  # New
]

updates_df = spark.createDataFrame(customer_updates, ["id", "name", "email", "city"])
updates_df.createOrReplaceTempView("customer_updates")

print("Customer updates:")
display(updates_df)

# Approach 1: Using MERGE
spark.sql("""
MERGE INTO customers target
USING customer_updates source
ON target.id = source.id
WHEN MATCHED THEN
  UPDATE SET 
    target.name = source.name,
    target.email = source.email,
    target.city = source.city
WHEN NOT MATCHED THEN
  INSERT (id, name, email, city)
  VALUES (source.id, source.name, source.email, source.city)
""")

print("After MERGE operation:")
display(spark.table("customers"))

# Approach 2: CREATE OR REPLACE TABLE with partitioning
# Create a new dataset with dates for partitioning
customers_with_dates = []
start_date = datetime(2023, 1, 1)

for i in range(1, 8):
    if i <= 5:
        date = (start_date + timedelta(days=i)).strftime("%Y-%m-%d")
        customers_with_dates.append((i, f"Customer {i}", f"customer{i}@example.com", f"City {i}", date))

# Create partitioned table
partitioned_df = spark.createDataFrame(
    customers_with_dates, 
    ["id", "name", "email", "city", "registration_date"]
)

# Save as partitioned table
partitioned_df.write.format("delta") \
    .partitionBy("registration_date") \
    .mode("overwrite") \
    .saveAsTable("customers_partitioned")

print("Partitioned customer table:")
display(spark.table("customers_partitioned"))

# Show partitions
print("Table partitions:")
display(spark.sql("SHOW PARTITIONS customers_partitioned"))

# Create updates for specific partition
partition_updates = [
    (3, "Customer 3 Updated", "customer3new@example.com", "New City 3", "2023-01-03"),
    (8, "Customer 8 New", "customer8@example.com", "City 8", "2023-01-03")
]

partition_updates_df = spark.createDataFrame(
    partition_updates,
    ["id", "name", "email", "city", "registration_date"]
)

# Overwrite specific partition
spark.sql("""
INSERT OVERWRITE TABLE customers_partitioned
PARTITION (registration_date = '2023-01-03')
SELECT id, name, email, city, registration_date
FROM partition_updates_df
""")

print("After partition overwrite:")
display(spark.table("customers_partitioned"))

# Approach 3: COPY INTO for idempotent loads
# Create files to be loaded
incremental_data = [
    (9, "New Customer 9", "customer9@example.com", "Seattle"),
    (10, "New Customer 10", "customer10@example.com", "Portland")
]

incremental_df = spark.createDataFrame(incremental_data, ["id", "name", "email", "city"])
incremental_df.write.format("csv").option("header", "true").mode("overwrite").save("/tmp/incremental_loads/batch1")

# Second batch with some overlap
incremental_data2 = [
    (10, "New Customer 10", "customer10@example.com", "Portland"),  # Duplicate
    (11, "New Customer 11", "customer11@example.com", "Boston")
]

incremental_df2 = spark.createDataFrame(incremental_data2, ["id", "name", "email", "city"])
incremental_df2.write.format("csv").option("header", "true").mode("overwrite").save("/tmp/incremental_loads/batch2")

# Create target table
spark.sql("CREATE TABLE IF NOT EXISTS copy_into_target (id INT, name STRING, email STRING, city STRING)")

# Load data using COPY INTO
spark.sql("""
COPY INTO copy_into_target
FROM '/tmp/incremental_loads'
FILEFORMAT = CSV
FORMAT_OPTIONS ('header' = 'true', 'inferSchema' = 'true')
PATTERN = '*/batch*'
""")

print("After COPY INTO operation:")
display(spark.table("copy_into_target"))

# Run second time to demonstrate idempotency
spark.sql("""
COPY INTO copy_into_target
FROM '/tmp/incremental_loads'
FILEFORMAT = CSV
FORMAT_OPTIONS ('header' = 'true', 'inferSchema' = 'true')
PATTERN = '*/batch*'
""")

print("After second COPY INTO operation (should be idempotent):")
display(spark.table("copy_into_target"))
```

---

### Assessment Quiz

1. Which of the following is NOT a property of ACID transactions in Delta Lake?
   - A) Atomicity
   - B) Concurrency
   - C) Isolation
   - D) Durability

2. What is the key difference between managed and external Delta tables?
   - A) External tables support time travel while managed tables don't
   - B) When a managed table is dropped, both data and metadata are deleted
   - C) External tables cannot be updated with MERGE operations
   - D) Managed tables don't support partitioning

3. Which command would you use to view the history of operations on a Delta table?
   - A) `SHOW HISTORY delta_table`
   - B) `DESCRIBE HISTORY delta_table`
   - C) `SELECT HISTORY FROM delta_table`
   - D) `DISPLAY OPERATIONS delta_table`

4. What is the purpose of Z-ordering in Delta Lake?
   - A) To encrypt sensitive data in Delta tables
   - B) To sort data lexicographically for faster access
   - C) To co-locate related data in the same files for query optimization
   - D) To compress data files for storage efficiency

5. Which operation permanently removes files that are no longer needed by a Delta table?
   - A) `CLEAN`
   - B) `PURGE`
   - C) `VACUUM`
   - D) `REMOVE`

6. What is the difference between `CREATE OR REPLACE TABLE` and `INSERT OVERWRITE`?
   - A) `CREATE OR REPLACE TABLE` can change the schema, `INSERT OVERWRITE` preserves it
   - B) `INSERT OVERWRITE` supports condition-based updates, `CREATE OR REPLACE TABLE` doesn't
   - C) `CREATE OR REPLACE TABLE` is only for managed tables, `INSERT OVERWRITE` works with both
   - D) There is no difference; they are synonyms

7. Which statement is true about the `MERGE` operation in Delta Lake?
   - A) It can only handle inserts, not updates
   - B) It requires creating a staging table first
   - C) It combines insert, update, and delete operations in a single atomic transaction
   - D) It can only be used with external tables

8. What is the advantage of using `COPY INTO` for data loading?
   - A) It automatically partitions data based on content
   - B) It loads only new files not previously ingested
   - C) It transforms data during the loading process
   - D) It's faster than `MERGE` for updating existing records

9. In Delta Live Tables, what does the `@dlt.expect_or_drop` annotation do?
   - A) Drops the entire table if any records violate the constraint
   - B) Drops records that violate the constraint
   - C) Drops the column if it contains invalid values
   - D) Marks records for later review

10. Which component of Delta Live Tables is used for efficiently processing new files as they arrive?
    - A) Change Data Capture
    - B) Auto Loader
    - C) File Tracker
    - D) Stream Processor

#### Answers to Assessment Quiz:

1. B) Concurrency (ACID stands for Atomicity, Consistency, Isolation, Durability)
2. B) When a managed table is dropped, both data and metadata are deleted
3. B) `DESCRIBE HISTORY delta_table`
4. C) To co-locate related data in the same files for query optimization
5. C) `VACUUM`
6. A) `CREATE OR REPLACE TABLE` can change the schema, `INSERT OVERWRITE` preserves it
7. C) It combines insert, update, and delete operations in a single atomic transaction
8. B) It loads only new files not previously ingested
9. B) Drops records that violate the constraint
10. B) Auto Loader

---

### Key Takeaways

1. Delta Lake enhances data lakes with ACID transactions, ensuring data reliability.
2. Understanding the difference between managed and external tables is crucial for proper data management.
3. Time travel capabilities allow for auditing and error recovery.
4. Optimization operations like Z-ordering and VACUUM improve query performance and manage storage.
5. Incremental data loading can be accomplished through multiple patterns (MERGE, COPY INTO, etc.).
6. Delta Live Tables provides a declarative framework for building reliable data pipelines.
7. Change Data Capture enables efficient processing of data changes from source systems.

---


## Production Pipelines & Data Governance

### Production Pipelines

#### Introduction to Databricks Jobs

Databricks Jobs provide a way to orchestrate and schedule your data processing workflows in a production environment. They allow you to automate notebook execution, specify dependencies between tasks, and set up monitoring and alerting.

##### Key Concepts of Databricks Jobs

Jobs in Databricks consist of several components:

1. **Jobs**: The top-level container for workloads.
2. **Tasks**: Individual units of work within a job (e.g., a notebook, JAR file, or Python script).
3. **Runs**: Specific executions of jobs, including all task runs.
4. **Task Runs**: Individual executions of tasks within a job run.

##### Benefits of Using Jobs

- **Automation**: Schedule workloads to run on a specific cadence.
- **Orchestration**: Define complex workflows with dependencies between tasks.
- **Resource Isolation**: Jobs run on dedicated job clusters that terminate after completion.
- **Monitoring**: Track job progress, execution time, and failures.
- **Notifications**: Set up alerts for job failures or completion.
- **Cost Optimization**: Jobs clusters automatically terminate after completion.

#### Multi-Task Workflows

Modern data pipelines often consist of multiple interconnected steps that need to be executed in a specific order. Databricks Jobs support this through multi-task workflows.

##### Creating Task Dependencies

```python
# Pseudocode representation of a multi-task workflow
job = {
    "name": "Sales Processing Pipeline",
    "tasks": [
        {
            "task_key": "extract_data",
            "notebook_task": {
                "notebook_path": "/path/to/extract_notebook"
            },
            "job_cluster_key": "job_cluster"
        },
        {
            "task_key": "transform_data",
            "notebook_task": {
                "notebook_path": "/path/to/transform_notebook"
            },
            "job_cluster_key": "job_cluster",
            "depends_on": [
                {"task_key": "extract_data"}
            ]
        },
        {
            "task_key": "load_data",
            "notebook_task": {
                "notebook_path": "/path/to/load_notebook"
            },
            "job_cluster_key": "job_cluster",
            "depends_on": [
                {"task_key": "transform_data"}
            ]
        }
    ]
}
```

The `depends_on` property specifies that a task should only run after its dependencies have completed successfully.

##### Task Execution Flow

When a multi-task job runs:

1. Tasks with no dependencies start immediately.
2. Tasks with dependencies wait until all dependencies complete successfully.
3. If a task fails, its dependent tasks will not run.
4. The job completes when all tasks either succeed or fail.

#### Job Scheduling with CRON

Databricks jobs can be scheduled to run automatically using CRON expressions.

##### CRON Expression Format

A CRON expression consists of 5-6 fields that define when a job should run:

```
┌────────── minute (0 - 59)
│ ┌──────── hour (0 - 23)
│ │ ┌────── day of month (1 - 31)
│ │ │ ┌──── month (1 - 12)
│ │ │ │ ┌── day of week (0 - 6) (Sunday = 0)
│ │ │ │ │
* * * * *
```

Common CRON patterns:

- `0 0 * * *` - Run at midnight every day
- `0 */6 * * *` - Run every 6 hours
- `0 8 * * 1-5` - Run at 8 AM on weekdays
- `0 0 1 * *` - Run at midnight on the first day of each month

##### Setting Up a Schedule

When creating a job, you can specify a schedule using either a CRON expression or a simpler UI-based approach that generates the CRON expression for you.

#### Job Monitoring and Alerting

Monitoring job execution and setting up alerts for failures are crucial for maintaining reliable data pipelines.

##### Monitoring Job Execution

Databricks provides several ways to monitor jobs:

1. **Jobs UI**: View all jobs, their status, and execution history.
2. **Run Details**: Examine logs, task outputs, and execution time for a specific run.
3. **Metrics**: Track execution time, success rates, and resource utilization.

##### Setting Up Alerts

Databricks supports various notification mechanisms:

1. **Email Notifications**: Send emails on job failure or completion.
2. **Webhook Notifications**: Integrate with external systems like Slack or PagerDuty.
3. **REST API**: Programmatically check job status and take action.

##### Retry Policies

For transient failures, you can set up retry policies:

```json
{
  "task_key": "extract_data",
  "notebook_task": {
    "notebook_path": "/path/to/extract_notebook"
  },
  "retry_on_failure": {
    "max_retries": 3,
    "min_duration_between_retries_seconds": 60
  }
}
```

This configuration will retry the task up to 3 times with a 60-second delay between retries if it fails.

---

### Hands-on Exercise: Creating a Production Pipeline

Let's build a complete production pipeline that performs the following steps:
1. Extracts and processes daily sales data
2. Computes key metrics
3. Updates a reporting dashboard
4. Sends an email notification upon completion

For this exercise, we'll create three notebooks and link them in a job:

#### Notebook 1: Extract and Process Sales Data

```python
# Notebook: extract_sales_data
# This notebook extracts daily sales data and performs initial processing

# Log the start of the process
import datetime
current_time = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
print(f"Starting sales data extraction at {current_time}")

# Create sample sales data (in a real scenario, you would extract from a source)
from pyspark.sql import functions as F
import random
from datetime import datetime, timedelta

# Generate sales data for yesterday
yesterday = (datetime.now() - timedelta(days=1)).strftime("%Y-%m-%d")
products = ["Product A", "Product B", "Product C", "Product D", "Product E"]
regions = ["North", "South", "East", "West", "Central"]

# Generate 100 random sales records
data = []
for i in range(100):
    product = random.choice(products)
    region = random.choice(regions)
    quantity = random.randint(1, 10)
    unit_price = round(random.uniform(10, 100), 2)
    total = round(quantity * unit_price, 2)
    
    data.append((yesterday, product, region, quantity, unit_price, total))

# Create DataFrame
columns = ["date", "product", "region", "quantity", "unit_price", "total_amount"]
sales_df = spark.createDataFrame(data, columns)

# Save as a Delta table, partitioned by date
sales_df.write.format("delta").partitionBy("date").mode("append").saveAsTable("daily_sales")

# Verify the data was written
count = spark.table("daily_sales").filter(F.col("date") == yesterday).count()
print(f"Successfully extracted {count} sales records for {yesterday}")

# Set a notebook parameter to pass to downstream tasks
dbutils.jobs.taskValues.set(key = "sales_date", value = yesterday)
dbutils.jobs.taskValues.set(key = "record_count", value = count)

print("Data extraction complete")
```

#### Notebook 2: Compute Sales Metrics

```python
# Notebook: compute_sales_metrics
# This notebook computes key sales metrics based on the extracted data

# Get the sales date from the upstream task
sales_date = dbutils.jobs.taskValues.get(taskKey = "extract_sales_data", key = "sales_date")
record_count = dbutils.jobs.taskValues.get(taskKey = "extract_sales_data", key = "record_count")

print(f"Computing sales metrics for {sales_date} with {record_count} records")

# Read the daily sales data
daily_sales = spark.table("daily_sales").filter(f"date = '{sales_date}'")

# Compute product-level metrics
product_metrics = daily_sales.groupBy("product").agg(
    F.sum("quantity").alias("total_quantity"),
    F.sum("total_amount").alias("total_revenue"),
    F.avg("unit_price").alias("average_price")
).orderBy(F.col("total_revenue").desc())

# Save product metrics
product_metrics.write.format("delta").mode("overwrite").option("overwriteSchema", "true").saveAsTable("product_metrics_daily")

# Compute region-level metrics
region_metrics = daily_sales.groupBy("region").agg(
    F.countDistinct("product").alias("product_count"),
    F.sum("quantity").alias("total_quantity"),
    F.sum("total_amount").alias("total_revenue")
).orderBy(F.col("total_revenue").desc())

# Save region metrics
region_metrics.write.format("delta").mode("overwrite").option("overwriteSchema", "true").saveAsTable("region_metrics_daily")

# Compute overall metrics for dashboard
overall_metrics = {
    "date": sales_date,
    "total_sales": daily_sales.select(F.sum("total_amount")).first()[0],
    "total_units": daily_sales.select(F.sum("quantity")).first()[0],
    "avg_order_value": daily_sales.select(F.avg("total_amount")).first()[0],
    "top_product": product_metrics.first()["product"],
    "top_region": region_metrics.first()["region"]
}

# Convert to DataFrame and save
metrics_df = spark.createDataFrame([overall_metrics])
metrics_df.write.format("delta").mode("append").saveAsTable("sales_overall_metrics")

# Pass metrics to the next task
dbutils.jobs.taskValues.set(key = "total_sales", value = overall_metrics["total_sales"])
dbutils.jobs.taskValues.set(key = "top_product", value = overall_metrics["top_product"])
dbutils.jobs.taskValues.set(key = "top_region", value = overall_metrics["top_region"])

print("Metrics computation complete")
```

#### Notebook 3: Update Dashboard and Notify

```python
# Notebook: update_dashboard
# This notebook updates a dashboard and sends a notification

# Get values from upstream tasks
sales_date = dbutils.jobs.taskValues.get(taskKey = "extract_sales_data", key = "sales_date")
total_sales = dbutils.jobs.taskValues.get(taskKey = "compute_sales_metrics", key = "total_sales")
top_product = dbutils.jobs.taskValues.get(taskKey = "compute_sales_metrics", key = "top_product")
top_region = dbutils.jobs.taskValues.get(taskKey = "compute_sales_metrics", key = "top_region")

print(f"Updating dashboard for {sales_date}")
print(f"Total sales: ${total_sales:.2f}")
print(f"Top product: {top_product}")
print(f"Top region: {top_region}")

# In a real scenario, you would use the Databricks API to refresh a dashboard
# or update an external BI tool

# Create a summary for notification
summary = f"""
Sales Report for {sales_date}
---------------------------
Total Sales: ${float(total_sales):.2f}
Top Product: {top_product}
Top Region: {top_region}

The complete report is available in the Databricks dashboard.
"""

# In a real scenario, you would send an email notification
# For this exercise, we'll just print the notification
print("Notification would be sent with the following content:")
print(summary)

print("Dashboard update and notification complete")
```

#### Creating a Multi-Task Job

To set up this workflow as a job:

1. Navigate to the Workflows section in Databricks
2. Click "Create Job"
3. Set up the first task:
   - Task name: extract_sales_data
   - Type: Notebook
   - Path: /path/to/extract_sales_data
   - Cluster: New job cluster (select appropriate configuration)
4. Add the second task:
   - Task name: compute_sales_metrics
   - Type: Notebook
   - Path: /path/to/compute_sales_metrics
   - Cluster: Same as task 1
   - Dependencies: extract_sales_data
5. Add the third task:
   - Task name: update_dashboard
   - Type: Notebook
   - Path: /path/to/update_dashboard
   - Cluster: Same as task 1
   - Dependencies: compute_sales_metrics
6. Set up a schedule:
   - Frequency: Daily
   - Start time: 01:00 AM
7. Configure notifications:
   - On failure: Email to team members
8. Save the job

This creates a complete ETL pipeline that runs daily, processes sales data, and updates dashboards with the results.

---

### Data Governance

#### Introduction to Data Governance

Data governance encompasses the policies, procedures, and standards that ensure data is managed as a valuable organizational asset. It focuses on data availability, usability, integrity, and security.

##### Four Areas of Data Governance

1. **Data Discovery**: Finding and understanding available data assets
2. **Access Control**: Managing who can access what data
3. **Audit and Compliance**: Tracking data usage and ensuring regulatory compliance
4. **Data Quality**: Ensuring data accuracy, completeness, and reliability

#### Unity Catalog Architecture

Unity Catalog is Databricks' solution for unified data governance across clouds and regions. It provides a centralized way to manage access to data, ML models, and analytics objects.

##### Metastores vs. Catalogs

**Metastore**:
- The top-level container in Unity Catalog
- Typically, one metastore per organization
- Contains catalogs, schemas (databases), and securable objects
- Linked to one or more Databricks workspaces

**Catalog**:
- A collection of schemas (databases)
- Used to organize data by business unit or project
- Examples: marketing_catalog, finance_catalog, hr_catalog

##### Three-Level Namespace

Unity Catalog uses a three-level namespace to address objects:
```
catalog.schema.object
```

For example:
```sql
-- Querying a table using the three-level namespace
SELECT * FROM marketing.customer_data.transactions;
```

Where:
- `marketing` is the catalog
- `customer_data` is the schema (database)
- `transactions` is the table

#### Security Models and Access Control

Unity Catalog implements fine-grained access control to data and analytical assets.

##### Securables in Unity Catalog

Securables are objects to which permissions can be granted:

1. **Metastore**: The top-level container
2. **Catalog**: Collection of schemas
3. **Schema**: Collection of tables and views
4. **Table/View**: Data objects
5. **Function**: User-defined functions
6. **Volume**: Locations for files
7. **Model**: Machine learning models

##### Access Control Principles

Unity Catalog follows these principles:

1. **Inheritance**: Permissions flow from higher-level objects to lower-level ones
2. **Least Privilege**: Users get only the permissions they need
3. **Separation of Duties**: Different roles handle different responsibilities

##### Common Permissions

```sql
-- Grant permission to read data
GRANT SELECT ON TABLE catalog.schema.table TO user@example.com;

-- Grant permission to modify data
GRANT MODIFY ON TABLE catalog.schema.table TO group sales_analysts;

-- Grant permission to manage a schema
GRANT USAGE, CREATE ON SCHEMA catalog.schema TO group data_engineers;

-- Grant permission to access all tables in a schema
GRANT SELECT ON SCHEMA catalog.schema TO group analysts;
```

#### Service Principals

A service principal is an identity used by automated processes, applications, or services, rather than people.

##### Benefits of Service Principals

- No password expiration or rotation issues
- Clear separation between human and non-human access
- Easier to audit automated processes
- Can be restricted to specific operations

##### Creating and Using Service Principals

Service principals are created in the Databricks account console and can be assigned permissions like human users:

```sql
-- Grant a service principal access to a table
GRANT SELECT ON TABLE catalog.schema.table TO `service-principal://etl-process`;

-- Use service principal for a connection
CREATE CONNECTION my_connection
TYPE MYSQL
PROPERTIES (
  host = 'myhost.example.com',
  port = '3306',
  user = 'myuser',
  password = 'supersecret'
)
WITH USER SERVICE PRINCIPAL `service-principal://etl-process`;
```

#### Cluster Security Modes

Unity Catalog works with specific cluster security modes:

1. **Unity Catalog-enabled Clusters**: 
   - Support the three-level namespace
   - Enforce access controls defined in Unity Catalog
   - Required for accessing data governed by Unity Catalog

2. **User Isolation Mode**:
   - Each user's code runs as their own user identity
   - Users cannot access each other's data or resources
   - Increased security for multi-tenant use cases

#### Best Practices for Data Governance

1. **Colocate Metastores with Workspaces**:
   - Assign each workspace to a specific metastore
   - Reduces network latency and improves performance

2. **Use Service Principals for Connections**:
   - Avoid hardcoding credentials in notebooks
   - Better security and auditability

3. **Segregate Business Units Across Catalogs**:
   - Create separate catalogs for different departments
   - Simplifies access control and improves organization

4. **Implement Row-Level Security When Needed**:
   - For highly sensitive data that requires filtering based on user
   - Can be implemented using dynamic views

---

### Hands-on Exercise: Implementing Data Governance

Let's implement a comprehensive data governance structure for a fictional organization:

```python
# This is a demonstration of Unity Catalog concepts
# Note: Some commands require appropriate permissions to execute

# 1. Create a catalog structure for different departments
spark.sql("CREATE CATALOG IF NOT EXISTS marketing")
spark.sql("CREATE CATALOG IF NOT EXISTS finance")
spark.sql("CREATE CATALOG IF NOT EXISTS hr")

# 2. Create schemas within each catalog
spark.sql("CREATE SCHEMA IF NOT EXISTS marketing.customer_data")
spark.sql("CREATE SCHEMA IF NOT EXISTS marketing.campaign_analytics")
spark.sql("CREATE SCHEMA IF NOT EXISTS finance.transactions")
spark.sql("CREATE SCHEMA IF NOT EXISTS finance.reporting")
spark.sql("CREATE SCHEMA IF NOT EXISTS hr.employee_records")

# 3. Create sample tables with different security requirements
# Marketing customer data
spark.sql("""
CREATE TABLE IF NOT EXISTS marketing.customer_data.profiles (
  customer_id INT,
  name STRING,
  email STRING,
  signup_date DATE,
  last_purchase_date DATE,
  total_spend DOUBLE
)
COMMENT 'Customer profile information'
""")

# Finance transaction data (sensitive)
spark.sql("""
CREATE TABLE IF NOT EXISTS finance.transactions.orders (
  order_id INT,
  customer_id INT,
  order_date DATE,
  amount DOUBLE,
  payment_method STRING,
  status STRING
)
COMMENT 'Financial transaction records - Sensitive data'
""")

# HR employee data (highly sensitive)
spark.sql("""
CREATE TABLE IF NOT EXISTS hr.employee_records.employees (
  employee_id INT,
  name STRING,
  hire_date DATE,
  department STRING,
  salary DOUBLE,
  manager_id INT
)
COMMENT 'Employee records - Highly sensitive data'
""")

# 4. Insert some sample data
spark.sql("""
INSERT INTO marketing.customer_data.profiles VALUES
  (1, 'John Doe', 'john@example.com', '2022-01-15', '2023-02-20', 1250.50),
  (2, 'Jane Smith', 'jane@example.com', '2022-03-10', '2023-03-05', 876.25),
  (3, 'Bob Johnson', 'bob@example.com', '2022-05-22', '2023-01-30', 543.75)
""")

spark.sql("""
INSERT INTO finance.transactions.orders VALUES
  (101, 1, '2023-02-20', 250.50, 'CREDIT_CARD', 'COMPLETED'),
  (102, 2, '2023-03-05', 876.25, 'PAYPAL', 'COMPLETED'),
  (103, 3, '2023-01-30', 543.75, 'BANK_TRANSFER', 'COMPLETED'),
  (104, 1, '2023-04-10', 125.00, 'CREDIT_CARD', 'PENDING')
""")

spark.sql("""
INSERT INTO hr.employee_records.employees VALUES
  (1001, 'Sarah Wilson', '2020-05-10', 'Marketing', 85000.00, 1005),
  (1002, 'Mark Davis', '2021-02-15', 'Finance', 92000.00, 1006),
  (1003, 'Lisa Brown', '2019-11-20', 'HR', 78000.00, 1007)
""")

# 5. Create user groups (in real scenario, these would be created in account console)
# For demonstration purposes only
print("In a real deployment, you would create these groups in the account console:")
print("- marketing_team")
print("- finance_team")
print("- hr_team")
print("- data_analysts")
print("- data_engineers")
print("- executives")

# 6. Set up access control permissions
# Marketing team access
print("""
-- Grant marketing team access
GRANT USAGE ON CATALOG marketing TO GROUP marketing_team;
GRANT SELECT ON SCHEMA marketing.customer_data TO GROUP marketing_team;
GRANT SELECT, MODIFY ON SCHEMA marketing.campaign_analytics TO GROUP marketing_team;
""")

# Finance team access
print("""
-- Grant finance team access
GRANT USAGE ON CATALOG finance TO GROUP finance_team;
GRANT SELECT, MODIFY ON SCHEMA finance.transactions TO GROUP finance_team;
GRANT SELECT, MODIFY ON SCHEMA finance.reporting TO GROUP finance_team;
""")

# HR team access
print("""
-- Grant HR team access
GRANT USAGE ON CATALOG hr TO GROUP hr_team;
GRANT SELECT, MODIFY ON SCHEMA hr.employee_records TO GROUP hr_team;
""")

# Data analysts - limited access across departments
print("""
-- Grant data analysts limited access
GRANT USAGE ON CATALOG marketing TO GROUP data_analysts;
GRANT USAGE ON CATALOG finance TO GROUP data_analysts;
GRANT SELECT ON SCHEMA marketing.customer_data TO GROUP data_analysts;
GRANT SELECT ON TABLE finance.reporting.financial_metrics TO GROUP data_analysts;
-- Note: Explicitly deny access to sensitive HR data
DENY SELECT ON CATALOG hr TO GROUP data_analysts;
""")

# Data engineers - broader access
print("""
-- Grant data engineers broader access
GRANT USAGE ON CATALOG marketing, finance TO GROUP data_engineers;
GRANT SELECT, MODIFY ON SCHEMA marketing.customer_data TO GROUP data_engineers;
GRANT SELECT, MODIFY ON SCHEMA finance.reporting TO GROUP data_engineers;
GRANT SELECT ON SCHEMA finance.transactions TO GROUP data_engineers;
-- Limited HR access
GRANT USAGE ON CATALOG hr TO GROUP data_engineers;
GRANT SELECT ON SCHEMA hr.employee_records TO GROUP data_engineers;
""")

# Executives - read-only access to specific dashboards and reports
print("""
-- Grant executives read-only access
GRANT USAGE ON CATALOG marketing, finance, hr TO GROUP executives;
GRANT SELECT ON TABLE marketing.campaign_analytics.campaign_performance TO GROUP executives;
GRANT SELECT ON TABLE finance.reporting.financial_metrics TO GROUP executives;
GRANT SELECT ON TABLE hr.employee_records.headcount_summary TO GROUP executives;
""")

# 7. Create a service principal for automated ETL processes
print("""
-- In a real scenario, create a service principal in the account console
-- service-principal://etl-process

-- Grant appropriate permissions
GRANT USAGE ON CATALOG marketing, finance, hr TO `service-principal://etl-process`;
GRANT SELECT, MODIFY ON SCHEMA marketing.customer_data TO `service-principal://etl-process`;
GRANT SELECT, MODIFY ON SCHEMA finance.transactions TO `service-principal://etl-process`;
GRANT SELECT, MODIFY ON SCHEMA hr.employee_records TO `service-principal://etl-process`;
""")

# 8. Demonstrate querying with the three-level namespace
# Query marketing data
display(spark.sql("SELECT * FROM marketing.customer_data.profiles"))

# Query finance data
display(spark.sql("SELECT * FROM finance.transactions.orders"))

# Query HR data
display(spark.sql("SELECT * FROM hr.employee_records.employees"))

# 9. Create a row-level security policy on sensitive data
# This is a simplified example of how you might implement RLS
print("""
-- Create a view with row-level security for salary data
CREATE OR REPLACE VIEW hr.employee_records.employee_details AS
SELECT
  employee_id,
  name,
  hire_date,
  department,
  -- Only show salary to HR team and the employee's manager
  CASE 
    WHEN is_member('hr_team') OR current_user() IN (
      SELECT DISTINCT manager_email 
      FROM hr.employee_records.manager_directory 
      WHERE employee_id = e.employee_id
    )
    THEN salary
    ELSE NULL
  END as salary,
  manager_id
FROM hr.employee_records.employees e
""")
```

---

### Assessment Quiz

1. What is the primary benefit of using Jobs in Databricks for production workflows?
   - A) They provide access to more powerful compute resources
   - B) They can integrate with version control systems
   - C) They enable automation, scheduling, and orchestration of workflows
   - D) They bypass Unity Catalog security restrictions

2. In a multi-task workflow, what happens if a task with dependencies fails?
   - A) All dependent tasks will still run
   - B) All dependent tasks will not run
   - C) The entire job is immediately terminated
   - D) The job pauses and waits for manual intervention

3. Which CRON expression would schedule a job to run at 2:30 PM every weekday?
   - A) `30 14 * * 1-5`
   - B) `30 2 * * 1-5`
   - C) `14 30 * * 1-5`
   - D) `30 2 * * 0-4`

4. How can a task pass values to downstream tasks in a Databricks job?
   - A) By writing to a shared Delta table
   - B) Using the `dbutils.jobs.taskValues` API
   - C) Through environment variables
   - D) By updating job parameters

5. What is the purpose of setting up a retry policy for a task?
   - A) To automatically restart the entire job if any task fails
   - B) To attempt the task again if it fails due to transient issues
   - C) To skip failing tasks and continue with the rest of the job
   - D) To resubmit the job with different parameters

6. What is the correct representation of the three-level namespace in Unity Catalog?
   - A) workspace.catalog.table
   - B) catalog.schema.table
   - C) workspace.database.table
   - D) metastore.catalog.table

7. What is the primary difference between a metastore and a catalog in Unity Catalog?
   - A) A metastore contains catalogs, while a catalog contains schemas
   - B) A metastore is cloud-specific, while catalogs work across clouds
   - C) A metastore is for structured data, while catalogs are for unstructured data
   - D) A metastore is read-only, while catalogs can be modified

8. When should you use a service principal instead of a user account?
   - A) For interactive data exploration
   - B) For automated processes and scheduled jobs
   - C) For administrative tasks in the account console
   - D) For query development in Databricks SQL

9. Which cluster security mode is required to use Unity Catalog?
   - A) Single user mode
   - B) Standard mode
   - C) High concurrency mode
   - D) Unity Catalog-enabled mode

10. What is a best practice for organizing data across catalogs in Unity Catalog?
    - A) Put all data in a single catalog for simplicity
    - B) Segregate data by business unit across different catalogs
    - C) Create a new catalog for each table
    - D) Use only the default catalog

#### Answers to Assessment Quiz:

1. C) They enable automation, scheduling, and orchestration of workflows
2. B) All dependent tasks will not run
3. A) `30 14 * * 1-5`
4. B) Using the `dbutils.jobs.taskValues` API
5. B) To attempt the task again if it fails due to transient issues
6. B) catalog.schema.table
7. A) A metastore contains catalogs, while a catalog contains schemas
8. B) For automated processes and scheduled jobs
9. D) Unity Catalog-enabled mode
10. B) Segregate data by business unit across different catalogs

### Key Takeaways

1. Databricks Jobs provide a robust framework for automating, scheduling, and orchestrating data workflows in production environments.

2. Multi-task workflows with dependencies enable complex data pipelines with clearly defined execution sequences.

3. CRON expressions allow flexible scheduling of jobs based on time, day, month, and other parameters.

4. Monitoring, alerting, and retry policies are essential components of production pipelines to ensure reliability.

5. Unity Catalog provides centralized data governance across cloud environments using a three-level namespace (catalog.schema.object).

6. Service principals should be used for automated processes rather than user accounts, improving security and auditability.

7. Access control should follow the principle of least privilege, granting users only the permissions they need to perform their roles.

8. Organizing data by business unit across different catalogs simplifies access control and improves manageability.

---

