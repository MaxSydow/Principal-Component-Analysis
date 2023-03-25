# Principal-Component-Analysis

# Contents

[Investigative Question and Goal](#investigative-question-and-goal)

[Method Justification and Assumptions](#method-justification-and-assumptions)

Investigative Question and Goal

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


Method Justification and Assumptions


The item data frame is ordered by a unique indexed column, and contains no missing values or outliers. Essentially, we want to transform the way these columns are viewed. Orthogonality and linear independence are key concepts in linear algebra. In a plain 2-dimensional Euclidean space a line can be represented as a vector, and 2 lines are said to be orthogonal if they are perpendicular to each other. In this case the vectors are also linearly independent. (Anton, Ch. 5.3) Looking at 2 of the item columns as vectors, we can say that their respective values are independent of each other if they are orthogonal. In order to look at all 8 item columns, or any number of vectorizable columns like this a linear equation consisting of transformed vectors each having a multiplying coefficient can be calculated. (Anton, Ch. 7.2) The transformed vectors are called eigenvectors while the coefficients are called eigenvalues. In the context of PCA the eigenvectors are the principle components. The magnitude of the eigenvalues can be viewed as a weight for variability amongst the components. That is to say the larger the eigenvalue, the greater the variability of it’s corresponding principal component. Furthermore this allows us to look at the strength of variability of each original vector relative to it’s orthogonal transformation. This means we can quantitatively tell which item aligns the strongest with which principle component. Such a task would be mathematically arduous to perform by hand, but Python contains libraries that allow such analysis to be performed quickly.

Python's sklearn.decomposition package allows for fitting of a PCA model to original data. It also provides easy to use functions to compute component variances in an similar way that eigenvalues are computed. This allows for the use of these variances when reducing dimensions by componenets. In general the ranges of all original variables may not be the same. This can result in skewed variances and misalignment to principal components. For this reason it is best to scale each variable before fitting the PCA model. Sklearn has a standardscaler function that will transform each value so that the column means are 0 and standard deviation is 1. So, the assumptions of the data to be used for PCA are that each column be continuous, numeric and scaled. It does not make any predictions or clustering, but collapses the dimensionality of the dataset according to similarity of each column's variances.
