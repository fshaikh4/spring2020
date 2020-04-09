class notes: 04/08/2020

# class activity
 - use last class's code for hyperparameter optimization of random forest regressor to optimize gradient boosting regressor
 - ### what are we looking at? (numbers that are different colors)
   - can access by checking estimator's `score` method:
     ```
     ?gbr.score
     Signature: gbr.score(X, y, sample_weight=None)
     Docstring:
     Return the coefficient of determination R^2 of the prediction.

     The coefficient R^2 is defined as (1 - u/v), where u is the residual
     sum of squares ((y_true - y_pred) ** 2).sum() and v is the total
     sum of squares ((y_true - y_true.mean()) ** 2).sum().
     The best possible score is 1.0 and it can be negative (because the
     model can be arbitrarily worse). A constant model that always
     predicts the expected value of y, disregarding the input features,
     would get a R^2 score of 0.0.
     ...
     ```
   - also found the `criterion` of `gbr` to be "Friedman MSE"
    - in simple terms: a weighted form of MSE
    - everything in gradient boosting machines is apparently in some way weighted
    - found more specific information from a [StackOverflow answer](https://datascience.stackexchange.com/a/66063)
 - ### ideas for my project
   - plot my model's balanced accuracy using hyperparameter search heatmap?
   - could limit to 2 hyperparameters to get a better idea of what's going on: `max_depth` and `n_estimators`?

# why do we do cross-validation?
 - to have a more robust estimate of our model's "true" performance
 - also somehow deals with overfitting issue of training and testing on same data (training data split)
 - provides us an opportunity to tune our hyperparameters
 - ### stratified k-fold cross-validation
   - important in cases where we may struggle with minority class representation in all cross-validation folds
   - i.e., classification with highly imbalanced data

# hyperparameter tuning
 - grid search: exhaustive (what we are doing)
 - random search: picks points at random from grid search space
 - Bayesian: look at results from current hyperparameter values, update (priors?), and see "if we're getting closer"

# brief discussion of classification
 - many aspects same as work we have been doing for regression
 - classification does have some of its own "special topics" we will get to later
   - e.g., ROC curves, PR curves, etc.

# final project discussion
 - typical project: find dataset, explore dataset, and try a few models
 - "unsupervised learning is cool too!"
 - criteria for grading: 3-steps to an A+
   1. do you have plot(s)?
   2. do you fit model(s)?
   3. did you explain what you did?
 - Q: can we document final project in MS Word?
   - will be performing some heavy computing outside of jupyter notebooks
   - A: this is fine
 - Q: how long for final project presentations?
   - A: 5min, but he will not cut us off
 - Q: do we need a final report for our project? or is final presentation fine?
   - A: looking for presentation + some sort of documentation of what you did
   - jupyter notebooks are great for this, but use MS Word if you want

 
