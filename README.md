# Nba-Playoffs-Predictor
Predicting NBA Playoff teams using machine learning and historical statistical analysis.

# NBA Playoff Prediction Using Machine Learning

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Pandas](https://img.shields.io/badge/Library-Pandas-150458)
![Status](https://img.shields.io/badge/Status-Complete-green)

**Authors:** Bryce Myers & Brock Olson

## Overview
This project predicts whether an NBA team will qualify for the playoffs based on regular-season team statistics. Data is collected programmatically through an NBA statistics API and used to train supervised machine learning models that identify which factors are most predictive of postseason success.

The project demonstrates an end-to-end data science workflow, utilizing a **Medallion Architecture** (Bronze/Silver/Gold) for data ingestion, cleaning, feature engineering, and modeling.

## Motivation
NBA organizations make high-stakes decisions based on player and team performance data. Understanding which statistical factors contribute most to playoff qualification can inform roster construction, strategic planning, and resource allocation. This project aims to highlight how data-driven methods can support these decisions.

## Data
- **Source:** NBA statistics API.
- **Unit of analysis:** Team-season.
- **Features include:**
  - **Offensive metrics:** Points per game, shooting percentages, assists.
  - **Defensive metrics:** Opponent points, steals, blocks, defensive rating.
  - **Advanced metrics:** Efficiency statistics and pace.
- **Target variable:** Playoff qualification (binary).

## Methods
- **Ingestion:** Automated API requests using `requests` (Bronze Layer).
- **Processing:** Data cleaning, null handling, and feature engineering using `pandas` (Silver Layer).
- **Modeling:**
  - **Logistic Regression:** Used as a baseline for interpretability.
  - **Random Forest Classifier:** Used to capture nonlinear relationships and analyze feature importance.
- **Evaluation:** Models are evaluated using Accuracy and Cross-Validation scores.

## Key Findings
Preliminary results indicate that **defensive metrics**—such as Defensive Rating and Opponent Points Per Game—are among the strongest predictors of playoff qualification. These findings align with prior academic research on NBA team success and suggest that while offense sells tickets, defense significantly influences postseason entry.

## Project Structure
```text
nba-playoff-predictor/
├── data/
│   ├── raw/            # Original API dumps (Bronze)
│   ├── processed/      # Cleaned data for modeling (Silver)
│   └── final/          # Aggregated dashboard data (Gold)
├── notebooks/
│   ├── 01_data_ingest.ipynb
│   └── 02_modeling.ipynb
├── src/
│   ├── __init__.py
│   ├── data_loader.py  # Scripts to fetch and clean data
│   └── models.py       # ML model training logic
├── README.md
└── requirements.txt
