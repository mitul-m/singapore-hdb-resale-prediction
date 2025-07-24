# Singapore HDB Resale Price Prediction (2017–2022)
This project aims to predict HDB resale prices in Singapore using historical transaction data from 2017 to 2022. The analysis includes exploratory data analysis (EDA), feature engineering, and building a linear regression model to estimate resale price trends and feature impact.

## Dataset

- **Source**: [kaggle – HDB Resale Flat Prices]((https://www.kaggle.com/datasets/mikelll/singapore-housing-price-20172022))
- **Rows**: ~132,000
- **Features**:  
  - `month`  
  - `town`  
  - `flat_type`
  - `block`
  - `street_name`
  - `floor_area_sqm`  
  - `storey_range`  
  - `flat_model`  
  - `lease_commence_date`  
  - `remaining_lease` (engineered)  
  - `resale_price` (target)

---

## EDA Highlights

- **Right-skewed resale price distribution** (peak around SGD 450,000)
- **Average resale price increased sharply from 2020–2022**
- **Strong relationship between remaining lease and price**, especially below 60 years
- **Flat type and town** are major drivers of price differences

---

## Feature Engineering

- Converted `remaining_lease` from text to numeric (years)
- One-hot encoded categorical variables: `flat_type`, `town`, `storey_range`, `flat_model`
- Extracted `year` from `month`
- Dropped high-cardinality, low-informative columns: `block`, `street_name`

---

## Model: Linear Regression

- **Framework**: `scikit-learn`
- **Train/Test Split**: 70/30
- **Evaluation Metrics**:
  - R² Score: **0.85**
  - MAE: **~SGD 47,700**

---

## Key Visuals

- Resale price trend over time  
- Boxplots by flat type  
- Scatter plot: Remaining lease vs resale price  
- Residual plots to assess linearity and error spread

---
