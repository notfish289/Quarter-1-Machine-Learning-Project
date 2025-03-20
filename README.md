**Predicting Driver Fault in Traffic Incidents**

**Project Goal**

The objective of this project is to develop a machine learning model that predicts whether a driver was at fault in a traffic incident using the Montgomery County Crash Reporting Incidents dataset. By analyzing various factors such as driver behavior, environmental conditions, and crash characteristics, the model aims to identify patterns and indicators that contribute to fault determination. The insights from this project could be valuable for law enforcement agencies, insurance companies, and urban planners to better understand the dynamics of traffic incidents and reduce preventable accidents.

**Dataset Description**

The dataset consists of approximately 180,000 instances with 39 attributes (excluding the class label). Key attributes include:

Crash Details: Date/Time, Route Type, Road Name, Collision Type, Weather, Surface Condition, Light Conditions, Traffic Control.

Driver & Vehicle Information: Driver Substance Abuse, Driver Distracted By, Vehicle Damage Extent, Vehicle Body Type, Speed Limit, Vehicle Movement.

Incident Outcomes: Injury Severity, Driver At Fault (class label).

**Data Preprocessing**

Handling Missing and Improperly Formatted Data

Removed sparsely populated or redundant attributes: Examples include 'Off Road Description' (>90% missing), 'Circumstance' (redundant with 'Surface Condition'), and 'Location' (redundant with 'Latitude' & 'Longitude').

Fixed formatting issues: Removed problematic newline characters and replaced quotation marks that interfered with WEKA processing.

Discretized numerical attributes: 'Crash Date/Time' converted to minutes and binned into categories.

Filled missing values: Used WEKA’s ‘ReplaceMissingValues’ to handle attributes with missing data.

**Train-Test Split**

Stratified 80-20 split: Ensured equal distribution of the class label ('At Fault') across training and test sets.

**Feature Selection**

To enhance model performance, we used multiple attribute selection methods:

Correlation-Based Feature Selection

Information Gain-Based Selection

OneR Attribute Evaluation

Gain Ratio Evaluation

Self-Selected Attributes (union of selected features from all methods)

The selected attributes primarily included:

Driver Factors: 'Driver Distracted By', 'Driver Substance Abuse'

Vehicle Factors: 'Vehicle First Impact Location', 'Vehicle Movement', 'Vehicle Damage Extent'

Environmental Factors: 'Speed Limit', 'Traffic Control', 'Light Conditions'

Incident Outcomes: 'Injury Severity', 'Collision Type'

**Model Implementation**

We trained and evaluated the following models:

J48 Decision Tree

Naive Bayes

OneR (One Rule Classifier)

Random Tree

Performance Metrics

Accuracy: Selected as the primary performance metric due to minimal class imbalance (56% yes, 44% no).

Additional Evaluation: Precision, recall, and confusion matrices were used to assess model performance.

**Results & Insights**

Performance results were compared across different feature selection methods for each model. The best-performing model was determined based on accuracy and consistency across multiple datasets.
