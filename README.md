# ML4SeasonalForecasts
A set of Python modules and Jupyter notebook exploring the potential of Machine Learning for downscaling and bias-correcting seasonal climate forecast models

## Background 

All the code, notebooks and modules have been developped as part of the MBIE project C01X1813 ("Machine Learning approaches to downscale seasonal climate forecasts for
New Zealand") 

## Organisation 

This repository is organized in different sections, each covering a distinct aspect of the processing and modeling pipelines allowing to explore Machine Learning approaches for the downscaling of monthly and seasonal climate forecasts from Atmospheric and Coupled General Circulation Models (GCMs), as well as from observational datasets (such as realtime Sea Surface Temperature datasets) and climate indices. 

#### download

This module handles the retrieval of all GCM outputs as well as various observational and reanalysis datasets used for the validation / verification of these forecasts 

#### processing 

This module contains various functions used to process the data 

#### verification 

Module for the verification (or validation) of the GCMs monthly and seasonal forecasts against observations and reanalysis, leverages the libaries [climpred](https://climpred.readthedocs.io/en/stable/) and [xskillscore](https://xskillscore.readthedocs.io/en/stable/)

#### target 

This module handles the generation of the continuous (for regression tasks) and discrete (for classification tasks) time-series of target (predictand) time-series from gridded datasets (with focus on the New Zealand Virtual Climate Station Network) 

#### reduction 

This module and associated notebooks (in the 'notebooks' folder) contains functions and experiments aiming at comparing different dimensionality reduction methods, applied to the multi-variate, multi-dimensional GCMs forecast data 

#### ensemble 

This module, and the associated notebooks, explore ensemble learning approaches (bagging, boosting, etc) for the downscaling of the GCM forecasts 

#### DL 

This module, and the associated notebooks, explore Deep Learning  (including Convolutional Neural Networks) approaches to the dowscaling problem. 

#### statistical 

This module, and the associated notebooks, is devoted to purely 'statistical' approaches, where the predictors are taken from realtime or near-realtime observational datasets instead of derived from the GCMs forecasts. 









