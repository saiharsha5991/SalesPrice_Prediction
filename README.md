# SalesPrice_Prediction
Iam going to explain my process of predicting House SalesPrice.  I tried to solve this problem first by modelling on the data with outliers, later modelled the data without outliers and tried explaining the reasons for the difference in model accuracy for that following steps had been taken below

*)Checked the data types and null value percentage

*)If null value percetage is more than 50% deleted the columns

*)Split the main table into two parts one with all Numeric features and another with Categorical features

       Numeric table:
*)In Numeric table filled NAN values column with mean

     Categorical table:
*)In Categorical table filled NAN values with method='bfill' and 'ffill'

*)After filling NAN values, assigned the labelencoder to all the columns and OneHotencoder as well

*)Joined both the tables of Numeric and Categorical tables in one table

*)Fit the model using decision tree machine learning algorithm with an accuracy score of 82% on complete data that includes ouliers

*)In Another try, modelled the data without outliers using decision tree machine learning algorithm, obtained accuracy score of 62%. Outliers are removed only from training data.

*)Acccuracy dropped after removing outliers, my hypothesis is important information is lost in outliers, and I tried to find that important information in outliers

*)To do that, I first did a check on feature importances in both With and WithOutliers data and compared them

*)While comparing, I found 15% diff in 'OVERALLQUAL' column, when further looked I observed that certain values were only present in the outliers and they went away when we removed outliers,hence we lost certain important information. These values were present in the test dataset and the model didnot know how to score them.



Kaggle Notebook Link :https://www.kaggle.com/saiharsha1234/salesprice-prediction. 

Programing Language used : Python Libraries used : pandas, numpy, matplotlib, sklearn

Concepts : Imputation

Machine Learning Algorithm : Decision Tree Regressor
