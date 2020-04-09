class notes: 02/19/2020

# Cisco WebEx
 - will now be used in this class
 - class

# gitignore file
 - added `.ipynb_checkpoints` to .gitignore file
 - why does this work just like `**/.ipynb_checkpoints`?
  - perhaps because it is a directory?

# anaconda environments
 - can run `!conda env list` in jupyterlab to list conda environments
 - additional possibilities to run commands in jupyter notebooks:
  - syntax: `!system_command` (system-specific)
  - syntax: `%magick_command` (cross-platform)

# pathlib
 - preferred way of interacting w/ paths (`import os` is deprecated)
 - `from pathlib import Path`
 - can create `Path` object: `p=Path()`
  - has `absolute()` method: returns absolute path of the `Path` object
  - can also use slash `/` ("operator overloading") to add to path
     - e.g., `p / 'dirname'`

# pandas
 - generally start with `import pandas as pd`
 - `pd.read_csv(p).head()`
  - creates `pandas.DataFrame` object from csv file stored at path `p`, and displays top 5 entries (or `tail` shows last 5 entries) of object
 - `df.apply(func)` method:
  - applies `func` function to all cells in `df`
 - can multiply entire dataframe by given scalar (integer or float): e.g., `df*2.5` or `df/2.5`
 - can at anytime access `numpy.array` from `pd.dataFrame` via `df.values()`

# scikit-learn datasets
 - `from sklearn import datasets`
 - `wine=datasets.load_wine()`
  - `type(wine)` returns `sklearn.utils.Bunch`
 - `df=pd.DataFrame(data=wine.data,columns=wine.feature_names)`

# python docstrings
 - triple-quoted string in a function
 - can access as `func.__doc__`
 - can also have `func.__annotations__` ("type hints" given as specified python types)
  - can use `pd.DataFrame` as type hint, after importing via `import pandas as pd`
 - can also access information via Shift+Tab when running command in ipython environment (incl. jupyter notebook)

# git remote
 - [documentation](https://www.neonscience.org/git-setup-remote): update local repo with changes to central repo
 - "remote": repo which is not our current working repo
 - `git remote add upstream URL`
  - we are calling our remote `upstream`
  - "upstream": production/official/central repo
 - `git remote -v`
  - `-v` is for verbose
  - shows information
 - `git stash`
  - put away files you don't want to commit right now(?)
 - `git pull upstream master`
  - pull changes from "upstream" repo, in the "master" branch
  - "rebase": have all edits to "upstream" be input into my fork's history FIRST, then add my changes
 - when finished working, use `git push origin master`
  - will push changes to "origin" repo, "master" branch

# python lists
 - step through list: `a[::3]` (steps through list, 3 at a time)
 - list comprehension: `[sin(x) for x in range(4)]`
 - `map` function: `list(map(sin,range(4)))`

# python naming conventions
 - python classes use "upper" camel case: `DataFrame`
  - as opposed to "lower" camel case: `dataFrame`
 - everything else pretty much in snake case: `variable_name`
  - for "constants", use screaming snake case: `CONSTANT_SHOULD_NOT_CHANGE`

# meetup
 - 
