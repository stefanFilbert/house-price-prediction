# House Price Prediction

In today's real estate market, both potential homebuyers and property owners face significant challenges. Homebuyers seek to find their dream homes within their budget, while property owners aim to price their homes competitively to attract potential buyers. In this context, accurate and data-driven house price prediction can play a pivotal role in assisting both parties in achieving their goals.

In order to solve that I use India House Price dataset that can be access from here: https://www.kaggle.com/datasets/howisusmanali/house-prices-2023-dataset

For the evaluation metric, I use Mean Average Error (MAE) because it addresses the specific characteristics of our project. It is robust to outliers, aligns with the assumption of a linear and constant cost of errors, and offers clear interpretability. By focusing on MAE, we aim to provide a reliable and easily understandable measure of our model's accuracy in predicting house prices, ultimately assisting stakeholders in making informed real estate decisions.

To predict the house price, we load the dataset that consists of 168446 rows and 20 columns. There are missing values on several variables and no duplicated rows in the data so no action is required.The variables type that contain missing values is categorical. In order that, we create new unique value that called "Other" to fill the missing value.

In the exploratory data analysis phase, we discover that most of the price variables are not close to the normal distribution. So, we use Spearman correlation since it is more suitable to determine the relationship between variables that are not normally distributed.

For feature engineering, we drop insignificant column such as property_id, and perform categorical variable encoding to convert them to numerical variables.

To split data and train model we use H2O AutoML. From train model, we take 2 model that is, top_model as model that has highest performance based on Mean Average Error (MAE) and best_model_overall as model that has highest performance overall models.

top_model MAE has 3836929.4640059024 which indicate that MAE of this model is relative high. So, this model suggesting that it's less accurate in predicting house prices.
