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
