# Anticipating Building Energy Consumption and Emissions

## Overview

This repository contains the code and analysis for predicting CO₂ emissions and total energy consumption of non-residential buildings in Seattle using structural and contextual features. The project aims to support the City of Seattle’s goal of becoming carbon-neutral by 2050 by providing scalable predictive models that reduce the need for costly and time-consuming annual energy audits.

## Project Structure

- `Notebook_exploration.ipynb`  
  Exploratory Data Analysis (EDA) to understand feature distributions, missing values, correlations, and potential data leakage.

- `Notebook_prediction_consumption.ipynb`  
  Model development and evaluation for predicting total energy consumption. Includes data preprocessing, feature engineering, model training, hyperparameter tuning (via cross-validation), and performance comparison across at least four algorithm families (e.g., ElasticNet, SVM, Gradient Boosting, Random Forest).

- `Notebook_prediction_emission.ipynb`  
  Model development and evaluation for predicting CO₂ emissions. Explores the impact of including the ENERGY STAR Score as an additional feature and compares model performances.

- `Presentation_of_analysis.pptx`  
  Slide deck summarizing key findings, methodology, and recommendations for integrating the predictive models into the City of Seattle’s workflow.

## Data

The project uses the Building Energy Benchmarking dataset provided by the City of Seattle, which contains detailed 2015–present energy use and emissions data for non-residential buildings.  

**Source:** [Seattle Building Energy Benchmarking Data (2015–Present)](https://data.seattle.gov/Built-Environment/Building-Energy-Benchmarking-Data-2015-Present/teqw-tu6e/about_data)

**Key Features:**
- Building size (e.g., gross floor area)
- Primary use type (e.g., office, hotel, retail)
- Year built
- Location (address, neighborhood)
- ENERGY STAR Score (when available)
- Annual energy consumption (kBtu)
- Annual CO₂ emissions (metric tons)

## Methodology

1. **Feature Engineering:**  
   - Extract structural features (size, year built, use type).  
   - Geocode addresses to derive latitude/longitude and neighborhood-level indicators.  
   - Compute transformations (log-scaling, normalization) to handle skewed distributions.

2. **Model Training:**  
   - Split data into training and hold-out test sets to prevent data leakage.  
   - Evaluate at least four different model families: ElasticNet, Support Vector Machines, Gradient Boosting, Random Forest.  
   - Perform grid search with k-fold cross-validation for hyperparameter tuning.

3. **Evaluation:**  
   - Compare models using appropriate regression metrics (MAE, RMSE, R²).  
   - Analyze the incremental value of including the ENERGY STAR Score for emission predictions.

4. **Results & Recommendations:**  
   - Summarize model performance and identify the best-performing approach.  
   - Discuss potential deployment strategies and data requirements for future buildings.

