---
id: certifications/databricks/machine-learning-professional
title: Databricks Machine Learning Professional Certification
sidebar_label: Databricks Machine Learning Professional Certification
---

<div style="text-align: right;">
    <a href="https://kranthib.github.io/tech-pulse/" style="display: inline-block; padding: 6px 14px; background-color: #2054a6; color: white; text-decoration: none; border-radius: 3px; font-size: 14px; font-weight: 500; transition: background-color 0.3s;">Back to Home →</a>
</div>

# Databricks Machine Learning Professional Certification

Table of contents
=================

<!--ts-->
   * [Preparation Plan](#preparation-plan)
        * [Experimentation & Data Management](#experimentation--data-management)
   * [Knowledge Base](#knowledge-base)
        * [Experimentation & Data Management](#experimentation--data-management-1)
            * [1. Delta Lake Fundamentals](#1-delta-lake-fundamentals)
            * [2. Feature Store Concepts](#2-feature-store-concepts)
            * [3. MLflow Experiment Tracking](#3-mlflow-experiment-tracking)
            * [Exercise 1: Delta Lake Operations](#exercise-1-delta-lake-operations)
            * [Exercise 2: Feature Store Operations](#exercise-2-feature-store-operations)
            * [Quiz: Experimentation & Data Management](#quiz-experimentation--data-management)
            * [Key Takeaways](#key-takeaways)
<!--te-->

# Preparation Plan

## Experimentation & Data Management

- 1. Delta Lake Fundamentals
- 2. Feature Store Concepts
- 3. MLflow Experiment Tracking
- Exercise 1: Delta Lake Operations
- Exercise 2: Feature Store Operations
- Quiz: Experimentation & Data Management
- Key Takeaways

---

# Knowledge Base

## Experimentation & Data Management

### 1. Delta Lake Fundamentals

Delta Lake is a storage layer that brings reliability to data lakes. As an ML engineer, you need to understand its capabilities for managing ML data.

**Key Concepts:**
- **ACID Transactions**: Delta Lake provides atomicity, consistency, isolation, and durability
- **Table History**: Ability to access and restore previous versions of data
- **Schema Enforcement**: Prevents data corruption by enforcing schema on write
- **Time Travel**: Query previous versions of your data using timestamps or version numbers

**Essential Operations:**
- Reading and writing Delta tables
- Accessing table history
- Version restoration
- Delta optimizations (Z-ordering, vacuuming)

---

### 2. Feature Store Concepts

The Databricks Feature Store is a centralized repository for managing and sharing ML features.

**Key Concepts:**
- **Feature Tables**: Collections of features stored with metadata
- **Online vs. Offline Store**: Offline for training, online for low-latency serving
- **Feature Sharing**: Reuse features across teams and models
- **Feature Lineage**: Track where features are used in models

**Essential Operations:**
- Creating feature tables
- Writing and reading from feature tables
- Using feature tables in ML workflows
- Managing feature metadata

---

### 3. MLflow Experiment Tracking

MLflow provides tools for experiment tracking, reproducibility, and model management.

**Key Concepts:**
- **Runs**: Individual executions of ML code
- **Experiments**: Collections of runs
- **Artifacts**: Files associated with runs (models, plots, data)
- **Parameters & Metrics**: Track and compare model configurations and performance

**Essential Operations:**
- Manual logging of parameters, metrics, and models
- Accessing experiment data programmatically
- Advanced tracking with model signatures and input examples
- Nested runs for complex workflows

---

### Exercise 1: Delta Lake Operations

```python
# 1. Create a Delta table
data = spark.range(0, 1000).withColumn("square", col("id") * col("id"))
data.write.format("delta").save("/path/to/delta-table")

# 2. Read from Delta table
df = spark.read.format("delta").load("/path/to/delta-table")

# 3. Update Delta table (append new data)
new_data = spark.range(1000, 2000).withColumn("square", col("id") * col("id"))
new_data.write.format("delta").mode("append").save("/path/to/delta-table")

# 4. View table history
from delta.tables import DeltaTable
delta_table = DeltaTable.forPath(spark, "/path/to/delta-table")
history = delta_table.history()
display(history)

# 5. Time travel (load previous version)
previous_df = spark.read.format("delta").option("versionAsOf", 0).load("/path/to/delta-table")

# 6. Optimize table (Z-ordering)
spark.sql("OPTIMIZE delta.`/path/to/delta-table` ZORDER BY (id)")
```

---

### Exercise 2: Feature Store Operations

```python
# 1. Initialize Feature Store client
from databricks.feature_store import FeatureStoreClient
fs = FeatureStoreClient()

# 2. Create a feature table
from databricks.feature_store import feature_table
features_df = spark.read.format("delta").load("/path/to/data")

fs.create_table(
    name="customer_features",
    primary_keys=["customer_id"],
    df=features_df,
    description="Customer features for churn prediction"
)

# 3. Write to an existing feature table
fs.write_table(
    name="customer_features",
    df=updated_features_df,
    mode="merge"  # Supports "overwrite" and "merge"
)

# 4. Read from a feature table
features = fs.read_table(
    name="customer_features"
)

# 5. Use features in model training
from databricks.feature_store import FeatureLookup

feature_lookups = [
    FeatureLookup(
        table_name="customer_features",
        feature_names=["feature1", "feature2", "feature3"],
        lookup_key="customer_id"
    )
]

training_data = fs.create_training_set(
    df=training_labels_df,
    feature_lookups=feature_lookups,
    label="churn"
)

# Get the training DataFrame
training_df = training_data.load_df()
```

### Exercise 3: MLflow Experiment Tracking

```python
# 1. Basic MLflow tracking
import mlflow
import mlflow.sklearn
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score

# Start a run
with mlflow.start_run(run_name="rf-classifier") as run:
    # Log parameters
    mlflow.log_param("n_estimators", 100)
    mlflow.log_param("max_depth", 5)
    
    # Train model
    model = RandomForestClassifier(n_estimators=100, max_depth=5)
    model.fit(X_train, y_train)
    
    # Log metrics
    y_pred = model.predict(X_test)
    accuracy = accuracy_score(y_test, y_pred)
    mlflow.log_metric("accuracy", accuracy)
    
    # Log model
    mlflow.sklearn.log_model(model, "model")
    
    # Get run ID for later reference
    run_id = run.info.run_id

# 2. Advanced MLflow tracking with signatures and input examples
import pandas as pd
from mlflow.models.signature import infer_signature

# Create an input example
input_example = X_train.iloc[0:5]

# Infer the model signature
signature = infer_signature(X_train, y_pred)

# Log model with signature and input example
with mlflow.start_run(run_name="rf-with-signature") as run:
    mlflow.sklearn.log_model(
        model, 
        "model", 
        signature=signature,
        input_example=input_example
    )

# 3. Working with nested runs
with mlflow.start_run(run_name="parent-run") as parent_run:
    mlflow.log_param("parent_param", "parent_value")
    
    # Create child runs for different model variations
    for n_estimators in [50, 100, 150]:
        with mlflow.start_run(run_name=f"child-run-{n_estimators}", nested=True) as child_run:
            mlflow.log_param("n_estimators", n_estimators)
            
            # Train and log model details
            model = RandomForestClassifier(n_estimators=n_estimators)
            model.fit(X_train, y_train)
            
            accuracy = accuracy_score(y_test, model.predict(X_test))
            mlflow.log_metric("accuracy", accuracy)
            
            mlflow.sklearn.log_model(model, "model")
```

---

### Quiz: Experimentation & Data Management

1. **What Delta Lake operation would you use to eliminate small files and optimize performance?**
   A) VACUUM
   B) OPTIMIZE
   C) COMPACT
   D) CLEAN

2. **In the Feature Store, what mode should you use when writing updates to an existing feature table for specific keys?**
   A) "overwrite"
   B) "append"
   C) "merge"
   D) "update"

3. **How would you access a Delta table's version from 3 days ago?**
   A) Using option("versionAsOf", X)
   B) Using option("timestampAsOf", timestamp)
   C) Using timeTravel(days=3)
   D) Using history().filter(days=3)

4. **When tracking experiments with MLflow, what does setting nested=True allow you to do?**
   A) Create hierarchical runs for different model configurations
   B) Nest models inside each other
   C) Create hierarchical storage of artifacts
   D) Track nested parameters in dictionaries

5. **Which of the following is NOT a benefit of using the Databricks Feature Store?**
   A) Feature sharing across teams
   B) Automatic feature selection
   C) Feature discovery
   D) Point-in-time lookups

6. **What information is provided by a model signature in MLflow?**
   A) The author of the model
   B) The input and output schema of the model
   C) Digital signature verifying model authenticity
   D) The model's architecture details

7. **Which MLflow tracking function would you use to save metadata about a trained model?**
   A) log_artifact()
   B) log_metric()
   C) log_param()
   D) log_tags()

8. **What operation can you perform to go back to a previous version of a Delta table?**
   A) table.rollback(version=N)
   B) RESTORE TABLE to version N
   C) Read with option("versionAsOf", N) and rewrite
   D) History and select previous version

9. **When using the FeatureStoreClient to create a training set, what does the FeatureLookup parameter do?**
   A) Searches for the best features automatically
   B) Specifies which features to retrieve and how to join them
   C) Looks up feature importance scores
   D) Creates a lookup table for the features

10. **How can you programmatically retrieve the metrics from a previous MLflow run?**
    A) mlflow.get_run(run_id).data.metrics
    B) mlflow.search_runs(experiment_id)
    C) mlflow.get_metrics(run_id)
    D) mlflow.runs.get_metrics(run_id)

#### Quiz Answers

1. **What Delta Lake operation would you use to eliminate small files and optimize performance?**
   **Answer: B) OPTIMIZE**
   
   Explanation: The OPTIMIZE command rewrites small files into larger ones to improve read performance. VACUUM removes old file versions but doesn't consolidate small files. COMPACT isn't a standard Delta operation, and CLEAN doesn't exist in Delta Lake.

2. **In the Feature Store, what mode should you use when writing updates to an existing feature table for specific keys?**
   **Answer: C) "merge"**
   
   Explanation: The "merge" mode updates existing records based on primary keys and inserts new ones. "Overwrite" would replace the entire table, "append" would add duplicate records, and "update" isn't a standard mode in Feature Store.

3. **How would you access a Delta table's version from 3 days ago?**
   **Answer: B) Using option("timestampAsOf", timestamp)**
   
   Explanation: To access a version from a specific time point, you use the "timestampAsOf" option with a timestamp value. "versionAsOf" is used for specific version numbers, not time periods. The other options don't exist in Delta Lake.

4. **When tracking experiments with MLflow, what does setting nested=True allow you to do?**
   **Answer: A) Create hierarchical runs for different model configurations**
   
   Explanation: The nested=True parameter allows you to create child runs within a parent run, which is useful for organizing related experiments (like testing different hyperparameters of the same model type).

5. **Which of the following is NOT a benefit of using the Databricks Feature Store?**
   **Answer: B) Automatic feature selection**
   
   Explanation: Feature Store doesn't automatically select optimal features for your models. It does provide feature sharing, discovery (finding features in the organization), and point-in-time lookups (accessing feature values as they were at a specific time).

6. **What information is provided by a model signature in MLflow?**
   **Answer: B) The input and output schema of the model**
   
   Explanation: A model signature defines the expected data types and shapes for model inputs and outputs, enabling validation when the model is used for inference.

7. **Which MLflow tracking function would you use to save metadata about a trained model?**
   **Answer: C) log_param()**
   
   Explanation: log_param() saves named parameters about your model (like hyperparameters). log_metric() is for performance metrics, log_artifact() is for files, and log_tags() isn't a standard MLflow function.

8. **What operation can you perform to go back to a previous version of a Delta table?**
   **Answer: C) Read with option("versionAsOf", N) and rewrite**
   
   Explanation: Delta Lake doesn't have a direct rollback command. To restore a previous version, you need to read the table at that version using "versionAsOf" and then write it back to replace the current version.

9. **When using the FeatureStoreClient to create a training set, what does the FeatureLookup parameter do?**
   **Answer: B) Specifies which features to retrieve and how to join them**
   
   Explanation: FeatureLookup specifies which features to retrieve from which feature tables and how to join them with the training dataset based on lookup keys.

10. **How can you programmatically retrieve the metrics from a previous MLflow run?**
    **Answer: A) mlflow.get_run(run_id).data.metrics**
    
    Explanation: You can get a run's details with mlflow.get_run() and then access its metrics via the .data.metrics attribute. This returns a dictionary of all logged metrics from that run.

#### Score Assessment

- **9-10 correct**: Excellent! You have a strong grasp of the fundamentals.
- **7-8 correct**: Good understanding, but review the topics you missed.
- **5-6 correct**: You're on the right track, but need more study in several areas.
- **Below 5 correct**: More intensive review needed on the Day 1 topics.

#### Areas to Focus On

Here are the concepts to review:

- **Delta Lake operations**: Review OPTIMIZE and VACUUM commands and their purposes
- **Feature Store operations**: Understand the different write modes (merge, overwrite, append)
- **Time travel in Delta**: Practice using both version-based and timestamp-based time travel
- **MLflow nested runs**: Implement example workflows with parent/child runs
- **MLflow model signatures**: Practice creating and using model signatures

---

### Key Takeaways

1. Delta Lake provides ACID transactions and time travel capabilities
2. Feature Store centralizes feature engineering and sharing
3. MLflow helps track experiments and model artifacts

---
