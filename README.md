# Global GDP Insights — ML + Data Analysis Project

This repository contains a Jupyter Notebook that explores and solves a **time series forecasting problem** focused on **predicting GDP** for selected countries using historical economic data.

The project walks through the complete data science workflow: data loading, exploratory data analysis (EDA), preprocessing, model training, hyperparameter optimization, and evaluation using multiple machine learning and statistical forecasting algorithms.

---

## Project Overview

Gross Domestic Product (GDP) is one of the most widely used indicators of a country's economic health. Accurately forecasting GDP trends can help policymakers, analysts, and researchers make informed decisions. In this project, multiple forecasting models are trained and compared to predict the GDP of selected countries using nominal GDP data spanning from 1960 to 2023.

The notebook is designed to be educational and practical, combining economic reasoning, visualization, and hands-on model implementation. It also merges GDP data with population data to compute per-capita metrics, offering a more nuanced perspective on economic performance.

---

## Models Used

Four forecasting approaches are implemented, optimized, and compared:

* **Polynomial Linear Regression** — Baseline model, applied with degree tuning
* **ARIMA** — Statistical time series model with grid search over (p, d, q) parameters
* **Prophet** — Facebook's forecasting library with changepoint prior scale optimization
* **LSTM** — Deep learning model (Long Short-Term Memory) using TensorFlow/Keras

Each model is trained on an 80/20 time-based train/test split, evaluated using MAPE (Mean Absolute Percentage Error), and used to produce a 5-year future forecast. A final side-by-side comparison is generated for each country.

---

## Dataset

* The GDP dataset is loaded from a CSV file (`gdp.csv`), sourced from DataHub (World Bank / OECD)
* A supplementary population dataset (`population.csv`) is merged to compute GDP per Capita
* The schema includes: `Country Name`, `Country Code`, `Year`, and `Value` (GDP in current USD)
* The dataset covers **1960–2023** across countries, regions, and income groups

> **Note:** The dataset contains **nominal GDP** values (not inflation-adjusted). Changes over time may reflect both real economic growth and price/currency effects. Additionally, the dataset paths are configured for Google Colab and Google Drive. You may need to update the paths when running locally.

---

## Workflow

1. **Import Libraries** — NumPy, Pandas, Matplotlib, Seaborn, Plotly, scikit-learn, statsmodels, Prophet, TensorFlow, etc.
2. **Data Loading** — Load and merge GDP and population datasets; compute GDP per Capita
3. **Data Quality Analysis** — Inspect structure, identify regional aggregates, missing values, coverage gaps, and temporal inconsistencies
4. **Exploratory Data Analysis (EDA)**
   * Top economies by GDP and GDP per Capita (2023)
   * GDP evolution over time for top 15 economies
   * Greece vs. comparable European economies (Croatia, Ireland, Portugal, Hungary)
   * GDP per Capita comparison between Greece and the European Union
   * Major economies comparison (US, EU, China, Japan, India, Brazil, Russia)
5. **Correlation Analysis** — GDP growth rate correlation matrix for top economies and selected European countries
6. **Model Training & Forecasting** — Train all four models for Greece, Portugal, and Germany
7. **Hyperparameter Optimization** — Grid search for ARIMA orders, Prophet changepoint scales, and LSTM lookback/epoch/batch size parameters
8. **Model Comparison** — MAPE-based ranking with horizontal bar chart visualization per country
9. **Fine-Tuning** — Walk-forward backtesting for ARIMA (40/60, 60/40, 80/20 splits) on Germany

---

## Visualizations

The notebook includes:

* Interactive bar and line charts (Plotly) for GDP and GDP per Capita by country
* GDP evolution plots for regional and country groupings
* Train/test/forecast plots for all four models per country
* Correlation heatmaps of annual GDP growth rates
* ARIMA walk-forward backtesting plots across multiple folds
* Model performance comparison bar charts (MAPE)

---

## Tools & Libraries

* NumPy
* Pandas
* Matplotlib
* Seaborn
* Plotly
* scikit-learn
* statsmodels (ARIMA)
* Prophet
* TensorFlow / Keras (LSTM)
* Google Colab

---

## Purpose

The purpose of this project is to practice and demonstrate how different forecasting techniques — ranging from simple linear regression to deep learning — can be applied to real-world economic time series data. It focuses on understanding the full machine learning workflow, from exploratory analysis and data cleaning to model evaluation and future forecasting, while also developing economic intuition through data-driven storytelling.

---

## Files Included

The repository includes 2 files:

* A PowerPoint Presentation summarizing the project
* The Python Code (Jupyter Notebook) for the project
