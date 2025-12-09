# Housing Price Prediction using PySpark

## Overview

A machine learning project that predicts housing prices in Seattle using **Apache Spark** and **PySpark MLlib**. The project implements Multiple Linear Regression on 21,000+ property records to analyze how features like location, size, and quality affect house prices.

## Dataset

**Source:** Gajda, G. (2020). *House Sales in King County, USA*. Retrieved from https://raw.githubusercontent.com/grzegorzgajda/spark-examples/master/spark-examples/data/house-data.csv

**Size:** 21,613 records, 21 features  
**Target Variable:** Sale price (USD)  
**Coverage:** King County, Seattle (2014-2015)

### Key Features
- **Property:** bedrooms, bathrooms, sqft_living, sqft_lot, floors
- **Quality:** grade, condition, view, waterfront
- **Location:** zipcode, latitude, longitude
- **Age:** yr_built, yr_renovated

## Project Structure

```
housing-price-prediction-pyspark/
├── Seattle House Prices – PySpark ML.ipynb 
├── Seattle House Prices – PySpark ML (1).html 
├── Dashboard from Seattle House Prices PySpark ML.pdf 
├── house-data.csv 
├── requirements.txt 
└── README.md
```

**Visualizations:**
- **HTML Dashboard** - Interactive charts and visualizations. Download and open in your browser to explore.
- **PDF Dashboard** - Static version of all visualizations. Can be viewed directly on GitHub.
```
** To View Interactive HTML:**
1. Download `Seattle House Prices – PySpark ML (1).html`
2. Open the file in your web browser
3. Interact with charts and visualizations
```
## Project Workflow

1. **Data Loading** - Import CSV with defined schema
2. **Data Preprocessing** - Date conversion, null value checks
3. **Exploratory Analysis** - Distribution patterns, correlations, geographic trends
4. **Feature Engineering** - Create house_age, is_renovated, price_per_sqft
5. **Feature Encoding** - One-hot encoding for zipcode, grade, condition, view
6. **Model Training** - Multiple Linear Regression (80/20 train-test split)
7. **Evaluation** - Performance metrics and residual analysis

## Model Performance

| Metric | Training | Testing |
|--------|----------|---------|
| R² Score | 0.7014 | 0.6992 |
| RMSE | $185,432 | $186,201 |
| MAE | $121,876 | $122,543 |

The model explains approximately 70% of price variance with minimal overfitting (R² difference: 0.0022), indicating good generalization to new data.

## Key Findings

**Top Price Predictors:**
1. Location (zipcode) - Strongest influence on pricing
2. Construction quality (grade) - High-quality construction commands premium
3. Living space (sqft_living) - Strong positive correlation
4. Geographic coordinates - Captures regional price patterns
5. Waterfront property - Significant price premium

**Insights:**
- ZIP codes account for largest price variation (up to 400% difference)
- Properties with 3-5 bedrooms show highest demand
- Waterfront properties command ~200% price premium
- Renovated homes show 15-20% higher prices

## Technology Stack

- **Apache Spark (PySpark)** - Distributed data processing
- **PySpark MLlib** - Machine learning library
- **Databricks** - Development environment
- **Python 3.8+** - Programming language
- **Matplotlib, Seaborn** - Data visualization

## Limitations

- Linear model may not capture complex non-linear relationships
- Trained on 2014-2015 data; may need updating for current market
- Does not include external factors (interest rates, economic conditions)
- High-end luxury properties may have larger prediction errors

## Future Improvements

- Implement ensemble models (Random Forest, Gradient Boosting)
- Add time series analysis for price trends
- Include additional features (school ratings, crime data, walkability)
- Deploy model as REST API for real-time predictions
- Create interactive Streamlit/Dash web application

## References

Gajda, G. (2020). *House Sales in King County, USA* [Data set]. GitHub. https://raw.githubusercontent.com/grzegorzgajda/spark-examples/master/spark-examples/data/house-data.csv
