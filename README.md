![alt text](churn_image.jpeg)


## Business Understanding
SyriaTel, a telecommunications company, faces a significant challenge with customer churn, where a significant portion of their customer base is leaving. This not only results in lost revenue but also increases the cost of acquiring new customers to replace those who churn. Given the competitive nature of the telecommunications industry, retaining existing customers is often more cost-effective than acquiring new ones. Therefore, reducing churn is vital for sustaining revenue streams, enhancing profitability, and maintaining market share.

The goal of this project is **to develop a predictive model that can accurately identify customers who are at risk of leaving the service in the near future**. 
By leveraging data-driven insights, SyriaTel can better understand the factors driving customer churn and implement targeted interventions to retain at-risk customers. These interventions might include personalized offers, enhanced customer support, and proactive engagement strategies, which are essential for reducing churn rates and increasing customer lifetime value.

Moreover, a deep understanding of churn patterns will enable SyriaTel to optimize its marketing and operational efforts, ensuring that resources are allocated effectively. The insights derived from this analysis will not only help in improving customer loyalty but will also support long-term strategic planning and decision-making, providing SyriaTel with a competitive edge in a crowded market.

### Objectives : 
1. **To develop a predictive model that can accurately identify customer churn.**
2. To Identify key drivers of churn
3. Accurately predict at-risk customers.
4. Measure Impact of Retention Strategies.

## Data Understanding
This project utilizes [this dataset from kaggle.](https://www.kaggle.com/datasets/becksddf/churn-in-telecoms-dataset). Each record is a customer
This dataset contains 3333 records and 21 columns.

The dataset contains a variety of features: 
* `state` - categorical variable denoting the state a customer is registered in.
* `account length` - The duration of the customer's account in terms of days.
* `area code` - The area code associated with the customer's phone number.
* `international plan` -  Whether the customer has an international calling plan (Yes/No).
* `voice mail plan` -  Whether the customer has a voice mail plan (Yes/No).
* `number of voicemail messages` - The number of voicemail messages the customer has.
* `total day minutes` - The total number of minutes the customer used during the daytime.
* `total day calls` - The total number of calls made by the customer during the daytime.
* `total day charge` - The total charge for daytime usage.
* `total evening minutes` - The total number of minutes the customer used during the evening.
* `total evening calls` - The total number of calls made by the customer during the evening.
* `total evening charge` - The total charge for evening usage.
* `total night minutes` - The total number of minutes the customer used during the night.
* `total night calls` - The total number of calls made by the customer during the night.
* `total night charge` - The total charge for night usage.
* `total international minutes` - The total number of international minutes used by the customer.
* `total international calls` - The total number of international calls made by the customer.
* `total international charge` - The total charge for international usage.
* `number of customer service calls` - The number of customer service calls made by the customer.
* `churn` - The target variable indicating whether the customer has churned or not (Yes/No).

For this project, we are trying to predict `Churn`, hence it is our target variable.

## Modeling
The goal of this project is to predict which customers are at a risk or churning in the near future. Since this entails classifying a customer into `Churn` or `Not Churn`, it is a **classification** problem. 

To achieve this target, we are going to use the following algorithms:
* Logistic Regression
* Decision Trees

We iteratively seek  to improve the performance of these models using hyperparameter tuning. This model will be evaluted using recall and the AUC (Area Under the Curve) metrics since the  cost of missing a churner is higher than falsely identifying a non-churner as one. Moreover, it is pertinent to balance between the false positives and false negatives.

## Evaluation

For this model, we use a customized cross-validation function to evaluate the different models. The best model for this project achieved a recall score of 69%. The model correctly identifies 69% of the churners.

Moreover, with an AUC of 79%, the model has a good ability to distinguish between churners and non-churners. 

The model has a moderate F1-score suggests that there may be a significant number of false positives or false negatives, impacting the overall effectiveness of the model.

## Findings and Conclusions
1. A recall of 69% means that the model correctly identifies 69% of the customers who actually churn. The model is relatively effective at identifying churners, but it still misses about 31% of actual churners (false negatives). This could lead to missed opportunities for retention efforts.
2. An AUC of 0.79 indicates that the model has a good ability to distinguish between customers who will churn and those who will not. While not as strong as a model with an AUC closer to 1.0, it still suggests that the model performs reasonably well at ranking customers by their likelihood to churn.
3. With an F1-score of 64%, the model strikes a balance between capturing true churners (recall) and ensuring that the identified churners are indeed likely to churn (precision). However, the moderate F1-score suggests that there may be a significant number of false positives or false negatives, impacting the overall effectiveness of the model.


## Recommendations

1. **Enhance Retention Strategies**: With a recall of 69%, the model successfully identifies a majority of customers who are likely to churn. However, it misses about 31% of actual churners. To address this, consider implementing targeted retention strategies for those not identified by the model. This might involve monitoring at-risk customers more closely or improving the model to capture a larger portion of potential churners.
2. **Prioritize High-Risk Customers**: The AUC of 0.79 indicates that the model performs well in distinguishing between customers who are likely to churn and those who are not. Leverage this ability to prioritize customers with a high likelihood of churn for retention efforts. Focus marketing and customer service resources on these high-risk customers to maximize the impact of retention initiatives.
3. **Monitor Model Performance**: Continuously monitor the model's performance over time. As customer behavior changes, the model may need adjustments to maintain its effectiveness. Regularly track key metrics like recall, AUC, and F1-score, and be prepared to retrain or recalibrate the model as needed.