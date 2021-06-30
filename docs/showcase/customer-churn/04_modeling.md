# Modeling

Stage 4

Churn prediction modeling techniques attempt to understand the precise customer
behaviors and attributes which signal the risk and timing of customer churn.
The accuracy of the technique used is obviously critical to the success of
any proactive retention efforts.  The most common churn prediction models
are based on statistical and data-mining methods, such as logistic
regression and other binary modeling techniques.

Out data has been prepared, we will withhold a random sample of 10% of the data.
We will use this to evaluate the final model.

We use the PyCaret library.  We must set the dataset via the setup() function.
This requires that we provide the Pandas DataFrame and specify the name of
the column that contains the target variable. The setup() function also allows
you to configure simple data pipeline, such as scaling, power transforms,
missing data handling, and PCA transforms.

Next, we can compare standard machine learning models by calling the
compare_models() function. By default, it will evaluate models using 10-fold
cross-validation, sort results by classification accuracy, and return the
single best model. These are good defaults, and we don’t need to change a thing.

