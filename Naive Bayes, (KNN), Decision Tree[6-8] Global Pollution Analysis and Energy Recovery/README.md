# Global Pollution Analysis and Energy Recovery Prediction

# Detailed Project Summary

This project analyzes global pollution data to examine the relationship between environmental indicators and energy recovery. The study focuses on two predictive tasks:

The goal is to classify countries into different pollution severity categories (Low, Medium, High) based on pollution levels, energy consumption, and other environmental factors.

The project includes data preprocessing, exploratory analysis, feature engineering, regression modeling, classification modeling, and performance comparison.

# Dataset Description

Dataset Name: Global_Pollution_Analysis.csv
Shape: 200 rows × 13 columns

The dataset contains country-level environmental and energy indicators across multiple years.

Key Variables

Country

Year

Air_Pollution_Index

Water_Pollution_Index

Soil_Pollution_Index

CO2_Emissions (in MT)

Industrial_Waste (in tons)

Plastic_Waste_Produced (in tons)

Population (in millions)

Renewable_Energy (%)

GDP_Per_Capita (in USD)

Energy_Consumption_Per_Capita (in MWh)

Energy_Recovered (in GWh) – Target variable for regression

The dataset does not contain missing values.

# Data Preprocessing Steps

-> Data Loading
The dataset was imported using Pandas.

-> Missing Value Check
All columns were checked for null values. No missing values were found.

-> Encoding Categorical Variable (Country)
The Country column had 175 unique values (high cardinality).
Instead of one-hot encoding, frequency encoding was applied to avoid excessive feature expansion.

-> Feature Scaling
StandardScaler was used to normalize numerical features before model training.

->Pollution Severity Creation (for Classification)
Pollution severity categories were created using quantile-based binning:

Bottom 33% → Low

Middle 33% → Medium

Top 33% → High
This ensured balanced class distribution.

->Train-Test Split
Data was split into 80% training and 20% testing sets.

#  Models Implemented

Three classification models were trained and evaluated:

1. Decision Tree Classifier

Accuracy: 80.0%
Precision: 0.792929
Recall: 0.819444
F1 Score: 0.0.798627

This model achieved the highest overall performance.

2. K-Nearest Neighbors (KNN)

Accuracy: 50.0%
Precision: 0.521351
Recall: 0.605556
F1 Score: 0.484444

Strong recall performance with slightly lower precision compared to Decision Tree.

3. Multinomial Naive Bayes

Accuracy: 35.5%
Precision: 0.292581
Recall: 0.486111
F1 Score: 0.329025



Objective: Classify pollution levels into Low, Medium, and High.

Evaluation Metrics:

Accuracy: 0.80

Balanced precision and recall across all classes

F1-score approximately 0.93 (macro average)

Interpretation:

The model achieved high classification accuracy.

Class distribution was balanced due to quantile-based binning.

Pollution severity levels are distinguishable using environmental indicators.

Conclusion: Logistic regression effectively classifies pollution severity.

# Model Comparison
Model	Performance	Interpretation
Linear Regression	Poor (Negative R²)	Weak linear dependency
Logistic Regression	Strong (92.5% Accuracy)	Effective classification

# Overall Comparison:

The regression model struggled due to weak linear correlations.

The classification model performed significantly better.

Pollution severity categories are easier to distinguish than predicting exact energy recovery values.

# Actionable Insights

Industrial waste shows a negative relationship with energy recovery, indicating potential inefficiencies in waste-to-energy systems.

Pollution indicators alone are insufficient for accurately predicting energy recovery.

Countries with high pollution but low energy recovery should be prioritized for technological upgrades.

Increasing renewable energy adoption may indirectly improve energy recovery mechanisms.

Nonlinear models such as Random Forest or Gradient Boosting may improve predictive performance.

