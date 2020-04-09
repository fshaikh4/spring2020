class notes: 03/18/2020

# last week's class
 - data wrangling in `pandas`
 - `LabelBinarizer`: creates dummy variables (for 3+ options)
 - `OneHotEncoder`: create indicator "switch" variables (creates 1 more feature than necessary)
 - working w/ image or text data

# this week's class
 - training dataset
 - training a model/algorithm
 - perform predictions on new data

# supervised learning
 - data are labeled
 - classification: discrete outcome variable
 - regression: continuous outcome variable
   - linear regression
   - decision tree
   - nearest neighbors
   - random forest
   - gradient boosting
 - preventing overfitting
   - regularization: creating additional penalty (as part of ML algorithm's "cost function") that must be optimized
   - LASSO & Ridge for regression problems
   - will get to next class

# seaborn package
 - data visualization in python
  - jupyter-notebook trick: end python command with semicolon `;` to suppress non-plot output
  - shift+tab: shows default parameters for given function
 - heatmap: useful to visualize correlation coefficients
 - pairplot: scatterplot matrix of all pair-wise combinations of features, w/ distribution histograms on the main diagonal

# the regression problem
 - create $f_{w,b}(x)=wx+b$ such that we

## regression cost function
 - typically, will use mean-squared-error
 
 $$MSE=\frac{1}{N}\cdot\sum^N_{i=1}$$

 
## solving the regression optimization problem
 - gradient descent method: for each parameter of our model, take the partial derivative of the cost function
 - numerically: can update over multiple iterations, with the rate of convergence $\alpha$ as a hyperparameter
 $$w_{k+1}=w_{k}-\alpha\frac{\partial C}{\partial w}$$
 $$b_{k+1}=b_{k}-\alpha\frac{\partial C}{\partial b}$$

# linear regression in `sklearn`
 - following 3 steps in scikit-learn ML: instantiate, train, and score
 ```
 # instantiate
 ```
 
# "exponential regression"
 - `sklearn.preprocessing.PolynomialFeatures` (feature engineering)
 - some links that were shared:
   - [polynomial interpolation](http://scikit-learn.org/stable/auto_examples/linear_model/plot_polynomial_interpolation.html)
   - [polynomial features](http://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.PolynomialFeatures.html)
   - [linear regression](https://jakevdp.github.io/PythonDataScienceHandbook/05.06-linear-regression.html)
   - [feature engineering](https://jakevdp.github.io/PythonDataScienceHandbook/05.04-feature-engineering.html)

# evaluating a model
 - coefficient of determination $r$: amount of variance explained by a model
   - this is OK, but there are better ways
 - mean squared error (MSE): $MSE=\frac{1}{N}\cdot\sum\limits^N_{i=1}\left(\hat{y}_i-y_i\right)^2$
 - mean absolute error (MAE): $MAE=\frac{1}{N}\cdot\sum\limits^N_{i=1}|\hat{y}_i-y_i|$
 - median absolute error: more robust to outliers than mean absolute error

# how data normalization affects linear regression

 
# nearest-neighbor algorithm
 - regression is very sensitive to outliers: [Anscombe's quartet](https://en.wikipedia.org/wiki/Anscombe%27s_quartet)
 - alternative: k-nearest-neighbors (kNN) algorithm
