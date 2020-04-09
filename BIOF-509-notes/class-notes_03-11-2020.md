class notes: 03/11/2020

# how to pull data from remote web servers
 - option 1: `urllib` package
  ```
  import urllib
  
  URL='https://some_url.here'
  FILENAME='some_file_name.tar.gz'
  
  urllib.request.urlretrieve(URL,FILENAME)
  ```
 - option 2: `requests` package (for JSON files)
  - used for more sophisticated APIs to extract data
 - option 3: sql
  ```
  import sqlalchemy as sa
  
  engine=sa.create_engine('mysql+pymysql://genome@genome-mysql.cse.ucsc.edu')
  
  sql_command="""SELECT *
                 FROM snp147Common
                 WHERE chrom='chrY'
                 LIMIT 3
              """
  
  pd.read_sql(sql_command,engine)
  ```

# useful tools to interact w/ databases
 - learn sql "on-the-job": helps you remember
 - some tools to learn sql:
  - pandasql: translates pandas commands into sql code
  - dbplyr: translates dplyr into sql code
     - dtplyr: translates dplyr into data table code

# preparing data for ML
 - handle missing values:
 - data wrangling: changing format of data
 - combinind data from several sources (e.g., w/ pandas)

# imputing missing data
 - scikit-learn has data imputation tools: `sklearn.impute.SimpleImputer`
 - after imputation, ensure data distribution remains relatively unchanged
 - categorical data: mode/most-frequent, kNN (`sklearn.impute.KNNImputer`)
  - to prevent from creating level that does not exists (e.g., 0 and 1 mean is 0.5)
  - ensure **k is an odd number** (so no ties and averaging)

# scikit-learn tools
 - estimators: `KNClassifier`, `KNRegressor`
  - methods: `fit`, `predict`, `score`
 - transformers: `SimpleImputer`, `KNNImputer`, `OneHotEncoder`
  - methods: `fit`, `transform`, `fit_transform`

# selecting columns in pandas: 1 vs 2 square brackets
 - 2 square brackets: data frame
 - 1 square bracket: series (same dim as squeezed numpy.array: 1D)

# data normalization
 - z-score standardization: `sklearn.preprocessing.StandardScaler`
 - min-max scaling: `sklearn.preprocessing.MinMaxScaler`
 - kNN: requires data be on the same scale, or will not function correctly

# data centering
 - subtract scaler from all values within a col, to make the mean 0 (does not affect model performance)
 - does not usually affect model performance
 
