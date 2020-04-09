class notes: 02/12/2020

# spring 2020 repo
- fork into your own GitHub
- change README.md badges to point to your own repo (not the BIOF509 one)

# week 1 assignment
- import iris dataset (from sklearn)
- added usage of pandas dataframes
- created code to quickly remove spaces and parens in pd.df columns (allow us to use ". notation" interacting w/ df)

# `pathlib` library
```
from pathlib import Path
p=Path().home() #p='/home/user/'
p.absolute() #output: '/home/user/'
f=p/'conf.py' #output: '/home/user/conf.py'
```

# jupyter notebook
- `%lsmagick` in cell shows various tricks
- can export jupyter notebook as executable python script (uses lots of ipython commands, and creates everything else as comments)
- can use python help via shift-tab on a command

# using scikit-learn
- import "estimator" from `sklearn`
 - first step
- `SVC`: support vector machine classifier
 - this is a class within `sklearn.svm` module
 - `from sklearn.svm import SVC`
- instantiation step: create an instance of class
 - e.g., `svc=SVC()`
- fit step: fit estimator w/ data
 - e.g., `svc.fit(X,y)`
- predict step: predict using fitted estimator
- apparently doesn't matter if we use pandas series, pandas DataFrames, or numpy arrays as sklearn inputs
- sklearn requires 1D outcomes and 2D features
 - what if we want to use 1D features?
    - use double-bracket in pandas to allow 1D array to be treated as 2D object
    - e.g., `df[[sepal_length_cm]]` (dim will be 150x1)
    - alternatively, can use numpy reshape
- some other libraries (e.g., h2o, most R libraries, etc.) allow you to specify y-column without having to separate from X input data

# general python info
- syntax notes:
 - classes tend to be written in CamelCase
 - everything else written in snake_case
- object-oriented-programming (OOP):
 - class: set of instructions / general template
 - object: specific instance of the template
- help: `?command`

# regression versus classification
- regression: continuous outcome/target/response/label
- classification: discrete outcome/target/response/label
