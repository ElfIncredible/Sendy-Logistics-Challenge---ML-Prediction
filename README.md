# Sendy Logistics Challenge - ML Prediction
This challenge not only aims to enhance logistical efficiency but also seeks to create more accessible and affordable delivery solutions for businesses in Africa. A successful submission will significantly contribute to improving logistics in the region.

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
- [Impact](#impact)

## Project Overview
The Sendy Logistics Challenge focuses on predicting the estimated time of arrival (ETA) for motorbike deliveries in Nairobi. The aim is to improve the efficiency of logistics in Sub-Saharan Africa, where high transportation costs can significantly impact the economy.

**Overview**
- **Purpose:** Predict delivery times from the moment a driver picks up a package until it reaches the destination.
- **Goal:** Enhance customer communication, improve service reliability, and achieve cost savings through better resource management.

## Problem Statement
The problem statement for this project involves addressing the challenge of optimizing energy usage across telecom sites powered by multiple sources: grid, diesel, and solar energy. The task requires developing a machine-learning model capable of predicting the optimal energy source at each time step while minimizing overall costs. Additionally, the solution must maintain battery capacity above a set threshold to ensure continuous operation. The problem is complex due to the fluctuating availability of renewable energy and varying energy costs, requiring a robust strategy for cost-effective energy allocation.

## Dataset
**Data Description**
- **Training Dataset:** A subset of over 20,000 direct orders for motorbike deliveries, fully anonymized with weather data included.
- **Files Provided:**
    - Train.csv: Data for training your model.
    - Test.csv: Data for testing your model.
    - Riders.csv: Information about unique riders, including their performance metrics.
    - VariableDefinitions.csv: Definitions for the variables used in the datasets.

**Key Variables in Datasets**
- **Order Details:**
    - Order No: Unique identifier for each order.
    - User Id: Unique identifier for each customer.
    - Vehicle Type: Currently limited to bikes.
    - Other features relevant to the delivery context, such as pickup and drop-off locations, times, and rider metrics.

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

## Impact
**1. Operational Efficiency**
- _Insights into Delivery Dynamics:_ By analyzing correlations between factors like distance, temperature, rider ratings, and delivery times, the project helps identify inefficiencies in the delivery process. For example, weak correlations between distance and delivery times suggest that factors other than distance, such as traffic or route optimization, may play a more significant role in delivery delays.
- _Data-Driven Decision Making:_ The insights gained from this analysis can help logistics companies like Sendy optimize rider assignments and improve delivery routing, reducing delays and enhancing efficiency.

**2. Improving Rider Performance**
- _Understanding Rider Efficiency:_ Investigating correlations between rider-specific factors (e.g., number of orders, average rating, and age) and delivery time reveals minimal influence of these variables on delivery efficiency. This insight suggests that companies should focus on external factors (like traffic or platform type) rather than only rider performance for improving delivery times.
- _Training and Incentives:_ Although the correlation is weak, riders with higher ratings tended to perform slightly better in terms of quicker deliveries. This can guide the design of training programs or incentive structures for riders to improve their skills and efficiency.

**3. Customer Experience**
- _Faster Delivery Times:_ Identifying peak hours (through the heatmap) and vehicle type correlations with delivery times can help Sendy optimize scheduling, allowing for quicker deliveries during rush hours, thereby improving customer satisfaction.
- _Reliable Deliveries:_ By addressing factors that contribute to delays, the project supports more predictable and reliable deliveries, leading to better customer trust in the service.

**4. Scalability and Future Applications**
- _Scalable Solutions:_ The methodology applied in this project can be scaled and adapted to different logistics challenges in other cities or for different companies facing similar delivery issues.
- _Predictive Modeling Potential:_ Beyond correlation analysis, predictive models could be developed to forecast delivery times based on specific features (e.g., distance, rider performance, time of day). This could help Sendy anticipate delays and proactively address them.

**5. Business Growth and Cost Savings**
- _Reduced Delivery Costs:_ Optimizing routes, reducing delays, and improving efficiency can reduce operational costs for Sendy by cutting fuel consumption, labor costs, and minimizing downtime.
- _Increased Customer Retention:_ Improved delivery experiences lead to higher customer satisfaction and retention, contributing to long-term business growth.

In summary, this project’s impact is far-reaching, offering insights that can drive operational improvements, enhance rider performance, improve customer satisfaction, and contribute to scalable, data-driven strategies for optimizing logistics processes.
