# Optimal Budget Allocation for Marketing Channels - Market Mix Modeling 

## Overview
This repository contains the implementation of an optimal budget allocation strategy for marketing channels, tailored for an electronics-focused e-commerce firm operating in Ontario, Canada. The strategy is based on a comprehensive analysis of past marketing campaigns, market mix modeling (MMM), and attribution analysis to enhance revenue response in the upcoming year.

## Solution Approach
1. **Data Preparation**: 
   - Incorrect values imputation: If Gross Merchandise Value i.e GMV  > (product_mrp * units ) then impute the faulty MRP values with GMV/units.
   - Selecting data of 1 year from July 2015 to June 2016.
   - Treating missing values and anomalies.
     
2. **Feature Engineering**:
   Creation of new KPIs
   - Derive “Listing Price” i.e. GMV/units.
   - Calculating Discount% with 100*(product_mrp – listing_price) / product_mrp and total price with product_mrp * units.
   - Convert order_payment_type from categorical to binary data by assigning Prepaid = 1 and COD = 0.
   - Create a calendar for the one year period and merge it with special sales dates list.
   - Removing features with high correlation.
   - All the features & target variable are aggregated on **weekly level**.

4. **Exploratory Data Analysis (EDA)**:
   - Perform EDA on Camera accessories, Gaming accessories, Home audio.
   - Take the target variable as Gross Merchandise VAlue (GMV).
   - Perform Univariate analysis of target variable GMV for per week.
   - Bivariate analysis of GMV  for special sales dates.
   - Bivariate analysis of GMV for discount on products.

5. **Model Development**:
   - Model used - Multi Linear Regression Model with feature selection using  Recursive feature elimination (RFE)
   - Data is split into train and test sets in 70:30 ratio.

6. **Model Tuning**:
   Model Tuning through Recursive Feature Elimination (RFE) to:
   - Improved Model efficiency
   - Prevent Overfitting
   - Identify Key Features for Final Model
Final Model Selected with no. of features = 10, based on p values of the features

## Business Impact
1. **Projected Revenue Improvements**
   
   There will be potential revenue improvements resulting from the optimized budget allocation

2. **Long-Term Benefits**
   
   Optimized budget allocation can create a ripple effect, impacting long-term brand perception, customer loyalty, and market positioning

3. **Improved ROI**
   
   Investing in high-impact marketing channels optimizes revenue for every marketing dollar invested, resulting in a direct increase in ROI.



## Requirements
- Python 3.x
- Jupyter Notebook
- Pandas, NumPy, Matplotlib, Seaborn (for data analysis and visualization)
- Scikit-learn (for modeling and analysis)
