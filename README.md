# SalesPrice_Prediction
Iam going to explain my process of predicting House SalesPrice.  I tried to solve this problem first by modelling on the data with outliers, later modelled the data without outliers and tried explaining the reasons for the difference in model accuracy for that following steps had been taken below

1)Checked the data types and null value percentage

2)If null value percetage is more than 50% deleted the columns

3)Split the main table into two parts one with all Numeric features and another with Categorical features

       Numeric table:
4)In Numeric table filled NAN values column with mean

     Categorical table:
5)In Categorical table filled NAN values with method='bfill' and 'ffill'

6)After filling NAN values, assigned the labelencoder to all the columns and OneHotencoder as well

7)Joined both the tables of Numeric and Categorical tables in one table

8)Fit the model using decision tree machine learning algorithm with an accuracy score of 82% on complete data that includes ouliers

9)In Another try, modelled the data without outliers using decision tree machine learning algorithm, obtained accuracy score of 62%. Outliers are removed only from training data.

10)Acccuracy dropped after removing outliers, my hypothesis is important information is lost in outliers, and I tried to find that important information in outliers

11)To do that, I first did a check on feature importances in both With and WithOutliers data and compared them

12)While comparing, I found 15% diff in 'OVERALLQUAL' column, when further looked I observed that certain values were only present in the outliers and they went away when we removed outliers,hence we lost certain important information. These values were present in the test dataset and the model didnot know how to score them.



Dataset :https://www.kaggle.com/saiharsha1234/salesprice-prediction. Tools used : Python Libraries used : pandas, numpy, matplotlib, sklearn, Concepts : Imputation, Machine Learning Algorithm : Decision Tree Regressor
