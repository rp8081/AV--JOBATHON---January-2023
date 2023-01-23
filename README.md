### Problem Description

In this hackathon , we were supposed to predict cltv (customer lifetime value) based on following charateristics :- 

['gender',
 'area',
 'qualification',
 'income',
 'marital_status',
 'vintage',
 'claim_amount',
 'num_policies',
 'policy',
 'type_of_policy']
 
 
### Customer Life Time Value

CLTV stands for "customer lifetime value." It is a measure of the total amount of money a customer is expected to spend on a company's products or services during their lifetime. It is used to evaluate the potential profitability of acquiring a new customer and to inform marketing and sales strategies. Businesses such as e-commerce, subscription-based services, and retail often use this metric.

There are several ways to model customer lifetime value (CLTV), but some common methods include:

Historical data analysis: This involves looking at the past purchase behavior of customers to predict future spending. This method is useful for businesses with a long history of customer data.

Cohort analysis: This involves grouping customers based on when they became customers and analyzing the spending patterns of each group. This method can help identify trends in customer behavior over time.

Predictive modeling: This involves using statistical techniques such as regression analysis or machine learning to predict future spending based on past data and other customer characteristics.

RFM analysis : Recency, Frequency, Monetary analysis. It is a technique that uses the customer's purchase history to segment them into groups, based on how recently they made a purchase, how often they make a purchase and how much they spend.

Discounted Cash Flow (DCF) : It is an estimation of the value of an investment based on the present value of future cash flows it is expected to generate.

It's worth noting that the best method will vary depending on the type of business and the data available, and it's important to validate the model using a holdout sample or other methods to ensure its accuracy.

#### In this hackathon our focus was on Predictive modeling.

**Approach:**

- **Data Exploartion :**
  - Data did not require much of the cleaning/outlier treatmnet.
  - Most of the variables were categorical in nature .
  - The target variable was positively skewed . Tried modelling with log transformation and also with box cox specific transformation. But did not help


- **Data Preprocessing and Feature Engineering:**
  - Tried Adding more features by combining categorical features . But it did not help .
  - A new feature using claim amount/vintage was derived and used .
  -  Claim amount was binned using the percentile values and this binned varaible was used into modelling . 
  - Finally I did k-mode clustering on categorical variables and this was used as a variable in model .
  - Tried Various Encoding like Label Encoding , One hot encoding . Finally One hot encoding performed better with GBM and Ridge model while for LGBM
     Variables were passed directly ( LGBM does internal encoding for these variables)

- **Modelling :**
  - Tried various models like Xgboost , Catboost,LGBM,Random forest , Linear model with regularization  (Lasso , Ridge) and Deep Learning Models. Finally selected Ridge,LGBM and GBM models
     For Submission. 
- **Final Model:**
  - Blended LGBM , Ridge , and GBM with weight of 0.6,0.2 and 0.2 .


 
