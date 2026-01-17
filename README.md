# Weather-to-Wildfire-Prediction
🌲 A Chained Model for Weather Forecasting and Wildfire Risk Prediction
Data Science Course Project (Apr 2025 – Jun 2025) > A two-stage predictive pipeline that forecasts future meteorological conditions in the Gyeongbuk region and estimates subsequent wildfire probabilities based on climate change scenarios.

📑 Project Overview
With the increasing frequency of large-scale wildfires due to global warming, there is a critical need for proactive disaster management. This project focuses on the Gyeongsangbuk-do (Gyeongbuk) region, which has recently suffered record-breaking damage. We developed a chained machine learning architecture that:

Predicts future climate variables (Temperature, Wind Speed, Precipitation).

Assesses wildfire risk levels using the forecasted weather data.

🏗️ System Architecture: The Chained Model
The system consists of two distinct but interconnected models linked by an External Function that handles data transformation and seasonal encoding.

Model 1 (Weather Forecaster): Learns long-term climatic patterns from historical data (1938–2025) to predict weather variables for a specific year and month.

Model 2 (Wildfire Risk Predictor): Analyzes the correlation between meteorological conditions and fire occurrences to output a probability score.

External Function: Converts "Month" inputs into "Season" categories and ensures the feature alignment between the two models.

📊 Dataset & Feature Engineering
1. Data Sources
Regional Weather Data: KMA Weather Data Service (Historical monthly data for Gyeongbuk, South Korea).

Wildfire Incident Data: Zenodo Open Dataset (Global wildfire records and associated climate metrics).

2. Key Preprocessing & Engineering
Time-Series Features: Created LINEAR_TEMP_TREND and YEAR_SQUARED to capture both linear and non-linear climate change progression.

Data Harmonization: Standardized units (Fahrenheit to Celsius, inches to mm) and handled missing values using mean imputation based on regional averages.

Feature Scaling: Applied normalization to ensure convergence in the stacking ensemble.

🤖 Modeling & Evaluation
Model 1: Climate Forecasting (Regression)
Algorithm: Stacking Regressor

Base Learners: CatBoost (for non-linear patterns) & Linear Regression (for trend extrapolation).

Meta-Learner: RidgeCV.

Performance: Achieved high R² scores for temperature variables, successfully capturing the warming trend in the Gyeongbuk area.

Model 2: Wildfire Risk Prediction (Classification)
Algorithm: Random Forest Classifier

Optimization: Hyperparameter tuning via Bayesian Optimization (Optuna) and Grid Search.

Metric: Optimized using a custom weighted score of ROC AUC and PR AUC to account for the imbalanced nature of wildfire occurrence data.

📈 Key Findings
Long-term Simulation: Projected wildfire risk for 2030 and 2080 suggests a significant upward trend in fire probability during the spring and autumn months, directly correlated with rising average temperatures.

Regional Specificity: The model successfully localized global wildfire patterns to the specific geographic and climatic characteristics of the Gyeongbuk region.

🛠️ Tech Stack
Environment: Python (Jupyter Notebook)

ML Frameworks: Scikit-learn, CatBoost, Optuna

Data Analysis: Pandas, NumPy

Visualization: Matplotlib, Seaborn

👥 Contributors (Team 2)
Gaeun Bang, Gyurie Baek, Jiwon Lee, Ahhyeon Jeong
