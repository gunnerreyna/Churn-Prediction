# Churn-Prediction
NOTE since this project uses real data from a real ride share company, the company will be referred to as 'Company X' and the data will not be published. 

#Problem: 
  Company X has an issue with high churn rates. This project will: 
  - help identify what factors are the best predictors for retention.
  - offer suggestions on how to operationalize these new insights in customer retention marketing campaigns.

#Data/Definitions
 - Sample dataset of a cohort of users who signed up for an account in January 2014. 
 - The data was pulled on July 1, 2014.
 - Define a user as retained if they were “active” (i.e. took a trip) in the preceding 30 days (from the day the data was pulled). 
 - Assume the latest day of last_trip_date to be when the data was pulled. 
 
#Exploratory Data Analysis
 - Number of records: 50,000
 - Inactive customers:   30777   61%
 - Active customers   19223  39%

 - Data limited to 3 cities

#Assumptions
 - Columns with NaN values:
      - Avg_rating_by_driver (201) – replaced with average of column
      - Avg_rating_of_driver (8122) - replaced with average of column
      - Phone (type) – (396) replaced with ‘Unknown’
      
#Computing the target
The target is a boolean indicating whether a customer is 'active' = True, or 'inactive' = False.  

![ComputingTarget](/ComputingTarget.png?raw=true "ComputingTarget")

#Model Selection
Several model types were generated and compared.  The Random Forest model was selected due to it's accuracy score.

![Model Selection](/ModelSelection.png?raw=true "ModelSelection")

#Model Optimization
 - Number of trees = 40
 - Number of features = 4
 - Min sample leaf = 55

![Model Optimization](/ModelOptimization.png?raw=true "ModelOptimization")


#Feature Importance
The overall top 8 features influencing churn were determined to be:

![Overall Feature Importance](/OverallFeatureImportance.png?raw=true "OverallFeatureImportance")

But further analysis showed that these feature rankings were not consistent across the 3 cities. 

![Active Customers by City](/ActiveCustomersbyCity.png?raw=true "ActiveCustomersbyCity")

![Feature Importance by City](/FeatureImportanctbyCity.png?raw=true "FeatureImportanctbyCity")

#Recommendation
Our results show two very different markets across the 3 cities.  The cities of Astapordf and Winterfelldf have a high churn rate, therefore the marketing campaign should focus on these 2 cities.



