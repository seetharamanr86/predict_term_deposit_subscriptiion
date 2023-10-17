# predict_term_deposit_subscription
This repo contains ML model and analysis used for predicting the whether the client would subscribe to the term deposit.

This is a practical application assignment that focuses on using data analysis skills, in an effort to seek answer to the question, “Whether the client will subscribe to the term deposit?”.

Link to Explore Notebook: 

Data Used: https://archive.ics.uci.edu/dataset/222/bank+marketing

The data is related with direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be ('yes') or not ('no') subscribed.

The dataset collected is related to 17 campaigns that occurred between May 2008 and November 2010, corresponding to a total of 79354 contacts.

The classification goal is to predict if the client will subscribe (yes/no) a term deposit (variable y).

General Observation:

- We are able to get some idea about each columns knowing how many unique values exist.
- There are not many duplicate rows.
- Some of the columns include outliers are age,duration,campaign,pdays,previous,cons.conf.idx,euribor3m,etc.
- Function based on IQR determined and removed 26% of data based on the specified columns and iqr range.
- We could see the outliers are mostly removed.
- A small amount of data cleaned up ignoring short calls.
- Binary encoding has helped encode 4 columns ('default','housing','loan','y') with binary values. Also, the null values generated due to 'unknown' value has been addressed using mode value.
- A regular label encoding technique but instead label encoder from sklearn, we use a manual way to assign the mapping for multiple unique values.
- Ensured no null values after label encoding.

PCA analysis helps narrow down to the minimal number of features that contributes to the maximum impact on target feature. It involves the following steps.

Use standard scaler to scale all the features to the same scale.
Plot # of components against explained variance ratio to find until where it is effective.
PCA loadings are the coefficients of the linear combination of the original variables from which the principal components (PCs) are constructed. It helps identify which variables have the largest effect on each component.
Select top n features and prepare dataset for modeling.

Models:
- Logistic Regression
- Decision Tree
- K Neighbors
- SVC

Next Steps & Recommendations
Logistic Regression is the suggested model to use with this prediction problem.
Perform additional data exploration to understand the data better.
Data cleaning process has resulted in a significant loss of data. Try to reduce the percentage of upper and lower bounds that we have elimanted in the outliers.
Choose alternate feature selection techniques such as Random Forest Regressor to see how the model performs when a dataset is built using the resulting features.
Try using more combinations for hyper parameters and use a machine with high system capacity to run the models in short duration and arrive at a best hyper parameter list.

