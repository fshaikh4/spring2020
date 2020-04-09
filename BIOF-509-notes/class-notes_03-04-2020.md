class notes: 03/04/2020

# changing path
 - can run `%pwd` magick command from jupyter notebook
 - if not in the correct path, change to appropriate path via `pathlib`
  - `from pathlib import Path`

# data manipulation: numpy arrays
 - indexing: retrieving 1 value from array
  - `np_arr[1,1]` returns item in first row & first col of `np_arr` (since python end-index is not inclusive)
 - slicing: retrieving sequence or series object
  - `np_arr[:3,:3]` returns items in first 2 cols and first 2 rows of `np_arr` (since python end-index is not inclusive)
 - can use `:` or `...` with numpy to specify entire row/col
 - any way to get around throwing away colnames entirely with from pandas to numpy?
  - same it in a list: `names=pd_df.columns`

# data manipulation: pandas dataframes
 - `pd_df.iloc[]`: return item from given index (behaves as expected in numpy/python indices)
  - `pd_df.iloc[1:3]` returns 1st 2 rows, as it would with numpy arrays and standard python
  - in combined wine example: `w.iloc[2]` returns 3rd row (indexed by 2) only
 - `pd_df.loc[]`: return items from given name or index (does not behave as standard python & numpy indexing)
  - `pd_df.loc[1:3]` returns 1st 3 rows, differently than standard python and numpy arrays
  - in combined wine example: `w.ilocp[2]` returns 2 rows, both having '2' in the first/index col of dataframe

# handling missing values
 - 3 options: keep, drop, fill
  - each w/ own advantages and disadvantages
 - numpy missing value: `np.nan`
 - pandas missing value: `pd.NA`
 - `pd_df.dropna(axis=0)` drops rows of na values
  - `pd_df.dropna(axis=1)` drops cols of na values
 - `pd_df.fillna(0)` fills all missing values as 0

# filtering through data
 - can use boolean masks: `pH<3.2`
 - same b/w numpy array (via `np_arr[mask]`) and pandas dataframe (using either of `pd_df.loc[mask]` or `pd_df.iloc[mask]` `or pd_df[mask]`)

# matrix operations
 - primarily will be using numpy arrays
 - transpose: `M.T` gives transpose of `M`
 - dot product (i.e., matrix multiplication): `M.dot(M.T)` gives dot-product of `M` and `M.T` (M and its transpose)
  - alternative notation: `M@M.T`

# additional helpful commands
 - `pd_df.describe`
