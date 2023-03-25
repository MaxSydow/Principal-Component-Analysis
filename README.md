# Principal-Component-Analysis

# Contents

[Investigative Question and Goal](#investigative-question-and-goal)


Without customers an internet service provider (ISP) could not stay in business. Like many other businesses it is important to retain existing customers, especially in areas where competing ISPs are an option. Churn can be described as customer turnover, while tenure refers to how long a customer keeps their services.

Thoughts and perceptions can influence how long a customer stays, or even whether or not they leave. The Customer Churn data set contains 8 fields that describe customer sentiment. This set of columns consists of 8 prompts for customers to rate in terms of importance, and are labeled item1 through item8. The responses in these columns include numerical data. A response of 1 indicates most important, with 8 on the other end as least important. The items themselves are:

• item1: Timely response

• item2: Timely fixes

• item3: Timely replacements

• item4: Reliability

• item5: Options

• item6: Respectful response

• item7: Courteous exchange

• item8: Evidence of active listening

Predictive models can shed some light on the likelihood of churn, and forcast trends with tenure. Churn is a binary value, so a classification model would be appropriate. Tenure is continuous, and a regression model would be suited to make predictions. It might be worthwhile to find out if 8 prompts are actually necessary or even that useful when used in such models. Some people probably don’t mind responding to this many questions, but it may be a deterrent to others. Could it be possible to engage more customers if there were less aspects to rate? If so, which of these prompts can be justified in being removed, or perhaps consolidated? Principal component analysis (PCA) provides a mathematical and algorithmic means of grouping seemingly independent sets of values by variability. If certain items vary in a similar way this would indicate redundancy. Why have 2 or more items that are only going to give you the same trends?



