# Sendy Logistics Challenge - ML Prediction
This project applies a data-driven approach to smart energy supply scheduling, leveraging historical energy data to predict future usage and create cost-efficient energy strategies for sustainable telecom networks.

## Table of Contents
- [Project Overview](#project-overview)
- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
- [Machine Learning](#machine-learning)
    - [Data Loading and Exploration](#data-loading-and-exploration)
    - [Data Merging](#data-merging)
    - [Data Cleaning](#data-cleaning)
    - [Feature Engineering](#feature-engineering)
    - [Correlation Analysis](#correlation-analysis)
    - [Data Preparation for Modeling](#data-preparation-for-modeling)
    - [Model Development](#model-development)
    - [Model Evaluation](#model-evaluation)
    - [Predictions and Submission Preparation](#predictions-and-submission-preparation)
    - [Visualizations](#visualizations)

## Project Overview
The project applies a data-driven approach to smart energy supply scheduling, leveraging historical energy data to predict future usage and create cost-efficient energy strategies for sustainable telecom networks.

## Problem Statement
The problem statement for this project involves addressing the challenge of optimizing energy usage across telecom sites powered by multiple sources: grid, diesel, and solar energy. The task requires developing a machine-learning model capable of predicting the optimal energy source at each time step while minimizing overall costs. Additionally, the solution must maintain battery capacity above a set threshold to ensure continuous operation. The problem is complex due to the fluctuating availability of renewable energy and varying energy costs, requiring a robust strategy for cost-effective energy allocation.

## Dataset
The [dataset](https://zindi.africa/competitions/sendy-logistics-challenge/data) used in the project includes energy usage data across multiple telecom sites, each powered by grid, diesel, and solar energy sources. It contains variables such as energy output (kWh), solar zenith angle, relative humidity, battery charge and discharge coefficients, and grid outage plans. Additionally, site-specific attributes like battery capacity, rated voltage, and diesel power output are included. The dataset spans various time periods, making it well-suited for predicting energy consumption patterns and optimizing the energy mix for minimizing operational costs while maintaining battery health.

## Machine Learning
### Data Loading and Exploration
- Load datasets (Train.csv, Test.csv, Riders.csv, etc.) using pandas.
- Display the first few rows and the structure of the datasets to understand the data.

### Data Merging
- Merge the train_df and test_df with the riders_df on the 'Rider Id' column to incorporate rider-specific features.

### Data Cleaning
- Handle missing values by dropping unnecessary columns (e.g., 'Precipitation in millimeters') and filling NaN values in the 'Temperature' column.
- Convert relevant columns to datetime format and extract features (e.g., hour of the day).

### Feature Engineering
- Create new features such as Placement_hour, Pickup_hour, and Time_diff_Pickup_to_Arrival in both training and test datasets.

### Correlation Analysis
- Calculate and interpret correlations between various features and the target variable (Time from Pickup to Arrival).
- Visualize the correlation matrix and key distributions using heatmaps and histograms.

### Data Preparation for Modeling
- Define features (X) and target (y) for the model.
- Set up preprocessing pipelines for numeric (scaling) and categorical (one-hot encoding) features using ColumnTransformer.

### Model Development
- Use a Pipeline to combine preprocessing and model fitting.
- Train a RandomForestRegressor on the training set, splitting data into training and validation subsets.

### Model Evaluation
- Evaluate model performance using Root Mean Squared Error (RMSE) on the validation set.

### Predictions and Submission Preparation
- Make predictions on the test set.
- Create a submission file containing the order number and predicted arrival times, then save it as a CSV file.

### Visualizations
- Generate visualizations such as swarm plots and scatter plots to explore relationships in the data and analyze model performance.
