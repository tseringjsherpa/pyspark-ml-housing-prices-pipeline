# Supervised Learning using PySpark
# Predict Housing Prices

## Introduction
Housing prices depend on many factors, like the size of the house, number of bedrooms and bathrooms, location, and condition. Predicting prices can help buyers, sellers, and real estate agents make better decisions.  

In this project, I use **supervised learning** to predict house prices. Since the target variable (`price`) is numeric, this is a **regression problem**. I use **Multiple Linear Regression (MLR)** to see how different features affect house prices.  

## Dataset
The dataset I use has information about houses sold in Seattle, including:  
- `id`: Unique identifier for each house  
- `date`: Date the house was sold  
- `price`: Sale price (target variable)  
- `bedrooms`: Number of bedrooms  
- `bathrooms`: Number of bathrooms  
- `sqft_living`: Living space in square feet  
- `sqft_lot`: Lot size in square feet  
- `floors`: Number of floors  
- `waterfront`: Waterfront property (0 = no, 1 = yes)  
- `view`: View quality rating  
- `condition`: Condition rating  
- `grade`: Construction and design grade  
- `sqft_above`: Living space above ground  
- `sqft_basement`: Basement area  
- `yr_built`: Year built  
- `yr_renovated`: Year renovated (0 if never)  
- `zipcode`: ZIP code  
- `lat`: Latitude  
- `long`: Longitude  
- `sqft_living15`: Living space of 15 nearest houses  
- `sqft_lot15`: Lot size of 15 nearest houses  

You can find the dataset here: [house-data.csv](https://raw.githubusercontent.com/grzegorzgajda/spark-examples/master/spark-examples/data/house-data.csv) (Grzegorz Gajda, 2020). 

## Project Workflow
1. **Load the Data** - Import housing data and check for missing values
2. **Explore the Data** - Analyze distributions and relationships between features
3. **Feature Engineering** - Create new features like house age and renovation status
4. **Data Preparation** - Create dummy variables for categorical features (zipcode, grade, condition, view)
5. **Modeling** - Train a Multiple Linear Regression model using PySpark MLlib
6. **Evaluation** - Evaluate model performance using R², RMSE, and MAE metrics

## Key Features Used
**Numeric Features:**
- Property characteristics: bedrooms, bathrooms, square footage, floors
- Location: latitude, longitude
- Age: house age, renovation status

**Categorical Features (Dummy Variables):**
- Zipcode (location zones)
- Grade (construction quality)
- Condition (property condition rating)
- View (view quality rating)

## Model Performance
- **R² Score**: Measures how well the model explains price variation
- **RMSE**: Average prediction error in dollars
- **MAE**: Average absolute prediction error

The model shows good performance with minimal overfitting, indicating it generalizes well to new data.

## Conclusion
This project successfully built a Multiple Linear Regression model to predict house prices in Seattle using PySpark. The model identifies key factors that influence housing prices, with location (zipcode), property size (square footage), and quality (grade) being the most important predictors.

**Key Findings:**
- The model explains a significant portion of price variance, showing that the selected features are good predictors
- Location features (zipcode, latitude, longitude) have strong influence on prices
- Property characteristics like living space and grade are important price drivers
- The model performs consistently on both training and test data, indicating good generalization

**Limitations:**
- Linear regression assumes linear relationships, which may not capture all price patterns
- Extreme outliers or luxury properties may not be predicted as accurately
- External factors like market trends or economic conditions are not included

This project demonstrates how machine learning can provide valuable insights for real estate pricing and decision-making.

## Tools & Technologies
- **Apache Spark** (PySpark) - Distributed data processing
- **PySpark MLlib** - Machine learning library
- **Databricks** - Development environment
- **Python** - Programming language

## References
- Dataset: Grzegorz Gajda (2020). [House Sales Data](https://raw.githubusercontent.com/grzegorzgajda/spark-examples/master/spark-examples/data/house-data.csv)
