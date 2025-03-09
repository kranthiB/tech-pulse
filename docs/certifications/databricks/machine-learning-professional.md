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
        * [Model Lifecycle Management](#model-lifecycle-management)
   * [Knowledge Base](#knowledge-base)
        * [Experimentation & Data Management](#experimentation--data-management-1)
            * [1. Delta Lake Fundamentals](#1-delta-lake-fundamentals)
            * [2. Feature Store Concepts](#2-feature-store-concepts)
            * [3. MLflow Experiment Tracking](#3-mlflow-experiment-tracking)
            * [Exercise 1: Delta Lake Operations](#exercise-1-delta-lake-operations)
            * [Exercise 2: Feature Store Operations](#exercise-2-feature-store-operations)
            * [Exercise 3: MLflow Experiment Tracking](#exercise-3-mlflow-experiment-tracking)
            * [Quiz: Experimentation & Data Management](#quiz-experimentation--data-management)
            * [Key Takeaways](#key-takeaways)
        * [Model Lifecycle Management](#model-lifecycle-management-1)
            * [1. MLflow Flavors and Custom Models](#1-mlflow-flavors-and-custom-models)
            * [2. Model Registry Fundamentals](#2-model-registry-fundamentals)
            * [3. Model Lifecycle Automation](#3-model-lifecycle-automation)
            * [Exercise 1: MLflow Flavors and Custom Models](#exercise-1-mlflow-flavors-and-custom-models)
            * [Exercise 2: Model Registry Operations](#exercise-2-model-registry-operations)
            * [Exercise 3: Automating the Model Lifecycle](#exercise-3-automating-the-model-lifecycle)
            * [Quiz: Model Lifecycle Management](#quiz-model-lifecycle-management)
            * [Key Takeaways](#key-takeaways-1)
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

## Model Lifecycle Management

- MLflow Flavors and Custom Models
- Model Registry Fundamentals
- Model Lifecycle Automation
- Exercise 1: MLflow Flavors and Custom Models
- Exercise 2: Model Registry Operations
- Exercise 3: Automating the Model Lifecycle
- Quiz: Model Lifecycle Management
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

---

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

## Model Lifecycle Management

### 1. MLflow Flavors and Custom Models

MLflow flavors provide a standardized way to package models for different frameworks.

**Key Concepts:**
- **MLflow Flavors**: Framework-specific formats for saving and loading models (sklearn, pytorch, tensorflow, etc.)
- **PyFunc Flavor**: Universal model format that can wrap any Python model
- **Custom Model Classes**: Extending MLflow with custom preprocessing logic
- **Model Signatures**: Defining input/output schemas for models

**Essential Operations:**
- Creating custom PyFunc models with preprocessing
- Saving models with different flavors
- Loading models using different flavors
- Defining model signatures and input examples

---

### 2. Model Registry Fundamentals

The Model Registry provides a centralized repository for managing the full lifecycle of your ML models.

**Key Concepts:**
- **Registered Models**: Named entities that contain different versions of a model
- **Model Versions**: Distinct iterations of a model under the same name
- **Model Stages**: Organizational states (None, Staging, Production, Archived)
- **Model Metadata**: Tags and descriptions to document models

**Essential Operations:**
- Creating and registering models
- Transitioning models between stages
- Adding metadata to models
- Retrieving models from the registry

---

### 3. Model Lifecycle Automation

Automating the model lifecycle enables CI/CD workflows for ML models.

**Key Concepts:**
- **Webhooks**: Event-triggered callbacks when model states change
- **Databricks Jobs**: Scheduled or triggered batch processing
- **CI/CD for ML**: Testing, deployment, and monitoring automation
- **Job Clusters**: Purpose-specific compute for model tasks

**Essential Operations:**
- Creating and managing webhooks
- Setting up automated testing jobs
- Building model deployment pipelines
- Connecting webhooks to jobs

---

### Exercise 1: MLflow Flavors and Custom Models

```python
# 1. Basic model with sklearn flavor
import mlflow.sklearn
from sklearn.ensemble import RandomForestRegressor
import pandas as pd
import numpy as np

# Train a model
X = np.random.rand(100, 4)
y = X[:, 0] + 2 * X[:, 1] + np.random.rand(100)
model = RandomForestRegressor(n_estimators=100)
model.fit(X, y)

# Log with sklearn flavor
with mlflow.start_run() as run:
    mlflow.sklearn.log_model(model, "sklearn_model")
    model_uri = f"runs:/{run.info.run_id}/sklearn_model"
    
# Load the model
loaded_model = mlflow.sklearn.load_model(model_uri)
predictions = loaded_model.predict(X)

# 2. Custom PyFunc model with preprocessing
import mlflow.pyfunc

# Define a custom model class with preprocessing
class CustomRFModel(mlflow.pyfunc.PythonModel):
    def __init__(self, model):
        self.model = model
        
    def predict(self, context, model_input):
        # Add preprocessing logic
        if isinstance(model_input, pd.DataFrame):
            # Scale numeric features
            numeric_cols = model_input.select_dtypes(include=[np.number]).columns
            model_input[numeric_cols] = model_input[numeric_cols] - model_input[numeric_cols].mean()
            model_input[numeric_cols] = model_input[numeric_cols] / model_input[numeric_cols].std()
            
        # Return predictions
        return self.model.predict(model_input)

# Create and log the custom model
custom_model = CustomRFModel(model)
with mlflow.start_run() as run:
    # Define the model signature
    from mlflow.models.signature import infer_signature
    signature = infer_signature(X, model.predict(X))
    
    # Provide an input example
    input_example = pd.DataFrame(X[0:5])
    
    # Log the model with all metadata
    mlflow.pyfunc.log_model(
        "custom_model",
        python_model=custom_model,
        signature=signature,
        input_example=input_example
    )
    custom_model_uri = f"runs:/{run.info.run_id}/custom_model"

# Load and use the custom model
loaded_custom_model = mlflow.pyfunc.load_model(custom_model_uri)
custom_predictions = loaded_custom_model.predict(X)
```

---

### Exercise 2: Model Registry Operations

```python
# 1. Register a model directly from a run
import mlflow.sklearn
from mlflow.tracking import MlflowClient

client = MlflowClient()

# First, log a model with MLflow
with mlflow.start_run() as run:
    mlflow.sklearn.log_model(model, "sk_model")
    run_id = run.info.run_id
    model_uri = f"runs:/{run_id}/sk_model"

# Register the model
model_name = "RandomForestRegressor"
mv = mlflow.register_model(model_uri, model_name)
print(f"Name: {mv.name}")
print(f"Version: {mv.version}")

# 2. Add description and tags to the registered model
client.update_registered_model(
    name=model_name,
    description="Random Forest Regressor for predicting target values"
)

client.set_registered_model_tag(
    name=model_name,
    key="team",
    value="data_science"
)

# 3. Add description and tags to a specific model version
client.update_model_version(
    name=model_name,
    version=mv.version,
    description="Model trained with 100 trees and default parameters"
)

client.set_model_version_tag(
    name=model_name,
    version=mv.version,
    key="train_data",
    value="synthetic_data"
)

# 4. Transition model to staging
client.transition_model_version_stage(
    name=model_name,
    version=mv.version,
    stage="Staging"
)

# 5. Create a new version and transition to production
with mlflow.start_run() as new_run:
    mlflow.sklearn.log_model(
        model,
        "sk_model",
        registered_model_name=model_name
    )
    new_run_id = new_run.info.run_id

# Find the latest version
latest_version = max([mv.version for mv in client.search_model_versions(f"name='{model_name}'")])

# Transition to production
client.transition_model_version_stage(
    name=model_name,
    version=latest_version,
    stage="Production"
)

# 6. Load a specific model version by stage
prod_model = mlflow.pyfunc.load_model(f"models:/{model_name}/Production")
staging_model = mlflow.pyfunc.load_model(f"models:/{model_name}/Staging")

# 7. Archive older versions
client.transition_model_version_stage(
    name=model_name,
    version=1,  # Assuming this is the older version
    stage="Archived"
)
```

---

### Exercise 3: Automating the Model Lifecycle

```python
# 1. Creating a webhook for Model Registry
from mlflow.tracking import MlflowClient

client = MlflowClient()

# Create a job-triggered webhook when a model is transitioned to staging
staging_webhook = client.create_webhook(
    name="Trigger-Test-Job-On-Staging",
    events=["MODEL_VERSION_TRANSITIONED_STAGE"],
    job_spec={
        "job_id": "123456",  # Replace with actual job ID
        "workspace_url": "https://your-workspace.cloud.databricks.com"
    },
    model_name=model_name,
    target_stage="Staging"
)

# Create an HTTP webhook when a model is transitioned to production
production_webhook = client.create_webhook(
    name="Notify-On-Production",
    events=["MODEL_VERSION_TRANSITIONED_STAGE"],
    http_url_spec={
        "url": "https://your-service.example.com/webhook",
        "authorization": "Bearer your-token-here"
    },
    model_name=model_name,
    target_stage="Production"
)

# 2. List all webhooks
all_webhooks = client.list_webhooks()
for webhook in all_webhooks:
    print(f"ID: {webhook.id}, Name: {webhook.name}, Events: {webhook.events}")

# 3. Delete a webhook
client.delete_webhook(webhook_id=staging_webhook.id)

# 4. Set up Databricks Jobs for model automation

# Note: This would typically be done through the Databricks UI or API
# Here's a conceptual example of what the jobs would look like:

# Job 1: Train Model (scheduled or triggered)
"""
{
    "name": "Train-RF-Model",
    "tasks": [
        {
            "task_key": "train_model",
            "notebook_task": {
                "notebook_path": "/Path/To/Training/Notebook",
                "source": "WORKSPACE"
            },
            "job_cluster_key": "training_cluster"
        }
    ],
    "job_clusters": [
        {
            "job_cluster_key": "training_cluster",
            "new_cluster": {
                "spark_version": "10.4.x-cpu-ml-scala2.12",
                "node_type_id": "Standard_DS3_v2",
                "num_workers": 2
            }
        }
    ]
}
"""

# Job 2: Test Model (triggered by webhook)
"""
{
    "name": "Test-RF-Model",
    "tasks": [
        {
            "task_key": "test_model",
            "notebook_task": {
                "notebook_path": "/Path/To/Testing/Notebook",
                "base_parameters": {
                    "model_name": "{{model.name}}",
                    "model_version": "{{model.version}}"
                }
            },
            "job_cluster_key": "testing_cluster"
        }
    ],
    "job_clusters": [
        {
            "job_cluster_key": "testing_cluster",
            "new_cluster": {
                "spark_version": "10.4.x-cpu-ml-scala2.12",
                "node_type_id": "Standard_DS3_v2",
                "num_workers": 1
            }
        }
    ]
}
"""

# Job 3: Deploy Model (triggered by webhook)
"""
{
    "name": "Deploy-RF-Model",
    "tasks": [
        {
            "task_key": "deploy_model",
            "notebook_task": {
                "notebook_path": "/Path/To/Deployment/Notebook",
                "base_parameters": {
                    "model_name": "{{model.name}}",
                    "model_version": "{{model.version}}"
                }
            },
            "job_cluster_key": "deployment_cluster"
        }
    ],
    "job_clusters": [
        {
            "job_cluster_key": "deployment_cluster",
            "new_cluster": {
                "spark_version": "10.4.x-cpu-ml-scala2.12",
                "node_type_id": "Standard_DS3_v2",
                "num_workers": 1
            }
        }
    ]
}
"""
```

---

### Quiz: Model Lifecycle Management

1. **Which MLflow flavor would you use to create a model with custom preprocessing logic?**
   A) mlflow.sklearn
   B) mlflow.custom
   C) mlflow.pyfunc
   D) mlflow.generic

2. **What happens when you register a model that already exists in the Model Registry?**
   A) It overwrites the existing model
   B) It creates a new version of the model
   C) It returns an error that the model already exists
   D) It creates a copy with a different name

3. **Which of the following is NOT a standard stage in the MLflow Model Registry?**
   A) Development
   B) Staging
   C) Production
   D) Archived

4. **When creating a webhook for model registry events, which of these is NOT a valid event type?**
   A) MODEL_VERSION_CREATED
   B) MODEL_VERSION_TRANSITIONED_STAGE
   C) REGISTERED_MODEL_CREATED
   D) MODEL_VERSION_DEPLOYED

5. **What is the correct way to load a production model from the registry?**
   A) mlflow.pyfunc.load_model("models:/model_name/production")
   B) mlflow.sklearn.load_production_model("model_name")
   C) mlflow.load_model("models:/model_name/Production")
   D) mlflow.pyfunc.load_model("models:/model_name/Production")

6. **What is the purpose of adding a model signature to an MLflow model?**
   A) Digitally sign the model to verify its creator
   B) Define the expected input and output schema
   C) Increase the model's security in the registry
   D) Document who approved the model for production

7. **Which client method is used to move a model from Staging to Production?**
   A) client.promote_model_version()
   B) client.update_model_stage()
   C) client.transition_model_version_stage()
   D) client.set_model_version_status()

8. **What would you include in a pyfunc model's predict() method to implement custom preprocessing?**
   A) Data cleaning and feature transformation logic before passing to the model
   B) Hyperparameter optimization logic
   C) Model retraining logic if performance decreases
   D) Post-processing of model outputs only

9. **What is the correct API to add a description to a model version?**
   A) client.set_model_version_description()
   B) client.update_model_version()
   C) client.add_model_description()
   D) client.update_registered_model_version()

10. **What type of compute is recommended for production Databricks Jobs?**
    A) All-purpose clusters
    B) Job clusters
    C) Single-node clusters
    D) Interactive clusters

#### Quiz Answers

1. **Which MLflow flavor would you use to create a model with custom preprocessing logic?**
   **Answer: C) mlflow.pyfunc**
   
   Explanation: The mlflow.pyfunc flavor allows you to create custom Python models by extending the PythonModel class, enabling you to implement custom preprocessing logic in the predict() method. The other flavors are for specific frameworks (sklearn) or don't exist (custom, generic).

2. **What happens when you register a model that already exists in the Model Registry?**
   **Answer: B) It creates a new version of the model**
   
   Explanation: When registering a model with a name that already exists in the registry, MLflow creates a new version under that name rather than overwriting the existing model or returning an error.

3. **Which of the following is NOT a standard stage in the MLflow Model Registry?**
   **Answer: A) Development**
   
   Explanation: The standard stages in the MLflow Model Registry are None (default), Staging, Production, and Archived. "Development" is not a standard stage.

4. **When creating a webhook for model registry events, which of these is NOT a valid event type?**
   **Answer: D) MODEL_VERSION_DEPLOYED**
   
   Explanation: Valid event types include MODEL_VERSION_CREATED, MODEL_VERSION_TRANSITIONED_STAGE, and REGISTERED_MODEL_CREATED. MODEL_VERSION_DEPLOYED is not a standard event type in MLflow webhooks.

5. **What is the correct way to load a production model from the registry?**
   **Answer: D) mlflow.pyfunc.load_model("models:/model_name/Production")**
   
   Explanation: The correct URI format is "models:/model_name/stage" and the stage name is case-sensitive, with "Production" being the proper casing. MLflow's pyfunc loader is the universal way to load any model.

6. **What is the purpose of adding a model signature to an MLflow model?**
   **Answer: B) Define the expected input and output schema**
   
   Explanation: A model signature in MLflow defines the expected data types and shapes for inputs and outputs, allowing for validation when the model is used for inference.

7. **Which client method is used to move a model from Staging to Production?**
   **Answer: C) client.transition_model_version_stage()**
   
   Explanation: The transition_model_version_stage() method of the MLflowClient is used to change a model version's stage (e.g., from Staging to Production). The other methods don't exist in the MLflow API.

8. **What would you include in a pyfunc model's predict() method to implement custom preprocessing?**
   **Answer: A) Data cleaning and feature transformation logic before passing to the model**
   
   Explanation: The predict() method in a custom pyfunc model is where you implement preprocessing logic like data cleaning and feature transformations before passing the data to the underlying model.

9. **What is the correct API to add a description to a model version?**
   **Answer: B) client.update_model_version()**
   
   Explanation: The update_model_version() method is used to update metadata for a specific model version, including its description. The other options are not valid MLflow API methods.

10. **What type of compute is recommended for production Databricks Jobs?**
    **Answer: B) Job clusters**
    
    Explanation: Job clusters are purpose-built for production workloads in Databricks. They start when a job begins and terminate when it completes, optimizing costs. All-purpose clusters are for interactive work, not production jobs.

#### Score Assessment

- **9-10 correct**: Excellent! You have a strong grasp of Model Lifecycle Management.
- **7-8 correct**: Good understanding, but review the topics you missed.
- **5-6 correct**: You're on the right track, but need more study in several areas.
- **Below 5 correct**: More intensive review needed on the Day 2 topics.

#### Areas to Focus On

Here are the concepts to review:

- **MLflow flavors**: Make sure you understand the different flavors, especially pyfunc for custom models
- **Model Registry stages**: Review the standard stages and their purpose in the workflow
- **Webhook events**: Practice setting up webhooks with different event triggers
- **Client API methods**: Familiarize yourself with the correct MLflowClient methods for different operations
- **Model URI formats**: Practice loading models using the correct URI format and stage names

---

### Key Takeaways

1. PyFunc is powerful for creating custom models with preprocessing logic
2. The Model Registry provides stages to organize model development
3. Webhooks enable event-driven automation for model transitions

---
