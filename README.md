# Telecom Industury Churn

# Introduction:
This project aims to predict customer churn in the telecom industry. The goal is to identify customers who are likely to churn so that the telecom company can take proactive steps to retain them. In this readme file, I provide an overview of the problem statement, the data used, the approach, and the results obtained.

# Problem Statement:
In the telecom industry, customers are able to choose from multiple service providers and actively switch from one operator to another. In this highly competitive market, the telecommunications industry experiences an average of 15-25% annual churn rate. Given the fact that it costs 5-10 times more to acquire a new customer than to retain an existing one, customer retention has now become even more important than customer acquisition.
For many incumbent operators, retaining high profitable customers is the number one business goal.
To reduce customer churn, telecom companies need to predict which customers are at high risk of churn.
In this project, you will analyse customer-level data of a leading telecom firm, build predictive models to identify customers at high risk of churn and identify the main indicators of churn.

# Understanding and defining churn: 
There are two main models of payment in the telecom industry - postpaid (customers pay a monthly/annual bill after using the services) and prepaid (customers pay/recharge with a certain amount in advance and then use the services).
In the postpaid model, when customers want to switch to another operator, they usually inform the existing operator to terminate the services, and you directly know that this is an instance of churn.
However, in the prepaid model, customers who want to switch to another network can simply stop using the services without any notice, and it is hard to know whether someone has actually churned or is simply not using the services temporarily (e.g. someone may be on a trip abroad for a month or two and then intend to resume using the services again).
Thus, churn prediction is usually more critical (and non-trivial) for prepaid customers, and the term ‘churn’ should be defined carefully.  Also, prepaid is the most common model in India and Southeast Asia, while postpaid is more common in Europe in North America.
This project is based on the Indian and Southeast Asian market.


# Data Preparation:

The following data preparation steps are crucial for this problem:

1. Filter high-value customers
As mentioned above, you need to predict churn only for high-value customers. Define high-value customers as follows: Those who have recharged with an amount more than or equal to X, where X is the 70th percentile of the average recharge amount in the first two months (the good phase).
After filtering the high-value customers, you should get about 30k rows.

2. Tag churners and remove attributes of the churn phase
Now tag the churned customers (churn=1, else 0) based on the fourth month as follows: Those who have not made any calls (either incoming or outgoing) AND have not used mobile internet even once in the churn phase. The attributes you need to use to tag churners are:
total_ic_mou_9
total_og_mou_9
vol_2g_mb_9
vol_3g_mb_9
After tagging churners, remove all the attributes corresponding to the churn phase (all attributes having ‘ _9’, etc. in their names).
The dataset contains information about customers of a telecom company, including their demographic information, call records, and billing information.

# Modelling:

Build models to predict churn. The predictive model that you’re going to build will serve two purposes:
It will be used to predict whether a high-value customer will churn or not, in near future (i.e. churn phase). By knowing this, the company can take action steps such as providing special plans, discounts on recharge etc. It will be used to identify important variables that are strong predictors of churn. These variables may also indicate why customers choose to switch to other networks.
In some cases, both of the above-stated goals can be achieved by a single machine learning model. Also, since the rate of churn is typically low (about 5-10%, this is called class-imbalance) - try using techniques to handle class imbalance.
Therefore, build another model with the main objective of identifying important predictor attributes which help the business understand indicators of churn. A good choice to identify important variables is a logistic regression model or a model from the tree family. In the case of logistic regression, make sure to handle multicollinearity.
After identifying important predictors, display them visually - you can use plots, summary tables etc. - whatever you think best conveys the importance of features.
Finally, recommend strategies to manage customer churn based on your observations.

# Results:
The results of the project include the following:

A prediction model for customer churn in the telecom industry.
Evaluation metrics for the selected model.
Insights into the factors that influence customer churn in the telecom industry.
Conclusion:
In this project, we developed a prediction model for customer churn in the telecom industry. The model can be used by the telecom company to identify customers who are likely to churn and take proactive steps to retain them. The insights from the project can help the telecom company to improve customer retention and reduce churn.
