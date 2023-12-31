# Bartholomew_Luke_DA301_Assignment
LSE Data Analytics Assignment 3
===========================================================================
# Assignment Activity 1: Making Predictions with Regression

Linear Regression: spending_score vs loyalty_points
- R-Squared: 45.20% of the total variability of y (how many loyalty_points the customer has collected), is explained by the variability of X (the customer spending_score).
- X: The coefficient of X describes the slope of the regression line, in other words, how much the response variable y change when X changes by 1 point. In this model, if the customer spending_score (X) changes by 1 point, then the loyalty_points collected by the customer (y) will change by 33.06 points. 
- The P>[t] for the X coefficient value tests the hypothesis that the slope is significant or not. If the corresponding probability is small (typically smaller than 0.05) the slope is significant. In this case, the probability of the t-value is zero, thus the estimated slope is significant.
- The model performed better where spending_score <= 60 (R-Squared = 60.10%). Perhaps this can investigated further using clustering.

Linear Regression: remuneration vs loyalty_points
- R-Squared: 38% of the total variability of y (how many loyalty_points the customer has collected), is explained by the variability of X (the customer remuneration).
- X: The coefficient of X describes the slope of the regression line, in other words, how much the response variable y change when X changes by 1 pound (£). In this model, if the customer remuneration (X) changes by 1 pound, then the loyalty_points collected by the customer (y) will change by 0.0342 pounds. 
- The P>[t] for the X coefficient value tests the hypothesis that the slope is significant or not. If the corresponding probability is small (typically smaller than 0.05) the slope is significant. In this case, the probability of the t-value is zero, thus the estimated slope is significant.
- The model performed better by removing customers with remuneration >= 55000 AND loyalty_points <= 2500 (R-Squared = 83.50%). Perhaps this can investigated further using clustering.

Linear Regression: age vs loyalty_points
- R-Squared: 0.1% of the total variability of y (how many loyalty_points the customer has collected), is explained by the variability of X (the customer age).
- No correlation between customer age and loyalty_points. This model will not be useful in predicting the value of loyalty_points using age.

Multiple Linear Regression: age, spending_score & remuneration vs loyalty_points
- R-Squared: 84% of the total variability of y (how many loyalty_points the customer has collected), is explained by the variability of X (the customer age, spending_score and remuneration).

# Assignment Activity 2: Making Predictions with Clustering

We identified 5 cluster groups of customers within the data relating to spending_score and remuneration which can help inform the marketing campaigns at Turtle Games:

Group 1: low spending_score, low remuneration
- This group is low risk (low value?), they spend relative to their monthly salary.
- This group represents 13.55% of the sample data.
- Average age is 43.5 years old (above average of the dataset which is 39.5). 
- The lowest number of loyalty points collected averaging only 275.

Targeting this group with a marketing campaign may have relatively low success in terms of new sales becuase this group would be risk adverse to spending beyond their means. 


Group 2: high spending_score, low remuneration
- This group is high risk and spend beyond their relative means.
- This group represents 13.45% of the total in this sample data.
- Average age is 31.6 years old which is the youngest grouping.
- Loyalty points collected averages 971 (3rd highest).

This group may purchase impulsively, even though the low yearly income suggests purchases will be less affordable. The lower average age indicates that perhaps some of the customers in this group are living at the parent's home. Despite the low remuneration, this group should be targeted for marketing purposes.The high spending_score coupled with the low loyalty_points suggests that this group may be interested in promotions or bargain buys (many purchases at low prices).


Group 3: medium spending_score, medium remuneration
- This group does not take on any extra risk and tends to spend as anticipated according to the yearly income.
- This group is the largest cluster and represents 38.70% of the total in this sample data.
- Average age is 42 years old which is the above the dataset average.
- Loyalty points collected are quite high at 1,420 (2nd highest).

This largest group is the 'bread-and-butter' of the business and should never be ignored. Average age suggests that they may be long-term loyal customers.


Group 4: low spending_score, high remuneration
- This group has lower interest in the products on sale, which can easily be purchased based on the yearly salary.
- This group represents 16.50% of the total in this sample data.
- Average age is 40.66 years old which is the above the dataset average.
- Loyalty points collected are not impressive at 911 (2rd lowest).

Despite being able to afford to purchase, customers in this group show little interest in the products. It may be less cost-effective to target this group with the marketing budget.
    

Group 5: high spending_score, high remuneration
- This group has a great deal of interest in the products on sale, and they can easily afford to purchase more based on the yearly salary.
- This group represents 17.80% of the total in this sample data (2nd largest group).
- Average age is 35.60 years old which is the below the dataset average (2nd youngest group).
- Loyalty points collected are the most impressive at 3,988 (top).
    
This group has the most disposable income and doesn't mind spending it, possibly purchasing some of the most expensive products. The marketing department should always include this group in any new campaign.

# Assignment Activity 3: Analysing Customer Sentiments with Reviews

Several NLP sentiment analysis models (VADER, TextBlob, BERT) were tested to better understand customer sentiment towards the products purchased, which will help Turtle Games to identify marketing opportunities that can increase sales and reduce churn rates. Vader and TextBlob required pre-processing the text to create a ‘bag of words’, while BERT models do not require this step, there are complications with the maximum length of the text. The BERT models provided more accurate sentiment scores, compared to VADER and TextBlob models. The NLP Town BERT Model was chosen because it had a familiar scoring system using star ratings from 1 (negative) to 5 (positive), this would make it easy for employees to understand and therefore take appropriate action. Accurate real-time sentiment analysis of customer reviews can provide valuable information to the marketing department, helping them to (1) identify products that were not well received by the customers, (2) respond to customers negative experience in order to avoid churn, (3) quickly identify top-rated products which can be included in promotions to new customers. These are just 3 examples.

# Assignment Activity 4: Visualising Data to Gather Insights

- There are strong correlations between the Global sales and the sales in North America and Europe.
- The data for each region shows as positively skewed and shows outliers in the higher range of sales.
- Sales in North America is generally higher in all categories than sales in Europe.
- Top genres of video games are: shooter, platform, action, role-playing, sports.
- Top platforms of video games are: Wii, X360, PS3, DS.
- Top publishers of video games are: Nintendo, Activision, EA, Take-Two.
- Several product codes stand out in terms of sales above 35m.

# Assignment Activity 5: Cleaning Manipulating & Visualising the Data

The data for Europe, North America and Global Sales does not form a normal distribution. There is positive skewedness (meaning most values are in the lower range), and kurtosis is leptokuric (meaning the bell shape is steep and pointed with a long tail, in this case the long tail is mainly on the right).

In order to normalise the data, serveral techniques were tested:
1. Removal of Outliers
2. Log
3. Square Root
4. Cube Root

Removal of outliers would not be deemed advisable because the excluded data would be valuable.

The log transformation was effective at reducing the value of kurtosis closer to 3, and worked best with the Global Sales data.

While for the Europe and North America Sales data, the cube root transformation was most effective. In fact, for Europe Sales, the cube root almost achieved a normal distribution.

# Assignment Activity 6: Making Recommendations to the Business

Multiple Linear Regression Model

Explanation
The model predicted Global sales based on the sales in North America and 
Europe.

Limitations
The dataset was too small to generate meaningful results. Ideally, any scenario involving predicting or forecasting sales would require time-based analysis. In this case, the data was limited to a snapshot in time, if the data was monthly then a time-series model could be built to any show trends and/or seasonality, and forecast future sales.

How can Turtle Games improve overall sales performance?

1. The Marketing Department must act on the target groups identified:
- Send an Net-Promoter Score survey to customers in group 1 (high spending score + high remuneration). These customers should be kept satisfied through special marketing promotions.
- Use a survey to understand more about group 2 (low spending score + high remuneration).

2. Use the loyalty program to collect more customer data which can improve the predictive model. The primary goal is to find key metrics that explain the accumulation of loyalty points e.g. house ownership, number of children, postcode.

3. Implement sentiment analysis on any customer contact such as product reviews, chat and emails. Focus on (i) keeping customers satisfied (e.g. fast-track complaints), (ii) products trending negative or positive, (iii) and identifying and rewarding happy customers who actively promote the brand.



It may be advisable to apply transformation to the data before building a multi-linear regression predictive model, but the results should be carefully monitored for undesirable effects. 

# Assignment Activity 6: Making Recommendations to the Business

Multiple Linear Regression Model

Explanation
The model predicted Global sales based on the sales in North America and 
Europe.

Limitations
The dataset was too small to generate meaningful results. Ideally, any scenario involving predicting or forecasting sales would require time-based analysis. In this case, the data was limited to a snapshot in time, if the data was monthly then a time-series model could be built to any show trends and/or seasonality, and forecast future sales.

How can Turtle Games improve overall sales performance?

1. The Marketing Department must act on the target groups identified:
- Send an Net-Promoter Score survey to customers in group 1 (high spending score + high remuneration). These customers should be kept satisfied through special marketing promotions.
- Use a survey to understand more about group 2 (low spending score + high remuneration).

2. Use the loyalty program to collect more customer data which can improve the predictive model. The primary goal is to find key metrics that explain the accumulation of loyalty points e.g. house ownership, number of children, postcode.

3. Implement sentiment analysis on any customer contact such as product reviews, chat and emails. Focus on (i) keeping customers satisfied (e.g. fast-track complaints), (ii) products trending negative or positive, (iii) and identifying and rewarding happy customers who actively promote the brand.

Further research should be focused on:
- Develop a logistic regression model using the target groups to identify more variables that may affect spending e.g., education, gender.

===========================================================================

THE END ;-)
  

