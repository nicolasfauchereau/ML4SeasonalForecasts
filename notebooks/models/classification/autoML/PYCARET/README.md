# experiments with the AutoML framework [pycaret](https://pycaret.org/)

[pycaret](https://pycaret.org/) is intended to be the Python version of the widely used R package [caret](https://topepo.github.io/caret/)(Classification And REgression Training) 

## running the notebooks with [papermill](https://papermill.readthedocs.io/en/latest/)

[papermill](https://papermill.readthedocs.io/en/latest/) Papermill is a tool for parameterizing and executing Jupyter Notebooks.

This is an example of use, to run the Pycaret experiments using the lagged climate indices (NINO3.4, EMI [El Nino Modoki Index], IOD (Indian Ocean Dipole)) as inputs, with one month lag to realtime (i.e. the monthly or seasonal 
indices ending July 2019 used for the prediction of regional rainfall or temperature anomalies for the September - November 2019), for the prediction of seasonal rainfall tercile categories for the North of the North Island (NNI). 

The climate indices considered are: NINO3.4, EMI (El Nino Modoki Index), IOD (Indian Ocean Dipole), the SAM (Southern Annular Mode), the SPSD (South Pacific Subtropical index), 

The code and notebooks for derivation of all these indices (download of source datasets, processing and calculations) can be found at [this location](https://github.com/nicolasfauchereau/SeasonalBench/tree/main/notebooks/features_engineering/climate_indices/notebooks). 

The parameters are: 

- predictors = 'observed_climate_indices' # the type of predictors, in this case observed climate indices 

- max_features_lag = 20 # the maximum number of lags for the above predictors (how many months / seasons in the past are we going back to)

- lag_to_realtime = 0 # the lag to realtime, or the difference between the last month of the predictor and the first month of the predictand

- varname_target = 'RAIN' # the target variable 

- period_features = 'seasonal' # the period over which the features are aggregated, can be 'seasonal' or 'monthly' 

- period_target = 'seasonal' # the period over which the predictand is aggretaged, can be 'seasonal' or 'monthly' 

- region = 'WNI' # the region (NNI, WNI, ENI, NSI, WSI, ESI currently)

- target_col = 'cat_3' # the target category:, `cat_3` for tercile categories, `cat_5` for quintile categories

- dpath = '/home/nicolasf/research/Smart_Ideas_Final/outputs/tabular' # the folder where the inputs tabular data is to be found 


```
papermill autoML_pycaret_experiments_climate_indices_lagged_features.ipynb autoML_pycaret_experiments_climate_indices_lagged_features.ipynb -p predictors 'observed_climate_indices' -p max_features_lag 20 -p lag_to_realtime 1 -p varname_target 'RAIN' -p period_features 'seasonal' -p period_target 'seasonal' -p region 'NSI' -p target_col 'cat_3' -p dpath '/home/nicolasf/research/Smart_Ideas_Final/outputs/tabular'
```