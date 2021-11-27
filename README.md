# Estimate-the-price-of-used-car-at-TrueValue
Looking for new car : Yaaaa, we understand that increasing prices of the cars are a big problem in India for most of the middle class families , so we created a model that can predict the price of a used car , certified by true values and would not break your budget, so find out 

# 1. Loading the dataset 
# 2. Understanding the data
- shape ,size , keys ,datatypes, checking for duplicated values 
# 3. Find unique values 
- uniques for all the columns and frequencies
# 4. Dealing the Null values 
- checking with percentage of null values and understanding how they are related to the target variable-
- remove the columns if they are higer then 35% of null values 
- replacing with mean , mode .ffill or bfill   
# 5. Correlation with the heatmaps
- seaborn librabry to see what features are effecting the target variable 
# 6. Outliers detecting and handeling
- matplotlib and seaborn , box plots for outlier detection and kde plots for skewness 
- Dealing the outliers by removing the unwanted records  
# 7. Complete EDA
- creating new featrues : pricedrop , pricedrop per year ,pricedrop % by year 
- converting continous data into catagorical data for more better analysis 
- barplots,lineplots ,countplots,heatmaps,crossttabs,jointplots,scatterplots,regression plots to understand and analyze
- correlation and dependency of the data 
# 8. Observations
- observations written after, each importent graph
# 9. Analysis report
- complete analysis points from all the graphs and data 
- conclusion :To increase the saleprice at Truevalue you have to offer the cars that are hatchback type and manual transmission with a petrol engine not more then 6year old and with less number owners and price should be ranging between 4 to 6 lakhs .
# 10 Standerd scaling 
# 11. Label encoding 
# 12. linear Regression 
# 13. lasso regression 
# 14. XGB Regressor 
# 15. Model Evaluation
-RMSE,meansquare erroe,mean absolute error,performence of each model 
# 16 Randomized search cv
# 17. Hyperparameter tuning with Randomforest regressor
- nestimators and cv,msx_depth,sample_splt and leaf_split
# 18. Error evaluation 

# 19. Importing a Pickel file  
