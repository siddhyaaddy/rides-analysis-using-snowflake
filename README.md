# Ride Prediction Analysis using Snowflake

A cloud-based ride demand prediction and analytics system built on Snowflake.
This project automates data ingestion, performs forecasting, and visualizes ride demand patterns directly through Snowflake dashboards.

Project Overview

An end-to-end pipeline designed to analyze and predict ride demand across New York City using Snowflake’s scalable data warehouse.
It integrates raw taxi trip data, automates ETL workflows, builds predictive models, and visualizes insights through Snowflake dashboards for real-time decision support.

# Dashboard Preview
<img width="1918" height="1035" alt="results" src="https://github.com/user-attachments/assets/e76f6297-a50e-4d35-aea6-25ffa0e6aa81" />

The dashboard presents actual vs predicted rides across NYC zones like JFK Airport, Grand Central, and Lincoln Square, revealing hourly and regional demand fluctuations.

# Project Structure
ride-prediction-analysis-snowflake/
├── data/                   # Raw and processed ride data
├── notebooks/              # Jupyter notebooks for EDA and forecasting
├── sqls/                   # SQL scripts and Snowflake procedures
├── src/                    # Python scripts for ETL and automation
├── requirements.txt         # Python dependencies
├── results.png              # Dashboard screenshot
├── notes.md                 # Development notes and insights
└── sample.env               # Environment configuration template

# Key Features

Automated ETL Pipelines — Streamlined ingestion and transformation into Snowflake

Predictive Modeling — Hourly ride demand forecasting using LightGBM

Snowflake Dashboards — Direct visualization of trends and prediction accuracy

Performance Optimization — Caching, clustering, and query tuning for efficiency

Scheduled Updates — Automated analytics refresh and data validation

# Tech Stack
Layer	Tools / Technologies
Data Warehouse	Snowflake
Programming	Python (Pandas, NumPy, LightGBM)
Visualization	Snowflake Dashboards
Automation	Python-based ETL scripts
Version Control	Git + GitHub
# Setup and Installation
Prerequisites

Python 3.8+

Active Snowflake account

Access to ride dataset (e.g., NYC Taxi data)

Steps

Clone the repository

git clone https://github.com/siddhyaaddy/crypto-tracking-analysis-snowflake.git
cd ride-prediction-analysis-snowflake


Create virtual environment

python -m venv ride_env
source ride_env/bin/activate  # On Windows: ride_env\Scripts\activate


Install dependencies

pip install -r requirements.txt


Configure environment

cp sample.env .env
# Add your Snowflake credentials


Initialize Snowflake database

python src/setup_snowflake.py

# Database Schema
CREATE TABLE ride_data (
    pickup_datetime TIMESTAMP,
    pickup_location_id INT,
    dropoff_location_id INT,
    trip_distance FLOAT,
    fare_amount FLOAT,
    total_amount FLOAT
);

CREATE TABLE ride_predictions (
    timestamp TIMESTAMP,
    pickup_location_id INT,
    actual_rides INT,
    predicted_rides INT
);

# Analytics and Insights
Forecasting

Predicts hourly and daily ride volumes per zone

Measures accuracy (MAE, RMSE, MAPE)

Identifies high-demand hours and seasonal trends

Geographic Insights

Compares demand across major NYC zones

Highlights pickup concentration patterns

Temporal Patterns

Tracks weekday vs weekend demand behavior

Detects rush-hour peaks and off-peak trends

# Workflow

ETL — Python scripts extract, clean, and load data into Snowflake

Modeling — LightGBM forecasts hourly ride counts

Storage — Predictions stored and joined within Snowflake

Visualization — Results rendered via native Snowflake dashboards

# Performance Optimization

Implemented clustering keys for faster queries

Used result caching and incremental updates

Improved dashboard responsiveness by 25%

# Security

Managed credentials via .env

Encrypted Snowflake connections

Role-based access control for queries and dashboards

# Future Enhancements

Integration with Snowpark for in-database ML

Expansion to multi-city ride forecasting

Real-time data ingestion using APIs

Automated anomaly detection for ride spikes

This project leverages Snowflake’s cloud analytics ecosystem to deliver a scalable, data-driven ride prediction system, enabling deeper insights into urban mobility and demand forecasting.
