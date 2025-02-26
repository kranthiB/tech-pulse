---
id: data-ai/conventional-ml
title: Conventional ML
sidebar_label: Conventional ML
previous_page: data-ai/data-engineer
---

Table of contents
=================
<!--ts-->
   * [Conventional ML](#conventional-ml)
      * [Machine Learning Fundamentals](#machine-learning-fundamentals)
        * [Run-time Complexity of Popular ML Algorithms](#run-time-complexity-of-popular-ml-algorithms)
        * [Importance of Mathematics in ML](#importance-of-mathematics-in-ml)
      * [Model Evaluation and Validation](#model-evaluation-and-validation)
        * [Train, Validation, and Test Sets](#train-validation-and-test-sets)
        * [Cross Validation Techniques](#cross-validation-techniques)
        * [When to Retrain After Cross Validation](#when-to-retrain-after-cross-validation)
        * [Monitoring Probabilistic Multiclass-Classification Models](#monitoring-probabilistic-multiclass-classification-models)
        * [Model Improvement with Human Benchmarking](#model-improvement-with-human-benchmarking)
      * [Statistical Concepts](#statistical-concepts)
        * [Maximum Likelihood Estimation vs Expectation Maximization](#maximum-likelihood-estimation-vs-expectation-maximization)
        * [Confidence Intervals vs Prediction Intervals](#confidence-intervals-vs-prediction-intervals)
        * [Probability vs Likelihood](#probability-vs-likelihood)
        * [Understanding Probability Distributions](#understanding-probability-distributions)
        * [Zero Probability in Continuous Distributions](#zero-probability-in-continuous-distributions)
        * [Distance Metrics for Distributions](#distance-metrics-for-distributions)
        * [Testing for Normality](#testing-for-normality)
      * [Feature Engineering](#feature-engineering)
        * [Types of Variables in Datasets](#types-of-variables-in-datasets)
        * [Cyclical Feature Encoding](#cyclical-feature-encoding)
        * [Feature Discretization](#feature-discretization)
        * [Categorical Data Encoding](#categorical-data-encoding)
        * [Feature Importance and Selection](#feature-importance-and-selection)
      * [Linear Models](#linear-models)
        * [Why Squared Error in MSE](#why-squared-error-in-mse)
        * [Linear Regression Hyperparameters](#linear-regression-hyperparameters)
        * [Poisson vs Linear Regression](#poisson-vs-linear-regression)
        * [Building Linear Models](#building-linear-models)
        * [Dummy Variable Trap](#dummy-variable-trap)
        * [Residual Distribution in Linear Regression](#residual-distribution-in-linear-regression)
        * [Understanding Statsmodel Regression Summary](#understanding-statsmodel-regression-summary)
        * [Generalized Linear Models (GLMs)](#generalized-linear-models-glms)
        * [Zero-Inflated Regression](#zero-inflated-regression)
        * [Huber Regression](#huber-regression)
      * [Tree-Based Models](#tree-based-models)
        * [Condensing Random Forests](#condensing-random-forests)
        * [Decision Trees and Matrix Operations](#decision-trees-and-matrix-operations)
        * [Decision Tree Visualization](#decision-tree-visualization)
        * [Decision Tree Splits](#decision-tree-splits)
        * [Overfitting in Decision Trees](#overfitting-in-decision-trees)
        * [AdaBoost Algorithm](#adaboost-algorithm)
        * [Out-of-Bag Validation in Random Forests](#out-of-bag-validation-in-random-forests)
        * [Training Random Forests on Large Datasets](#training-random-forests-on-large-datasets)
      * [Dimensionality Reduction](#dimensionality-reduction)
        * [PCA and Variance](#pca-and-variance)
        * [KernelPCA vs PCA](#kernelpca-vs-pca)
        * [PCA for Visualization](#pca-for-visualization)
        * [t-SNE vs SNE](#t-sne-vs-sne)
        * [t-SNE Projections](#t-sne-projections)
        * [Accelerating t-SNE](#accelerating-t-sne)
        * [PCA vs t-SNE](#pca-vs-t-sne)
      * [Clustering Algorithms](#clustering-algorithms)
        * [Types of Clustering Algorithms](#types-of-clustering-algorithms)
        * [Intrinsic Measures for Clustering Evaluation](#intrinsic-measures-for-clustering-evaluation)
        * [Breathing KMeans: An Enhanced K-Means Algorithm](#breathing-kmeans-an-enhanced-k-means-algorithm)
        * [Mini-Batch KMeans for Large Datasets](#mini-batch-kmeans-for-large-datasets)
        * [Faiss: Accelerating KMeans with Approximate Nearest Neighbor Search](#faiss-accelerating-kmeans-with-approximate-nearest-neighbor-search)
        * [Gaussian Mixture Models vs KMeans](#gaussian-mixture-models-vs-kmeans)
        * [DBSCAN++ vs DBSCAN for Efficient Density-Based Clustering](#dbscan-vs-dbscan-for-efficient-density-based-clustering)
        * [HDBSCAN vs DBSCAN](#hdbscan-vs-dbscan)
      * [Correlation Analysis](#correlation-analysis)
        * [Predictive Power Score vs Correlation](#predictive-power-score-vs-correlation)
        * [Dangers of Summary Statistics](#dangers-of-summary-statistics)
        * [Pearson vs Spearman Correlation](#pearson-vs-spearman-correlation)
        * [Correlation with Ordinal Categorical Data](#correlation-with-ordinal-categorical-data)
      * [Model Monitoring and Drift Detection](#model-monitoring-and-drift-detection)
        * [Detecting Covariate Shift](#detecting-covariate-shift)
        * [Using Proxy-Labeling to Identify Drift](#using-proxy-labeling-to-identify-drift)
      * [kNN Algorithms and Optimizations](#knn-algorithms-and-optimizations)
        * [kNN in Imbalanced Classification](#knn-in-imbalanced-classification)
        * [Approximate Nearest Neighbor Search with Inverted File Index](#approximate-nearest-neighbor-search-with-inverted-file-index)
      * [Kernel Methods](#kernel-methods)
        * [Kernel Trick Explained](#kernel-trick-explained)
        * [Radial Basis Function (RBF) Kernel](#radial-basis-function-rbf-kernel)
      * [Missing Data Analysis](#missing-data-analysis)
        * [Types of Missing Data](#types-of-missing-data)
        * [MissForest and kNN Imputation](#missforest-and-knn-imputation)
<!--te-->

## Conventional ML

### Machine Learning Fundamentals

#### Run-time Complexity of Popular ML Algorithms

Understanding the run-time complexity of machine learning algorithms is crucial when dealing with large datasets. This affects both training and inference times, and can be the deciding factor in algorithm selection.

Here's the run-time complexity of 10 popular ML algorithms:

- **Linear Regression (OLS)**: O(nd²) where n is the number of samples and d is the number of features
- **SVM**: O(n³) - runtime grows cubically with the total number of samples
- **Decision Tree**: O(nd log n) 
- **Random Forest**: O(K × nd log n) where K is the number of trees
- **k-Nearest Neighbors (kNN)**: 
  - Training: O(1) (just stores the data)
  - Inference: O(nd + n log k) where k is the number of neighbors
- **K-Means**: O(nkdi) where k is the number of clusters, d is dimensions, i is iterations
- **t-SNE**: O(n²) - quadratic with the number of samples
- **PCA**: O(nd² + d³)
- **Logistic Regression**: O(nd)
- **Neural Networks**: Varies based on architecture

When selecting algorithms, consider:
- The size of your dataset
- Available computational resources
- Required inference speed
- Whether you need to retrain frequently

For example, SVM or t-SNE will struggle with very large datasets due to their O(n³) and O(n²) complexity respectively, while linear models scale better with sample size.

-----

#### Importance of Mathematics in ML

Many data scientists can build and deploy models without fully understanding the underlying mathematics, thanks to libraries like sklearn. However, this comes with significant disadvantages:

- Difficulty optimizing models
- Struggle identifying improvement areas
- Longer debugging time
- Incomplete understanding of hyperparameters
- Inability to estimate algorithm time complexity

Key mathematical concepts essential for data science include:

- **Maximum Likelihood Estimation (MLE)**: A method for estimating statistical model parameters by maximizing the likelihood of observed data
- **Gradient Descent**: Optimization algorithm for finding local minima
- **Normal Distribution**: Understanding probability distributions
- **Eigenvectors**: Used in dimensionality reduction techniques like PCA
- **Z-score**: Standardized value indicating standard deviations from the mean
- **Entropy**: Measure of uncertainty of a random variable
- **R-squared**: Statistical measure representing variance explained by regression
- **KL Divergence**: Assesses information loss when approximating distributions
- **SVD (Singular Value Decomposition)**: Matrix factorization technique
- **Lagrange Multipliers**: Used for constrained optimization problems

Building mathematical intuition transforms your approach from trial-and-error to principled understanding.

-----

### Model Evaluation and Validation

#### Train, Validation, and Test Sets

The proper use of train, validation, and test sets is crucial for model development:

1. **Split data** into train, validation, and test sets
2. **Use the train set** for all analysis, transformations, and initial model fitting
3. **Evaluate on validation set** to guide model improvements
4. **Iterate between training and validation** until satisfied
5. **If validation set is "exhausted"** (overfitted), merge it with train and create a new split
6. **Only use test set once** for final unbiased evaluation
7. **If model underperforms on test**, go back to modeling but create new splits

Important considerations:
- The test set should never influence model decisions
- Once used, a test set should not be reused
- Cross-validation is preferable when data is limited

-----

#### Cross Validation Techniques

Cross validation provides more robust model performance estimates by repeatedly partitioning data into training and validation subsets:

1. **Leave-One-Out Cross Validation**:
   - Leaves one data point for validation
   - Trains on remaining data points
   - Repeats for all points
   - Computationally expensive for large datasets

2. **K-Fold Cross Validation**:
   - Splits data into k equally-sized subsets
   - Uses one subset for validation, rest for training
   - Repeats k times, using each subset once for validation
   - Common choice: k=5 or k=10

3. **Rolling Cross Validation**:
   - Used for time-series data
   - Maintains temporal order with fixed-size training windows
   - Evaluates on subsequent windows

4. **Block Cross Validation**:
   - Another technique for time-series data
   - Uses shorter data slices when variance is steady

5. **Stratified Cross Validation**:
   - Preserves class distribution in each fold
   - Essential for imbalanced datasets

-----

#### When to Retrain After Cross Validation

After cross-validation identifies optimal hyperparameters, you have two options:

1. **Retrain on entire dataset** (train + validation + test) with optimal hyperparameters
   - Advantages: Uses all available data
   - Disadvantages: Cannot reliably validate the final model

2. **Use the best model** from cross-validation
   - Advantages: Already validated performance
   - Disadvantages: Leaves out potentially valuable training data

The recommended approach is usually to retrain on the entire dataset because:
- Cross-validation has already estimated out-of-fold performance
- Including validation data likely won't harm generalization
- It maximizes use of available training data

Exceptions include when:
- Training takes days/weeks
- Stakes are extremely high (e.g., fraud detection)
- You can gather new data for final validation

-----

#### Monitoring Probabilistic Multiclass-Classification Models

Traditional accuracy metrics can be misleading when iteratively improving probabilistic multiclass models. Consider using:

**Top-k Accuracy Score**: Measures whether the correct label appears among the top k predicted labels.

Benefits:
- Captures gradual model improvements
- Shows if the model is getting "closer" to correct predictions
- Available in sklearn as `top_k_accuracy_score`

For example, if top-3 accuracy improves from 75% to 90%, it indicates the model is improving even if traditional accuracy remains unchanged.

-----

#### Model Improvement with Human Benchmarking

A powerful technique for guiding model improvements is comparing model performance against human performance on the same task:

1. Gather human labels for a sample of your dataset
2. Calculate accuracy for both humans and the model
3. Compare class-wise accuracies
4. Focus improvement efforts on classes where the gap between human and model performance is largest

For example, if your model achieves:
- 85% accuracy on "Rock" vs. 98% for humans (13% gap)
- 70% accuracy on "Scissors" vs. 72% for humans (2% gap)

This reveals that "Rock" needs more attention, even though absolute performance on "Scissors" is lower.

This technique:
- Provides clarity on which classes need improvement
- Establishes realistic performance goals
- Helps determine when a model has reached diminishing returns

-----

### Statistical Concepts

#### Maximum Likelihood Estimation vs Expectation Maximization

**Maximum Likelihood Estimation (MLE)**:
- Used when we have labeled data
- Finds parameters that maximize the likelihood of observing the given data
- Process:
  1. Assume a data generation process
  2. Define likelihood of observing the data
  3. Find parameters that maximize this likelihood

**Expectation Maximization (EM)**:
- Used when we have unobserved/hidden labels
- Iterative optimization technique
- Process:
  1. Make initial parameter guess
  2. E-step: Compute posterior probabilities of unobserved label
  3. M-step: Maximize expected likelihood to get new parameters
  4. Repeat until convergence

EM is particularly useful for clustering where true labels are unknown. Unlike MLE which directly maximizes likelihood, EM iteratively improves estimates of both parameters and labels.

-----

#### Confidence Intervals vs Prediction Intervals

Statistical models always involve uncertainty which should be communicated:

**Confidence Intervals**:
- Represent uncertainty in estimating the true mean value
- Narrower than prediction intervals
- Capture sampling uncertainty
- Example: "We are 95% confident the mean house price for this square footage is between $190,000-$210,000"

**Prediction Intervals**:
- Represent uncertainty in predicting a specific value
- Wider than confidence intervals
- Include both sampling uncertainty and individual observation variance
- Example: "We are 95% confident a house of this size will sell between $165,000-$235,000"

Key differences:
- Confidence intervals address: "How certain are we about our estimate of the average?"
- Prediction intervals address: "How certain are we about a single future value?"
- More data narrows confidence intervals but has less impact on prediction intervals

-----

#### Probability vs Likelihood

Though often used interchangeably in everyday language, probability and likelihood have distinct meanings in statistics:

**Probability**:
- Used to determine the possibility of an event
- Parameters are known and trusted
- Example: "What's the probability of obtaining heads in a fair coin toss?"
- In ML: "What's the probability this image contains a cat?"

**Likelihood**:
- Used to evaluate parameters based on observed data
- Quantifies how well parameters explain observations
- Example: "Given these coin toss outcomes, what's the likelihood this coin is fair?"
- In ML: Used during training to find optimal parameters

The relationship can be summarized as:
- Probability: Given parameters, what's the chance of certain data?
- Likelihood: Given data, how reasonable are these parameters?

This distinction is fundamental to understanding model training, especially maximum likelihood estimation.

-----

#### Understanding Probability Distributions

Statistical models assume a data generation process, making knowledge of probability distributions essential. Key distributions include:

**Normal Distribution**:
- Symmetric bell-shaped curve
- Parameterized by mean and standard deviation
- Example: Heights of individuals

**Bernoulli Distribution**:
- Models binary events
- Parameterized by probability of success
- Example: Single coin flip outcome

**Binomial Distribution**:
- Bernoulli distribution repeated multiple times
- Counts successes in fixed number of trials
- Example: Number of heads in 10 coin flips

**Poisson Distribution**:
- Models count of events in fixed interval
- Parameterized by rate of occurrence
- Example: Number of customer arrivals per hour

**Exponential Distribution**:
- Models time between events in Poisson process
- Example: Wait time between customer arrivals

**Gamma Distribution**:
- Variation of exponential distribution
- Models waiting time for multiple events
- Example: Time until three customers arrive

**Beta Distribution**:
- Models probabilities (bounded between [0,1])
- Unlike Binomial where probability is parameter, in Beta it's a random variable

**Uniform Distribution**:
- Equal probability across range
- Can be discrete or continuous
- Example: Die roll outcomes

**Log-Normal Distribution**:
- Log of variable follows normal distribution
- Example: Stock prices, income distributions

**Student's t-Distribution**:
- Similar to normal but with heavier tails
- Used in t-SNE for low-dimensional similarities

**Weibull Distribution**:
- Models waiting time for events
- Often used for time-to-failure analysis

-----

#### Zero Probability in Continuous Distributions

In continuous probability distributions, the probability of any specific exact value is zero, which is counterintuitive but mathematically sound.

For example, if travel time follows a uniform distribution between 1-5 minutes:
- The probability of taking exactly 3 minutes is zero
- We can only meaningfully ask about ranges (e.g., between 2.9-3.1 minutes)

This occurs because:
- Continuous distributions have infinitely many possible values
- Probability is calculated as area under the curve
- A single point has zero width, therefore zero area

This is why we use probability density functions (PDFs) to calculate probabilities over intervals rather than at specific points.

-----

#### Distance Metrics for Distributions

**Bhattacharyya Distance**:
- Quantifies similarity between probability distributions
- Measures overlap between distributions
- Higher values indicate less similarity
- Symmetric (distance A→B equals B→A)
- Useful for:
  - Simplifying complex distributions
  - Image matching
  - Comparing observed data to reference distributions

**KL Divergence vs Bhattacharyya Distance**:
- KL Divergence measures information lost when approximating one distribution with another
- Bhattacharyya measures overlap or closeness
- KL Divergence is asymmetric, Bhattacharyya is symmetric
- KL Divergence is used as a loss function in some algorithms (e.g., t-SNE)

**Mahalanobis Distance vs Euclidean Distance**:
- Euclidean distance assumes independent axes and can be misleading with correlated features
- Mahalanobis distance accounts for data distribution and correlation between features
- Process:
  1. Transform to uncorrelated variables
  2. Scale to unit variance
  3. Calculate Euclidean distance in new space
- Particularly useful for:
  - Outlier detection
  - Working with correlated features
  - Modified kNN implementations

-----

#### Testing for Normality

Many ML models assume or work better with normally distributed data. Methods to test normality include:

**Visual Methods**:
- Histogram
- QQ Plot
- KDE Plot
- Violin Plot

**Statistical Tests**:
1. **Shapiro-Wilk test**:
   - Uses correlation between observed data and expected normal values
   - High p-value indicates normality

2. **Kolmogorov-Smirnov (KS) test**:
   - Measures maximum difference between observed and theoretical CDFs
   - High p-value indicates normality

3. **Anderson-Darling test**:
   - Emphasizes differences in distribution tails
   - More sensitive to deviations in extreme values

4. **Lilliefors test**:
   - Modified KS test for unknown parameters

**Distance Measures**:
- Compare observed distribution to multiple reference distributions
- Choose distribution with minimum distance
- Common measures:
  - Bhattacharyya distance
  - Hellinger distance
  - KL Divergence

-----

### Feature Engineering

#### Types of Variables in Datasets

Understanding variable types helps guide appropriate handling during analysis:

**Independent and Dependent Variables**:
- Independent variables: Features/predictors used as input
- Dependent variable: Target/outcome being predicted

**Confounding Variables**:
- Not primary interest but influence both independent and dependent variables
- Can lead to spurious associations
- Example: Temperature affecting both ice cream sales and air conditioner sales
- Why "correlation doesn't imply causation"

**Control Variables**:
- Variables held constant during analysis
- Help isolate true causal relationships

**Latent Variables**:
- Not directly observed but inferred
- Example: Intelligence (inferred from test scores)
- In clustering, true labels are latent variables

**Interaction Variables**:
- Represent combined effect of multiple variables
- Created by cross-multiplying features
- Example: Income-level * Population-density

**Stationary and Non-Stationary Variables**:
- Stationary: Statistical properties don't change over time
- Non-stationary: Properties evolve over time
- Critical for time-series analysis
- Non-stationary features often transformed to relative changes

**Lagged Variables**:
- Previous time points' values
- Common in time-series forecasting
- Example: Previous month's sales to predict current month

**Leaky Variables**:
- Unintentionally provide information about target
- Lead to overoptimistic model performance
- Example: Patient images in both train and test sets

-----

#### Cyclical Feature Encoding

Cyclical features (like hour-of-day, day-of-week, month) require special encoding to preserve their circular nature:

**The Problem**:
- Standard encoding loses crucial information
- Example: Hours 23 and 0 should be close, but numerically they're far apart
- Distance between adjacent values should be equal

**Solution: Trigonometric Encoding**:
- Use sine and cosine functions
- Formula:
  ```
  sin_x = sin(2π * x / max_value)
  cos_x = cos(2π * x / max_value)
  ```
- Example for hour (0-23):
  ```
  sin_hour = sin(2π * hour / 24)
  cos_hour = cos(2π * hour / 24)
  ```

**Benefits**:
- Preserves cyclical nature
- Distance between adjacent values is constant
- Works for any cyclical feature (hours, days, months, angles)

-----

#### Feature Discretization

Feature discretization transforms continuous features into discrete features:

**Rationale**:
- Sometimes continuous values are better understood in groups
- Example: Age as youngsters/adults/seniors instead of exact years
- Can reveal more valuable insights than raw features

**Techniques**:
1. **Equal Width Binning**:
   - Divides range into equal-sized bins
   - Simple but sensitive to outliers

2. **Equal Frequency Binning**:
   - Each bin contains equal number of observations
   - Better handles skewed distributions

**Benefits**:
- Enables non-linear behavior even with linear models
- Improves signal-to-noise ratio by smoothing minor fluctuations
- Makes interpretations more intuitive

**Considerations**:
- Increases dimensionality after one-hot encoding
- Can lead to overfitting
- Best used when it makes intuitive sense

-----

#### Categorical Data Encoding

Seven techniques for encoding categorical features:

1. **One-Hot Encoding**:
   - Each category gets binary feature (0 or 1)
   - Features = Number of categories
   - Preserves no ordinal relationship

2. **Dummy Encoding**:
   - One-hot encoding minus one feature
   - Avoids multicollinearity (dummy variable trap)
   - Features = Number of categories - 1

3. **Effect Encoding**:
   - Similar to dummy but reference category = -1
   - Features = Number of categories - 1

4. **Label Encoding**:
   - Assigns unique integer to each category
   - Creates artificial ordering
   - Features = 1

5. **Ordinal Encoding**:
   - Similar to label but preserves actual order
   - Features = 1

6. **Count Encoding**:
   - Replaces category with its frequency
   - Features = 1

7. **Binary Encoding**:
   - Converts categories to binary code
   - Features = log2(number of categories)
   - Efficient for high-cardinality features

The choice depends on:
- Whether categories have natural order
- Number of categories
- Model type
- Concern about dimensionality

-----

#### Feature Importance and Selection

**Shuffle Feature Importance**:
- Intuitive technique to measure feature importance
- Process:
  1. Measure baseline model performance
  2. Randomly shuffle one feature
  3. Measure performance drop
  4. Repeat for all features
- Features with larger performance drops are more important
- Advantages:
  - No retraining required
  - Intuitive interpretation
  - Works with any model type
- Limitation: Correlated features may show lower importance

**The Probe Method** for feature selection:
- Process:
  1. Add random feature (noise)
  2. Train model
  3. Measure feature importance
  4. Discard features less important than random feature
  5. Repeat until convergence
- Intuition: If a feature is less important than random noise, it's useless
- Helps reduce model complexity
- Requires multiple model trainings

-----

### Linear Models

#### Why Squared Error in MSE

Mean Squared Error (MSE) is the most common loss function for regression, but why specifically use squared error?

From a probabilistic perspective:
1. In linear regression, we assume data follows: y = Xθ + ε where ε ~ N(0, σ²)
2. This means the likelihood of observing data is:
   P(y|X,θ) = (1/√(2πσ²)) * exp(-(y-Xθ)²/(2σ²))
3. For all data points, the likelihood is the product of individual likelihoods
4. Taking log of likelihood and maximizing:
   log(P(y|X,θ)) ∝ -∑(y-Xθ)²
5. Maximizing this is equivalent to minimizing squared error

Therefore, squared error in MSE directly emerges from maximum likelihood estimation under Gaussian noise assumption. It's not arbitrary but has strong statistical foundations.

-----

#### Linear Regression Hyperparameters

Sklearn's LinearRegression implementation has no hyperparameters because it uses Ordinary Least Squares (OLS) rather than gradient descent:

**OLS vs Gradient Descent**:
- **Gradient Descent**:
  - Stochastic algorithm with randomness
  - Approximate solution via optimization
  - Has hyperparameters (learning rate, etc.)

- **Ordinary Least Squares**:
  - Deterministic algorithm
  - Always finds optimal solution
  - No hyperparameters

OLS closed-form solution: θ = (X^T X)^(-1) X^T y

This approach:
- Always finds the same optimal solution
- Requires no hyperparameter tuning
- Has cubic time complexity with feature count
- Can be impractical for very high-dimensional data

For large feature sets, gradient descent methods like SGDRegressor may be more practical.

-----

#### Poisson vs Linear Regression

Linear regression has limitations that Poisson regression addresses:

**Linear Regression Limitations**:
- Can predict negative values (nonsensical for count data)
- Assumes residuals are normally distributed around mean
- Assumes outcomes on either side of mean equally likely

**Poisson Regression**:
- Suitable for count data (always non-negative)
- Assumes response follows Poisson distribution
- Models log of expected count: log(λ) = Xβ
- Variance equals mean (unlike linear regression's constant variance)
- Asymmetric distribution around mean

Example use cases:
- Number of events in time period
- Count data like calls received, goals scored
- Any non-negative integer outcomes

-----

#### Building Linear Models

Understanding the data generation process is critical when selecting linear models:

Every generalized linear model relates to a specific data distribution:
- Normal distribution → Linear Regression
- Poisson distribution → Poisson Regression (count data)
- Bernoulli distribution → Logistic Regression (binary data)
- Binomial distribution → Binomial Regression (categorical data)

This connection helps you:
- Select appropriate models based on data characteristics
- Understand model assumptions
- Make informed modeling decisions
- Avoid blindly applying algorithms

Instead of trial and error, first consider: "What process likely generated this data?"

-----

#### Dummy Variable Trap

When one-hot encoding categorical variables, we introduce perfect multicollinearity:

**The Problem**:
- If we have n categories and n one-hot encoded features, we can predict any feature using the others
- Example: If we know n-1 features are 0, the nth must be 1
- This redundancy makes regression coefficients unreliable

**Solution**:
- Drop any one category from the one-hot encoded features
- This breaks the linear relationship
- Known as "dummy encoding"

This is why sklearn and other libraries automatically drop one category when encoding.

-----

#### Residual Distribution in Linear Regression

Linear regression assumes normally distributed residuals. A residual distribution plot helps verify this:

**What to Look For**:
- Good residual plot: Bell-shaped, centered at zero, no patterns
- Bad residual plot: Skewed, shows trends or patterns

**Advantages**:
- Works in high dimensions where regression line can't be visualized
- Residual distribution is always one-dimensional
- Quickly identifies assumption violations

If residuals aren't normally distributed, consider:
- Data transformations
- Different model types
- Adding features

-----

#### Understanding Statsmodel Regression Summary

Statsmodel provides comprehensive regression analysis summaries with three key sections:

**Section 1: Model Configuration and Overall Performance**:
- Dependent variable, method, observations
- R-squared: Variance explained by model
- Adjusted R-squared: Accounts for feature count
- F-statistic: Overall model significance
- AIC/BIC: Goodness of fit measures with complexity penalty

**Section 2: Feature Details**:
- Coefficients: Estimated effect of each feature
- t-statistic and p-values: Individual feature significance
- Confidence intervals: Range for true coefficient values

**Section 3: Assumption Tests**:
- Omnibus/Jarque-Bera: Tests residual normality
- Skew/Kurtosis: Residual distribution shape
- Durbin-Watson: Tests residual autocorrelation
- Condition Number: Tests multicollinearity

These metrics help validate model assumptions and guide improvements.

-----

#### Generalized Linear Models (GLMs)

GLMs extend linear regression by relaxing its strict assumptions:

**Linear Regression Assumptions**:
1. Conditional distribution of Y given X is Gaussian
2. Mean is linear combination of features
3. Constant variance across all X levels

**How GLMs Relax These**:
- Allow different distributions (Poisson, Binomial, etc.)
- Transform relationship between X and mean (link functions)
- Allow variance to change with X

This makes linear models more adaptable to real-world data and helps address issues like:
- Count data with Poisson regression
- Binary outcomes with logistic regression
- Categorical data with multinomial regression

-----

#### Zero-Inflated Regression

For datasets with many zero values in the target variable:

**The Problem**:
- Regular regression models struggle with excess zeros
- Can't predict exact zeros frequently enough
- Leads to poor fit

**Solution: Two-Model Approach**:
1. Binary classifier to predict zero vs. non-zero
2. Regression model trained only on non-zero examples

**Prediction Process**:
- If classifier predicts "zero", output zero
- If classifier predicts "non-zero", use regression prediction

This approach significantly improves performance on zero-inflated datasets like:
- Count data with many zeros
- Sales data with many non-purchasing customers
- Event occurrence with many non-event periods

-----

#### Huber Regression

Linear regression is sensitive to outliers due to squared error magnifying large residuals.

**Huber Regression Solution**:
- Uses Huber loss function with threshold parameter δ
- For residuals < δ: Uses squared error (like linear regression)
- For residuals ≥ δ: Uses linear loss (less sensitive to outliers)

**Determining δ**:
- Create residual plot from regular regression
- Identify where outliers begin
- Set threshold at this point

Huber regression provides robust predictions while maintaining the interpretability of linear models.

-----

### Tree-Based Models

#### Condensing Random Forests

A technique to convert a random forest into a single decision tree with comparable performance:

**Process**:
1. Train a random forest model
2. Generate predictions on training data
3. Train a single decision tree on original features and random forest predictions

**Benefits**:
- Decreased prediction time
- Improved interpretability
- Reduced memory footprint
- Simplified model
- Maintains generalization power

This works because the decision tree learns to mimic the more complex random forest model's decision boundaries.

-----

#### Decision Trees and Matrix Operations

Decision tree inference can be transformed into matrix operations for faster prediction:

**The Process**:
1. Create five matrices representing tree structure:
   - Matrix A: Features used at each node
   - Matrix B: Thresholds at each node
   - Matrix C: Left/right subtree mappings
   - Matrix D: Sum of non-negative entries in Matrix C
   - Matrix E: Mapping from leaf nodes to class labels

2. For prediction, use matrix operations:
   ```
   XA < B
   Result × C
   Compare with D
   Multiply by E
   ```

**Benefits**:
- Enables parallelization
- Allows GPU acceleration (40x speedup)
- Maintains identical accuracy
- Makes deployment more efficient

-----

#### Decision Tree Visualization

Interactive Sankey diagrams provide an elegant way to visualize and prune decision trees:

**Advantages over Standard Visualization**:
- Interactive node collapsing
- Size and color encoding for class distribution
- Intuitive representation of data flow
- Easier identification of pruning candidates

This visualization helps quickly determine optimal tree depth and identify unnecessary splits.

-----

#### Decision Tree Splits

Decision trees make only perpendicular (axis-aligned) splits, which can be inefficient for diagonal decision boundaries:

**The Issue**:
- Trees create boundaries perpendicular to feature axes
- Diagonal boundaries require many perpendicular splits
- Results in unnecessarily complex trees

**Detection and Solutions**:
1. Inspect decision tree visualization
2. If many small, closely-spaced splits, suspect diagonal boundary
3. Try PCA transformation to align with boundary
4. Consider alternative models (logistic regression, SVM)
5. Engineer features aligned with natural boundaries

Understanding this limitation helps choose appropriate models or transformations.

-----

#### Overfitting in Decision Trees

By default, decision trees grow until all leaves are pure, leading to 100% overfitting:

**Cost-Complexity Pruning (CCP) Solution**:
- Balances misclassification cost against tree complexity
- Removes subtrees that minimally increase error but maximize complexity reduction
- Controlled by ccp_alpha parameter:
  - Large alpha → underfitting (simpler tree)
  - Small alpha → overfitting (complex tree)

This produces simpler trees with better generalization.

-----

#### AdaBoost Algorithm

AdaBoost builds strong models from weak learners through weighted ensembling:

**Process**:
1. Assign equal weights to all training instances
2. Train weak learner (typically decision stump)
3. Calculate error as sum of weights for incorrect predictions
4. Calculate learner importance based on error
5. Update instance weights:
   - Decrease weights for correct predictions
   - Increase weights for incorrect predictions
6. Normalize weights to sum to one
7. Sample new training data based on weights
8. Repeat steps 2-7 for specified iterations

**Final prediction** combines all weak learners weighted by their importance.

This approach progressively focuses on difficult examples, creating a powerful ensemble.

-----

#### Out-of-Bag Validation in Random Forests

Random forests allow performance evaluation without a separate validation set:

**How It Works**:
- Each tree in random forest uses bootstrap sample (~63% of data)
- Remaining ~37% are "out-of-bag" (OOB) samples
- For each data point, collect predictions only from trees that didn't use it in training
- Aggregate these predictions for final OOB prediction
- Calculate performance metrics using OOB predictions

**Benefits**:
- No data splitting required
- Computationally efficient
- No data leakage

**Considerations**:
- Use cautiously for model selection
- Still benefits from final validation on truly unseen data

-----

#### Training Random Forests on Large Datasets

Most ML implementations require entire dataset in memory, limiting their use with very large datasets.

**Random Patches Approach**:
1. Sample random data patches (subsets of rows and columns)
2. Train tree model on each patch
3. Repeat to create ensemble

**Benefits**:
- Works with data too large for memory
- Often performs better than traditional random forest
- Increases diversity between trees
- Further reduces variance

This approach enables tree-based models on massive datasets without specialized frameworks.

-----

### Dimensionality Reduction

#### PCA and Variance

Principal Component Analysis (PCA) aims to retain maximum variance during dimensionality reduction. But why focus on variance?

**The Intuition**:
- Features with higher variance typically contain more information
- Example: If height varies greatly but weight barely differs, height better distinguishes individuals
- Retaining variance = retaining information

PCA works by:
1. Transforming data to create uncorrelated features
2. Measuring variance of each new feature
3. Keeping features with highest variance

This approach maximizes information retention while reducing dimensions.

-----

#### KernelPCA vs PCA

Standard PCA has limitations with non-linear data:

**The Problem**:
- PCA only finds linear subspaces
- Many datasets have non-linear structures
- Linear projection loses important information

**KernelPCA Solution**:
- Uses kernel trick to implicitly transform data to higher dimensions
- Applies standard PCA in transformed space
- Creates non-linear projections in original space

**Tradeoffs**:
- Better fits non-linear data
- Increased computational complexity (quadratic with sample count)
- Less interpretable components

Consider KernelPCA when data shows clear non-linear patterns that PCA can't capture.

-----

#### PCA for Visualization

Using PCA for 2D visualization requires caution:

**Potential Issue**:
- First two components may not capture sufficient variance
- Results in misleading visualization

**Solution: Check Explained Variance**:
- Create cumulative explained variance plot
- Only use PCA for visualization if first two components explain substantial variance (>70-80%)
- Otherwise, use visualization-specific techniques (t-SNE, UMAP)

Example guideline:
- >90% explained variance: PCA visualization is reliable
- 70-90%: Use with caution
- <70%: Consider alternative visualization techniques

-----

#### t-SNE vs SNE

t-SNE improves upon Stochastic Neighbor Embedding (SNE) for visualization:

**SNE Process**:
1. Convert high-dimensional distances to Gaussian probabilities
2. Initialize low-dimensional points randomly
3. Define similar conditional probabilities in low dimensions
4. Minimize KL divergence between distributions

**t-SNE Improvement**:
- Uses t-distribution instead of Gaussian in low dimensions
- Creates more separated clusters by having heavier tails
- Addresses "crowding problem" in SNE
- Computationally more efficient

This produces better separated, more interpretable visualizations.

-----

#### t-SNE Projections

t-SNE visualizations require careful interpretation:

**Cautions**:
- Perplexity parameter drastically affects results
- Cluster shapes in projection don't reflect original shapes
- Cluster sizes are not meaningful
- Distances between clusters don't represent high-dimensional distances
- Axes have no inherent meaning

**Best Practices**:
- Try multiple perplexity values (typically 5-50)
- Don't over-interpret specific positions
- Focus on cluster membership, not geometry
- Use for exploring structure, not making precise claims
- Always combine with other analysis methods

-----

#### Accelerating t-SNE

t-SNE is computationally intensive with O(n²) complexity, making it impractical for large datasets:

**GPU Acceleration (tSNE-CUDA)**:
- CUDA implementation of t-SNE algorithm
- 33-700x faster than sklearn implementation
- Enables visualization of much larger datasets
- Similar quality to standard implementation
- Limited to 2D projections

**CPU Optimization (openTSNE)**:
- 20x faster than sklearn without GPU
- Scales to millions of data points
- Better memory management
- Similar quality to standard implementation

These implementations make t-SNE practical for large-scale visualization tasks.

-----

#### PCA vs t-SNE

Key differences between PCA and t-SNE:

**Purpose**:
- PCA: Primarily dimensionality reduction
- t-SNE: Primarily visualization

**Algorithm Type**:
- PCA: Deterministic (same result every run)
- t-SNE: Stochastic (different results each run)

**Uniqueness**:
- PCA: Unique solution (rotation of axes)
- t-SNE: Multiple possible solutions

**Approach**:
- PCA: Linear technique
- t-SNE: Non-linear technique

**Preservation**:
- PCA: Preserves global variance
- t-SNE: Preserves local relationships

When to use each:
- PCA: For dimensionality reduction, feature extraction, or when interpretability matters
- t-SNE: For visualization, cluster identification, or exploring complex data structure

-----

### Clustering Algorithms

#### Types of Clustering Algorithms

Clustering algorithms can be categorized into six main types, each with its own strengths and application areas:

1. **Centroid-based Clustering**: 
   - Clusters data based on proximity to centroids
   - Example: K-Means
   - Best for: Well-separated, globular clusters of similar size

2. **Connectivity-based Clustering**:
   - Clusters points based on proximity between clusters
   - Example: Hierarchical clustering
   - Best for: Finding hierarchical relationships in data

3. **Density-based Clustering**:
   - Clusters points based on areas of high density
   - Example: DBSCAN, HDBSCAN
   - Best for: Irregularly shaped clusters and detecting outliers

4. **Graph-based Clustering**:
   - Clusters points based on graph distance
   - Example: Spectral clustering
   - Best for: Complex, non-linear structures

5. **Distribution-based Clustering**:
   - Clusters points based on probability of belonging to the same distribution
   - Example: Gaussian Mixture Models
   - Best for: When underlying distributions are known or suspected

6. **Compression-based Clustering**:
   - Transforms data to lower dimensions then performs clustering
   - Example: Deep embedded clustering
   - Best for: High-dimensional data

Understanding these categories helps in selecting the appropriate algorithm for specific data characteristics and clustering objectives.

-----

#### Intrinsic Measures for Clustering Evaluation

Without labeled data, evaluating clustering quality requires intrinsic measures. These metrics help determine the optimal number of clusters and assess overall clustering quality:

1. **Silhouette Coefficient**:
   - Measures how well each data point fits into its assigned cluster
   - For each point:
     - Calculate A = average distance to all points in the same cluster
     - Calculate B = average distance to all points in the nearest cluster
     - Score = (B-A)/max(B,A)
   - Overall score = average of all individual scores
   - Range: -1 to 1 (higher is better)
   - Time complexity: O(n²)

2. **Calinski-Harabasz Index**:
   - Ratio of between-cluster variance to within-cluster variance
   - A = sum of squared distances between centroids and overall center
   - B = sum of squared distances between points and their centroids
   - Score = A/B (with scaling factor)
   - Higher values indicate better-defined clusters
   - Faster than Silhouette (especially for large datasets)

3. **Density-Based Clustering Validation (DBCV)**:
   - Specifically for evaluating arbitrary-shaped clustering algorithms
   - Computes density within clusters and density overlap between clusters
   - More appropriate for density-based clustering methods like DBSCAN
   - Overcomes bias of Silhouette and Calinski-Harabasz toward convex clusters

When evaluating clustering results:
- Use multiple metrics for comprehensive assessment
- Match the evaluation metric to the clustering algorithm type
- For arbitrary-shaped clusters, prefer DBCV over traditional metrics
- Consider computational requirements for large datasets

-----

#### Breathing KMeans: An Enhanced K-Means Algorithm

KMeans clustering effectiveness depends heavily on centroid initialization. Breathing KMeans addresses this limitation with a "breathe-in, breathe-out" approach:

**Process:**
1. **Run Standard KMeans** once without repetition
2. **Breathe In**: Add m new centroids (typically m=5)
   - New centroids are added near existing centroids with high error
   - High error = large sum of squared distances to assigned points
   - Intuition: High error centroids likely represent multiple clusters
3. **Run KMeans** once with k+m centroids
4. **Breathe Out**: Remove m centroids with lowest utility
   - Utility = distance from other centroids (isolated centroids have higher utility)
   - After removing each centroid, recalculate utility for remaining centroids
5. **Run KMeans** once with resulting k centroids
6. **Repeat** breathing cycles until convergence

**Benefits:**
- More accurate clustering than standard KMeans
- Faster convergence (typically 50% runtime improvement)
- Less dependent on initialization
- Better handles complex cluster structures

This approach effectively splits clusters with high error and merges similar clusters, leading to more optimal centroid placement. Implementation is available in the `bkmeans` Python library with a sklearn-like API.

-----

#### Mini-Batch KMeans for Large Datasets

Standard KMeans requires the entire dataset to fit in memory, creating challenges for large datasets. Mini-Batch KMeans addresses this limitation:

**Memory Bottleneck in Standard KMeans:**
- Step 1: Initialize centroids
- Step 2: Find nearest centroid for each point
- Step 3: Reassign centroids as average of assigned points
- Step 4: Repeat until convergence

The bottleneck occurs in Step 3, which requires all points in memory to compute averages.

**Mini-Batch KMeans Solution:**
1. Initialize centroids
2. For each centroid, maintain:
   - A "sum-vector" (initialized to zero)
   - A "count" variable (initialized to zero)
3. Process data in mini-batches:
   - For each point in batch, find nearest centroid
   - Update sum-vector for assigned centroid
   - Increment count for assigned centroid
4. After processing all batches, calculate new centroid positions:
   - New position = sum-vector / count
5. Reset sum-vectors and counts
6. Repeat until convergence

This approach uses constant memory regardless of dataset size and allows processing of datasets larger than available memory. The implementation is available in scikit-learn as `MiniBatchKMeans`.

-----

#### Faiss: Accelerating KMeans with Approximate Nearest Neighbor Search

Standard KMeans has a runtime bottleneck in finding the nearest centroid for each point (an exhaustive search). Facebook AI Research's Faiss library accelerates this process:

**How Faiss Works:**
- Uses approximate nearest-neighbor search algorithms
- Implements "Inverted Index" data structure to optimize searching
- Provides GPU acceleration for further speedup

**Performance Benefits:**
- 20x faster than sklearn's KMeans on large datasets
- Example: On 500k points with 1024 dimensions
  - Sklearn KMeans: ~4.5 minutes
  - Faiss KMeans: ~12 seconds
- Same accuracy as traditional KMeans

Faiss is particularly valuable for:
- Very large datasets
- High-dimensional data
- Applications requiring fast training/inference
- Real-time clustering tasks

The library can be installed with `pip install faiss-cpu` or `pip install faiss-gpu` depending on hardware availability.

-----

#### Gaussian Mixture Models vs KMeans

Gaussian Mixture Models (GMMs) address several limitations of KMeans clustering:

**Limitations of KMeans:**
1. Only produces globular (circular) clusters
2. Performs hard assignment (each point belongs to exactly one cluster)
3. Only relies on distance, ignoring cluster variance/shape

**GMM Advantages:**
1. Creates flexible cluster shapes (e.g., oval clusters in 2D)
2. Provides probabilistic assignments (soft clustering)
3. Accounts for cluster variance and covariance
4. Better handles clusters with different sizes and densities

**How GMMs Work:**
- Represent data as mixture of multiple Gaussian distributions
- Each Gaussian component corresponds to a cluster
- Learn parameters (mean, covariance, mixing coefficients) via EM algorithm
- Assign probabilities of cluster membership to each point

When to use GMMs over KMeans:
- When clusters have different shapes, sizes, or orientations
- When probabilistic assignments are needed
- When cluster variance is important for interpretation
- When data likely comes from mixture of distributions

GMMs provide a more flexible and statistically sound approach to clustering, though with increased computational complexity.

-----

#### DBSCAN++ vs DBSCAN for Efficient Density-Based Clustering

DBSCAN is an effective density-based clustering algorithm, but its O(n²) worst-case time complexity limits scalability. DBSCAN++ addresses this limitation:

**DBSCAN Limitations:**
- Quadratic time complexity with dataset size
- Prohibitively slow on large datasets (>100k points)
- Excellent for arbitrary-shaped clusters when data size permits

**DBSCAN++ Approach:**
- Based on the observation that density estimates for a subset of points are sufficient
- Process:
  1. Sample m << n points from the dataset (m can be much smaller than n)
  2. Compute density estimates only for this subset
  3. Use these estimates for clustering the entire dataset
- Maintains clustering quality while dramatically reducing computation

**Performance Comparison:**
- 20x faster than standard DBSCAN on 60k data points
- Often produces better clustering scores than standard DBSCAN
- Scales to datasets where original DBSCAN is impractical

DBSCAN++ makes density-based clustering feasible for large datasets while preserving the ability to detect arbitrary-shaped clusters and identify outliers.

-----

#### HDBSCAN vs DBSCAN

HDBSCAN (Hierarchical DBSCAN) enhances DBSCAN by addressing several limitations:

**DBSCAN Limitations:**
1. Assumes uniform density across clusters (controlled by eps parameter)
2. Struggles with varying-density clusters
3. Requires careful parameter tuning
4. Scale variant (results change if data is scaled)

**HDBSCAN Improvements:**
1. Handles varying density clusters automatically
2. Requires fewer parameters (no eps parameter)
3. Scale invariant (same results regardless of data scaling)
4. Explores multiple density scales simultaneously
5. Provides hierarchical clustering structure

**How HDBSCAN Works:**
1. Transforms space based on density estimation
2. Builds minimum spanning tree of transformed space
3. Constructs cluster hierarchy
4. Extracts stable clusters

When to use HDBSCAN:
- Datasets with varying-density clusters
- When cluster counts are unknown
- When minimal parameter tuning is preferred
- When scale invariance is important

HDBSCAN is implemented in the `hdbscan` Python package and offers significant advantages over traditional DBSCAN for most clustering tasks.

-----

### Correlation Analysis

#### Predictive Power Score vs Correlation

Traditional correlation measures like Pearson's have several limitations that the Predictive Power Score (PPS) addresses:

**Correlation Limitations:**
1. Symmetric (corr(A,B) = corr(B,A)) while real-world associations are often asymmetric
2. Only measures linear/monotonic relationships
3. Not designed to measure predictive power
4. Limited to numerical data

**Predictive Power Score (PPS):**
- Asymmetric measure (PPS(A→B) ≠ PPS(B→A))
- Measures predictive power of one feature for another
- Works with categorical and numerical data
- Handles linear and non-linear relationships
- Calculation:
  - For numeric targets: Train Decision Tree Regressor, compare MAE to baseline model
  - For categorical targets: Train Decision Tree Classifier, compare F1 to baseline model

**When to Use Each:**
- Correlation: When interested in general monotonic trends between variables
- PPS: When evaluating feature predictiveness or for feature selection

PPS reveals relationships that correlation might miss, particularly for:
- Non-linear but highly predictive relationships
- Categorical variables
- Asymmetric relationships

The `ppscore` Python package provides an easy implementation of this technique.

-----

#### Dangers of Summary Statistics

Relying solely on summary statistics like correlation coefficients can lead to misleading conclusions:

**The Problem:**
- Summary statistics can mask important patterns in data
- Different datasets can have identical statistics but wildly different structures
- Outliers can dramatically change correlation values

**Example:**
Adding just two outliers to a dataset can change a correlation coefficient from 0.816 to 0.139, completely altering the perceived relationship.

**Solution:**
- Always visualize data alongside statistical measures
- Use tools like pair plots to examine relationships
- Look for patterns that statistics might miss
- Be vigilant for outliers that could distort statistics

The classic example is Anscombe's quartet: four datasets with nearly identical summary statistics but completely different visual patterns. Similar examples include the "Datasaurus Dozen" where drastically different data shapes yield identical statistics.

This reinforces the principle: "Never draw conclusions from summary statistics without visualizing the data."

-----

#### Pearson vs Spearman Correlation

Different correlation measures serve different purposes and have distinct characteristics:

**Pearson Correlation:**
- Measures linear relationship only
- Sensitive to outliers
- Default in many frameworks (e.g., Pandas)
- Underestimates non-linear relationships
- Range: -1 to 1

**Spearman Correlation:**
- Measures monotonic relationship (can be non-linear)
- Based on ranks rather than raw values
- Less sensitive to outliers
- Better for ordinal data
- Range: -1 to 1

**Key Differences:**
- On linear data: Pearson ≈ Spearman
- On non-linear but monotonic data: Spearman > Pearson
- With outliers: Spearman more robust than Pearson

**When to Use Spearman:**
- When relationship might be non-linear
- When data contains outliers
- With ordinal or ranked data
- When monotonicity is more important than linearity

To use Spearman in Pandas: `df.corr(method='spearman')`

-----

#### Correlation with Ordinal Categorical Data

When measuring correlation between ordinal categorical features and continuous features, encoding choice matters:

**The Challenge:**
- Categorical encoding affects Pearson correlation results
- Different encoding schemes can yield different correlation values for the same relationship

**Example:**
T-shirt sizes (S, M, L, XL) correlated with weight:
- Encoding 1: S(1), M(2), L(3), XL(4) → Correlation: 0.61
- Encoding 2: S(1), M(2), L(4), XL(8) → Correlation: 0.75

**Solution: Spearman Correlation**
- Based on ranks, not actual values
- Invariant to monotonic transformations of encoding
- Preserves the original relationship regardless of encoding scheme
- Same correlation value regardless of ordinal encoding

This property makes Spearman correlation particularly valuable when working with:
- Ordinal categorical variables
- Variables requiring transformation
- Any data where the exact numeric values are less important than their order

-----

### Model Monitoring and Drift Detection

#### Detecting Covariate Shift

Covariate shift occurs when the distribution of features changes over time while the relationship between features and target remains the same:

**Types of Covariate Shift:**
1. **Univariate Shift**: Distribution of individual features changes
2. **Multivariate Covariate Shift (MCS)**: Joint distribution changes while individual distributions remain the same

**Detecting Univariate Shift:**
- Compare feature distributions (training vs. production)
- Methods:
  - Visual comparison of distributions
  - Compare summary statistics
  - Statistical tests (KS test, etc.)
  - Distribution distance measures (Bhattacharyya, etc.)

**Detecting Multivariate Shift:**
1. **PCA Visualization**: For 2-3 features at a time
2. **Data Reconstruction**:
   - Train autoencoder on original training data
   - Apply to new data and measure reconstruction error
   - High error indicates distribution shift
   - Process:
     1. Establish baseline reconstruction error on post-training data
     2. Regularly check reconstruction error on new data
     3. Compare to baseline to identify shifts

**Implementation Considerations:**
- Covariate shift typically happens gradually
- Establish monitoring windows (e.g., weekly checks)
- Combine with performance metrics when available
- Consider gathering user feedback as proxy for performance

Early detection of covariate shift allows for timely model updates before performance significantly degrades.

-----

#### Using Proxy-Labeling to Identify Drift

When true labels aren't immediately available, proxy-labeling techniques can help detect feature drift:

**The Challenge:**
- Model performance degrades due to changing feature distributions
- True labels often unavailable or delayed in production
- Need to detect drift without waiting for labels

**Proxy-Labeling Solution:**
1. Combine old (training) dataset and current (production) dataset
2. Add binary label: "old" vs "current" to each dataset
3. Merge datasets and train a classification model
4. Measure feature importance for distinguishing between datasets
5. Features with high importance are likely drifting

**Why It Works:**
- If features can reliably distinguish between datasets, their distribution has changed
- No need for true outcome labels
- Provides early warning of potential performance issues

**Implementation Insights:**
- Use interpretable models (e.g., Random Forest) for feature importance
- Can be automated as part of regular monitoring
- Particularly valuable when labels are delayed (e.g., fraud detection where true labels arrive weeks later)

This technique provides actionable insights about which features are drifting, allowing targeted remediation strategies.

-----

### kNN Algorithms and Optimizations

#### kNN in Imbalanced Classification

The k-Nearest Neighbors algorithm is highly sensitive to the parameter k, particularly with imbalanced data:

**The Problem:**
- Standard kNN uses majority voting
- With imbalanced classes, majority class dominates predictions
- Minority classes may never be predicted regardless of proximity

**Example:**
With k=7 and a class having fewer than 4 samples, that class can never be predicted even if a query point is extremely close to it.

**Solutions:**

1. **Distance-Weighted kNN**:
   - Weights neighbors by their distance
   - Closer neighbors have more influence on prediction
   - Formula: weight = 1/distance²
   - Implementation: `KNeighborsClassifier(weights='distance')` in sklearn
   - More robust to imbalance than standard kNN

2. **Dynamic k Parameter**:
   - For each test instance:
     1. Find initial k nearest neighbors
     2. Identify classes represented in these neighbors
     3. Update k to min(total training samples of represented classes)
     4. Use majority voting on first k' neighbors only
   - Rationale: Adjust k based on class representation
   - Requires custom implementation

These approaches significantly improve kNN performance on imbalanced datasets by preventing majority class dominance while maintaining the intuitive nearest-neighbor concept.

-----

#### Approximate Nearest Neighbor Search with Inverted File Index

Traditional kNN performs exhaustive search, comparing each query point to all database points. This becomes prohibitively slow for large datasets:

**The Challenge:**
- kNN has O(nd) search complexity (n = data points, d = dimensions)
- Real-time requirements often incompatible with large datasets
- Need faster search without losing too much accuracy

**Inverted File Index (IVF) Solution:**

1. **Indexing Phase:**
   - Partition dataset using clustering (e.g., k-means)
   - Each partition has a centroid
   - Each data point belongs to one partition (nearest centroid)
   - Each centroid maintains list of its points

2. **Search Phase:**
   - Find closest centroid to query point
   - Search only points in that partition
   - Time complexity: O(k + n/k) where k = number of partitions

**Performance Example:**
For 10M data points with 100 partitions:
- Standard kNN: O(10M) operations
- IVF: O(100 + 100K) = O(100K) operations
- ~100x speedup

**Accuracy Tradeoff:**
- May miss nearest neighbors in neighboring partitions
- Acceptable tradeoff for many applications
- Can query multiple nearby partitions for higher accuracy

This approach enables kNN on massive datasets with minimal accuracy loss, making it practical for real-time applications like recommendation systems and similarity search.

-----

### Kernel Methods

#### Kernel Trick Explained

The kernel trick is a fundamental concept in machine learning that allows algorithms to operate in high-dimensional spaces without explicitly computing coordinates in that space:

**The Concept:**
- A kernel function K(x,y) computes the dot product between two vectors in some high-dimensional space without actually mapping to that space
- Mathematically: K(x,y) = ⟨φ(x), φ(y)⟩ where φ is the mapping function

**Example: Polynomial Kernel**
For K(x,y) = (x·y + 1)²:

Given 2D vectors x = [x₁, x₂] and y = [y₁, y₂]:
1. Expand K(x,y) = (x₁y₁ + x₂y₂ + 1)²
2. = (x₁y₁)² + (x₂y₂)² + 2(x₁y₁)(x₂y₂) + 2x₁y₁ + 2x₂y₂ + 1
3. This equals the dot product of x and y mapped to 6D space:
   φ(x) = [x₁², √2x₁x₂, x₂², √2x₁, √2x₂, 1]
   φ(y) = [y₁², √2y₁y₂, y₂², √2y₁, √2y₂, 1]

**Key Insight:**
The kernel computes this 6D dot product while only working with the original 2D vectors.

**Benefits:**
- Enables non-linear decision boundaries with linear algorithms
- Computationally efficient
- Allows working in potentially infinite-dimensional spaces
- Particularly powerful for SVM, PCA, and other algorithms

Common kernels include polynomial, RBF (Gaussian), sigmoid, and linear. The choice of kernel determines the type of non-linear transformations applied to the data.

-----

#### Radial Basis Function (RBF) Kernel

The Radial Basis Function kernel is one of the most widely used kernels in machine learning, serving as the default in many implementations including sklearn's SVC:

**Mathematical Expression:**
RBF Kernel: K(x,y) = exp(-γ ||x-y||²)

**Feature Mapping Exploration:**
For a 1D input, the RBF kernel implicitly maps to an infinite-dimensional space:

1. Expand the kernel:
   K(x,y) = exp(-γ(x-y)²)
   = exp(-γx²) · exp(2γxy) · exp(-γy²)

2. Using the Taylor expansion of exp(2γxy):
   exp(2γxy) = 1 + 2γxy + (2γxy)²/2! + (2γxy)³/3! + ...

3. The equivalent mapping φ is:
   φ(x) = exp(-γx²) · [1, √2γx, √2γ²x²/√2!, √2γ³x³/√3!, ...]

This reveals that RBF maps points to an infinite-dimensional space, explaining its flexibility.

**Properties of RBF Kernel:**
- Decreases as points move apart (locality property)
- Always between 0 and 1
- Equal to 1 only when x=y
- Can model highly complex decision boundaries
- Particularly effective when relationship between features is non-linear
- γ parameter controls the influence radius (smaller γ = larger radius)

The infinite-dimensional mapping explains why RBF kernels can model virtually any smooth function and why they're so effective for complex classification tasks.

-----

### Missing Data Analysis

#### Types of Missing Data

Understanding why data is missing is crucial before applying imputation techniques. Missing data falls into three categories:

1. **Missing Completely At Random (MCAR)**:
   - Data missingness has no relation to any variables
   - No discernible pattern in missingness
   - Example: Survey participants randomly skipping questions
   - Rare in real-world datasets
   - Suitable for simple imputation techniques

2. **Missing At Random (MAR)**:
   - Missingness of one feature can be explained by other observed features
   - Pattern exists but can be accounted for using available data
   - Example: Higher-income respondents less likely to disclose income, but income correlates with education (which is observed)
   - More common in practice
   - Suitable for model-based imputation (kNN, MissForest)

3. **Missing Not At Random (MNAR)**:
   - Missingness related to the missing value itself or unobserved variables
   - Example: People with high stress levels less likely to report stress
   - Most challenging type
   - Difficult to address without additional data collection
   - Best handled by adding missingness indicators and domain expertise

**Approach to Missing Data:**
1. First understand the missingness mechanism (talk to domain experts, data engineers)
2. Analyze patterns in missing data
3. Then select appropriate imputation technique based on missingness type
4. For MNAR, consider adding binary indicators for missingness

This systematic approach prevents introducing bias during imputation and improves model performance.

-----

#### MissForest and kNN Imputation

For data Missing At Random (MAR), two powerful imputation techniques are kNN Imputation and MissForest:

**kNN Imputation:**
1. For each row with missing values:
   - Find k nearest neighbors using non-missing features
   - Impute missing values using corresponding values from neighbors
2. Advantages:
   - Preserves data relationships
   - Handles multiple missing values
   - Maintains feature distributions
3. Limitations:
   - Computationally expensive for large datasets
   - Requires feature scaling
   - Struggles with categorical features

**MissForest:**
1. Process:
   - Initially impute missing values with mean/median/mode
   - For each feature with missing values:
     - Train Random Forest to predict it using other features
     - Impute only originally missing values with predictions
   - Repeat until convergence
2. For multiple missing features:
   - Impute in order of increasing missingness
   - Features with fewer missing values first
3. Advantages:
   - Handles mixed data types naturally
   - Captures non-linear relationships
   - Preserves feature distributions
   - More efficient than kNN for high-dimensional data
   - No feature scaling required

**Comparison to Simple Imputation:**
Both methods preserve summary statistics and distributions better than mean/median imputation, which can distort distributions and relationships between variables.

The choice between kNN and MissForest depends on dataset size, dimensionality, and computational resources. MissForest generally performs better for complex relationships but requires more computation time.

-----
