# Steel Industry Energy Consumption - Analysis and Modeling

## Project Overview
This project analyzes the energy consumption patterns of a steel industry facility. The goal is to perform Exploratory Data Analysis (EDA) to uncover insights and build baseline machine learning models to classify the Load_Type (Light, Medium, or Maximum Load) based on electrical parameters.

## Dataset Information
The dataset (Week 2 (DataSet).xlsx) contains continuous energy consumption data recorded every 15 minutes over a year. 
* *Target Variable:* Load_Type (Categorical: Light_Load, Medium_Load, Maximum_Load)
* *Features:* Includes parameters like Usage (kWh), Reactive Power (kVarh), Power Factor, CO2 emissions, and temporal features (Day_of_week, WeekStatus).

## Environment Setup
1. Clone this repository.
2. Create a virtual environment (optional but recommended).
3. Install the required dependencies using:
   pip install -r requirements.txt

## Feature Engineering Steps
* Dropped the date column as continuous time-series modeling is outside the current scope.
* Encoded categorical temporal features (WeekStatus, Day_of_week) using One-Hot Encoding.
* Encoded the target variable (Load_Type) using Label Encoding.
* Scaled numerical features using Standard Scaler to ensure uniform magnitude across electrical parameters.

## EDA Findings
* *Class Imbalance:* Light_Load is the most frequent occurrence, followed by Medium_Load and Maximum_Load.
* *Correlations:* High correlations exist between Active Power (Usage_kWh) and CO2 emissions.
* *Temporal Patterns:* Energy consumption varies significantly based on whether it is a weekday or weekend.

## Model Training Process
Baseline models were trained using an 80-20 train-test split. The essential models applied include:
1. *Logistic Regression:* A linear baseline.
2. *K-Nearest Neighbors (KNN):* A non-parametric distance-based classifier.
3. *Random Forest Classifier:* An ensemble tree-based model.

## Results and Conclusions
* *Random Forest* typically outperforms the other baseline models due to its ability to handle non-linear relationships and interactions between continuous electrical features.
* *KNN* also serves as a strong baseline for this dataset given the localized clustering of similar load types.
