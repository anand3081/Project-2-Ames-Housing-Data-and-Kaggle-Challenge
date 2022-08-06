# Project 2: Ames Housing Data and Kaggle Challenge

Project 2 done by - **Anand Ramchandani**

## Executive Summary  

## Problem Statement  
We are a start-up aiming to set up a Sale Price recommendation tool where users can use to get a recommended Sale Price with just a few feature characteristics about their property which users would provide and upload onto our recommendation tool. Using our proprietary machine learning algorithm, the web application generates a quote estimate for their property Sale Price.

## Contents

- [Background](#Background)
- [Data Import & Cleaning](#Data-Import-and-Cleaning)
- [Exploratory Data Analysis](#Exploratory-Data-Analysis)
- [Feature Engineering](#FeatureEngineering)
- [Modelling](#Modelling)
- [Kaggle Submission](#KaggleSubmission)
- [Conclusion and Business Recommendations](#ConclusionandBusinessRecommendations)
- [Limitations](#Limitations)


## How the analysis was done
Train and Test Data was obtained from Kaggle of over 2000 housing datapoints, in order to train and test a model. For each Id in the test set, we are required to predict the SalePrice of the corresponding houses. We imported the data using pandas and checked for missing data and outliers. Using the data dictionary, we went through the features and selected which ones were the most pertinent on Sale Price and addressed any underlying data quality issues. Ordinal values were labeled with numeric code so as to avoid using get dummies and multiplying features unneccesarily, that method was reserved for nominal values

After cleaning the data and conducting EDA, we started testing the data using different models to see how the performance was and retroactively did feature engineering to improve the RMSE score. The evaluation of the project is done by Kaggle submission, with leaderboard standings provide a root mean squared error (RMSE) which can help gauge the performance of the model

## Limitations
- This model does not take into account interest rates, overall macroeconomic trends, unemployment figures, etc  
- The housing data obtained was between 2006 to 2010, which is the time interval at the heart of the 2008 Financial Crisis which resulted in a housing bubble collapse. There must have been a massive drop in Sale Prices throughout those years and may heavily impact our prediction model for more stable years in the housing market  
- The features that are highly correlated with Sale Price tend to exhibit high multi-collinearity and require additional processing
- Sale Price has a right skewed distribution and tends to not perform well with house prices above $400k  


## Conclusions and Business Recommendations
- The following features appear to add the most value to a home: 'overall_qual', 'gr_liv_area', 'exter_qual', 'kitchen_qual', 'total_bsmt_sf', 'garage_area', 'year_built' 
- Lot Shape (Ordinal): General shape of property seems to hurt the value of a home the most, but generally features observed that have a highly negative correlation with Sale Price  
- Homeowners could improve their homes to increase the value by increasing overall quality of the home, expanding groung living area, exterior and kitchen quality should improve, increased garage area and increased basement square feet  
- Houses in Stone Brook neighborhoods seem like they might be a good investment due to high correlation with Sale Price  
- This model may not generalize well to other cities, because a lot of other cities may not have garages or basements as a popular house addition  
- To make it more universal we would need more data that have house features that are more popular, and also proximity to locations like malls, schools, transportation hubs would be invaluable to improving the model  
- Although Ridge Regression Model was used for this project finally, it would be advantageous to try different models to see if we can achieve better prediction performance  
- We can collect data that is more recent and a wider year range historically rather than just the 4 years 2006 to 2010. This is recommended because we believe a longer timescale will minimise the effect on short term macroeconomic events that could drastically affect house sale prices  
- Since the model does not work well with houses above $400k in value, we should collect more data points with house saleprices above $400k  
- Collecting data with more features would be advantageous in improving the model  