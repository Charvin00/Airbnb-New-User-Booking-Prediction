# Airbnb-New-User-Booking-Prediction

### To access given datasets: https://www.kaggle.com/c/airbnb-recruiting-new-user-bookings/data

## Data Science Final Write Up
Team: Avengers | Topic: Airbnb New User Bookings

(1) Introduction which explains the problem you are trying to address and why it's a big deal, 

This challenge from Airbnb ask us to predict the “Country Destination” that a new user will make as his or her first booking based on the given data sets.

We decided to choose this topic as all four of us are passionate about traveling as well as heavily users of Airbnb. It’s amazing that we could pitch in as part of the community, at the same time practice what we have learned in Data Science. 

(2) Details regarding the dataset used, how many rows, features, 

Here is the chart for raw dataset information in details: 



Referred to https://www.kaggle.com/c/airbnb-recruiting-new-user-bookings/data

Features:
train_users.csv - the training set of users
test_users.csv - the test set of users
id: user id
date_account_created: the date of account creation
timestamp_first_active: timestamp of the first activity, note that it can be earlier than date_account_created or date_first_booking because a user can search before signing up
date_first_booking: date of first booking
gender
age
signup_method
signup_flow: the page a user came to signup up from
language: international language preference
affiliate_channel: what kind of paid marketing
affiliate_provider: where the marketing is e.g. google, craigslist, other
first_affiliate_tracked: whats the first marketing the user interacted with before the signing up
signup_app
first_device_type
first_browser
country_destination: this is the target variable you are to predict
sessions.csv - web sessions log for users
user_id: to be joined with the column 'id' in users table
action
action_type
action_detail
device_type
secs_elapsed
countries.csv -
summary statistics of destination countries in this dataset and their locations
age_gender_bkts.csv 
summary statistics of users' age group, gender, country of destination
sample_submission.csv 
correct format for submitting your predictions
Referred to https://www.kaggle.com/c/airbnb-recruiting-new-user-bookings/data

(3) Methodology, which algorithm/s did you use? 

Algorithems:
Random Forest Regression
As an algorithm covered in the lecture, we selected random forest as our first approach.
Since the outcome of the project should be the predicted destination country, random forest can do the work of classification - prediction.

Random Forest is good because of its several features below:
It runs efficiently on large data bases
It can handle thousands of input variables without variable deletion
It gives estimates of what variables are important in the classification
It generates an internal unbiased estimate of the generalization error as the forest building progresses
It has an effective method for estimating missing data and maintains accuracy when a large proportion of the data are missing

Feature Extraction -> XGBoost
Considering the fact that the dataset is offered with additional data of sessions.csv, which is the web log of users. We consider that additional should also be valuable and helpful for the prediction.
We did additional work on preprocessing data, then selected XGBoost (eXtreme
Gradient Boosting) as our further approach on training the dataset. 
XGBoost (eXtreme Gradient Boosting) is one of the most loved machine learning algorithms at Kaggle. It uses gradient boosting framework and designed to “push the extreme of the computation limits of machines to provide a scalable, portable and accurate library.”
Gradient boosting is a machine learning technique for regression and classification problems, which produces a prediction model in the form of an ensemble of weak prediction models, typically decision trees. It builds the model in a stage-wise fashion like other boosting methods do, and it generalizes them by allowing optimization of an arbitrary differentiable loss function.


(4) Results, which metric did you use and why? What was the performance of your model on the test set?
We choose NDCG (Normalized discounted cumulative gain) as the metric to measure the performance of model. Because it is a measure of ranking quality. In information retrieval, it is often used to measure effectiveness of web search engine algorithms or related applications. For out scenario, it’s very similar to web search engine. We recommend the destination country to users based on their previous behavior. Also, Kaggle competition uses this metrics to evaluate predict result. 
Performance:
We used two ways to train models, the performance are as follows.


Naive Random Forest


XGBoost + Random Forest

