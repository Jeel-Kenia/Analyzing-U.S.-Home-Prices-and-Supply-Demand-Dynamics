# Introduction
In this project, we aim to analyse various supply demand factors that affect U.S. Home prices over the last 20 years. Home prices can be affected due to various demand and supply factors such as GDP, Population, House inventory, etc. It is important to find the relation between these factors and house prices to develop a robust predictive model. 

Demand and supply are fundamental economic concepts that describe the relationship between the quantity of a good or service that consumers are willing to buy (demand) and the quantity of that good or service that producers are willing to supply (supply) at different prices. These concepts are essential for understanding how prices and quantities are determined in markets.The law of demand and supply states that as the price of goods/services increases the demand for it would decrease (consumers tend to buy less to reduce loss) and the supply for it would increase (prodcuers would want to sell more to increase profit). The interaction of demand and supply determines the equilibrium price and quantity in a market.

![image](https://github.com/Jeel-Kenia/Analyzing-U.S.-Home-Prices-and-Supply-Demand-Dynamics/blob/main/0d37867b-d0a8-44b7-8c62-a1c73809e34e.jpg)
Image Courtesy: [Financial Times](https://www.ft.com/content/b9df3102-a7d2-483d-8216-f507c0460d3d)

# Purpose of the Project
In this project, we aim to:

- Gather historical data on U.S. home prices using the S&P Case-Schiller Home Price Index.
- Collect additional publicly available data on key supply and demand factors affecting the housing market.
- Perform data analysis to identify trends and correlations between housing prices and supply-demand factors.
- Create data visualizations to present insights and findings.
- Build predictive models to explain how these factors impacted home prices over the last 20 years.
  
# About the Dataset
**The Data for this project is collected from FRED(Federal Reserve Economic Data) which is the official site for U.S. Economic data.** The different factors considered for this project are:

**`observation_date`**: The range of period taken for analysis. Data taken from 01-01-2003 to 01-04-2023.

**`ASPUS`**: Average Sales Price of Houses Sold for the United States, Dollars. This represents the average value of house sale pricesd for a specific period.

**`MSPUS`**: Median Sales Price of Houses Sold for the United States, Dollars. The median sales price is the middle value in a list of all house sale prices, with half of the sales prices falling below this value and half above it.

**`EVACANTUSQ176N`**: Housing Inventory Estimate: Vacant Housing Units in the United States, Thousands of Units. It provides information about the estimated number of vacant housing units in the United States at a given point in time or over a specific period.

**`ETOTALUSQ176N`**: Housing Inventory Estimate: Total Housing Units in the United States, Thousands of Units. The data represents the estimated total count of housing units, which includes a wide range of residential properties such as single-family homes, multi-family units, apartments, condominiums, and other types of dwellings.

**`GDP`**: Gross Domestic Product, Billions of Dollars.

**`UNRATE`**: Unemployment Rate, Percent. The unemployment rate is a critical labor market indicator that measures the proportion of people in the labor force who are without a job and are actively looking for work.	

**`INTDSRUSM193N`**: Interest Rates, Discount Rate for United States, Percent per Annum. It is the interest rate at which eligible depository institutions (typically banks and credit unions) can borrow money from their regional Federal Reserve Bank

**`MORTGAGE15US`**: 15-Year Fixed Rate Mortgage Average in the United States, Percent. It is a type of home loan where the interest rate remains constant (fixed) for the entire 15-year term of the loan. 

**`MORTGAGE30U`**: 30-Year Fixed Rate Mortgage Average in the United States, Percent. It is a type of home loan where the interest rate remains constant (fixed) for the entire 15-year term of the loan.

**`UMCSENT`**: University of Michigan: Consumer Sentiment, Index 1966:Q1=100. It is a measure of consumer confidence and attitudes toward the economy. It reflects consumers' perceptions of their current financial situation, as well as their expectations for future economic conditions.

**`MSACSR`**: Monthly Supply of New Houses in the United States, Months' Supply. The data indicates the supply of newly constructed homes available in the market each month. This supply is typically measured in the number of months it would take to sell the current inventory of new homes at the current sales pace.

**`TLRESCONS`**: Total Construction Spending: Residential in the United States, Millions of Dollars. The data indicates the total monetary value of spending on residential construction projects in the United States. It encompasses spending on various types of residential construction, including single-family homes, multi-family dwellings, and residential improvements.

**`POPTHM`**: Population, Thousands. This data represents the total population of the country for a specific period of time.

**`PERMIT`**: New Privately-Owned Housing Units Authorized in Permit-Issuing Places: Total Units, Thousands of Units. It showcases the number of new privately-owned housing units that have been authorized or permitted for construction in a specific geographical area over a given period of time	

**`CSUSHPISA`**: S&P/Case-Shiller U.S. National Home Price Index, Index Jan 2000=100, Quarterly, Seasonally Adjusted. The S&P Case-Shiller U.S. National Home Price Index (CSUSHPISA) is used as a proxy for home prices and serves as the dependent variable in the analysis.

The data taken is on quartery basis with GDP, UNRATE, MSACR, TLRESCONS, PERMIT AND CSUSHPISA being seasonally adjusted and the rest not seasonally adjusted.

# Data cleaning and preprocessing
Data has been cleaned and pre-processed to treat:
* Null Values
* Duplicates
* Incorrect Data Structures
* Outliers

# Exploratory Data Analysis
EDA has been done to find the relationship between the features and the target variable. You can find the correlation heatmap depicting relation of features with the Home Price Index below:

![image](https://github.com/Jeel-Kenia/Analyzing-U.S.-Home-Prices-and-Supply-Demand-Dynamics/blob/main/Screenshot%202023-09-11%20at%2011.42.25%20AM.png)

Different data visualizations have been created showcase relationship of the Case-Shiller Home Price Index with each variable individually.

![image](https://github.com/Jeel-Kenia/Analyzing-U.S.-Home-Prices-and-Supply-Demand-Dynamics/blob/main/Screenshot%202023-09-11%20at%2011.59.43%20AM.png)

# Machine Learning Models:
Various models were analysed to find the model with the best performance. The steps followed to create an efficient machine learning model were as follows:

- Assigning feature and target variables to X and y respectively.
- Splitting the data into training set for developing the model and testing set for model evaluation
- Scaling training data for better model development and accuracy.
- Using different machine learning models such as `Linear regression`, `KNN`, `Decision Tree`, `Ridge`, `Lasso`, `XG Boost` and `SVR` to find the most efficient model.
- `Mean Absolute Error(MAE)` and `R Squared` values were used as evaluation metric for model evaluation.
- Finding the most important features which resulted in fluctuations in the Home Price Index.

# Key Insights
![image](https://github.com/Jeel-Kenia/Analyzing-U.S.-Home-Prices-and-Supply-Demand-Dynamics/blob/main/Screenshot%202023-09-11%20at%2012.33.46%20PM.png)

Features such as "GDP," "Total Construction Spending," and "Housing Inventory Estimate(Total)" have the highest positive coefficients. This suggests that increases in these variables are strongly associated with higher home prices. Specifically:

"GDP" has the highest positive coefficient, indicating that an increase in GDP is associated with a substantial increase in home prices.

"Total Construction Spending" also has a strong positive influence on home prices.

"Housing Inventory Estimate(Total)" has a positive impact, suggesting that a larger inventory of available housing is associated with higher home prices.

Feature such as "Consumer Sentiment", "Mortgage rates" and "Housing Inventory estimate(Vacant)" have week coefficients. This suggests that a change in these variables would not afffect home prices substantially. 

# Conclusion
This project aimed to find different supply demand factors that drove house prices nationally in the U.S. with the help of machine learning models, we were ble to find out the most accurate and efficient model that assisted in predicting house prices and finding out the factors that influenced house prices over the years.

# Files Included

Data.xlsx: The dataset used for the analysis.

model.ipynb: Jupyter Notebook documenting the complete data analysis and model building process.

README.md: This README file providing an overview of the project.

# Usage and Exploration

Feel free to explore the Jupyter Notebook (model2.ipynb) to understand the entire data analysis process, from data preprocessing to model evaluation. If you're interested in predicting U.S. Home prices due to different supply demand factors and or understanding how predictive analytics can drive business decisions, this project can serve as a valuable resource.

# Contact

If you have any questions, suggestions, or would like to discuss the project, predictive analytics, or the insurance industry, please feel free to contact me at jeelkenia.jk@gmail.com.

Thank you for visiting this repository!














