# MLB_Digital_Engagement1 - LightGBM Notebook

## The LGBM_model notebook is the main notebook of the project.

A model that can predict daily MLB fan engagement given a wide range of variables t+1 day in advance. This Kaggle competition project challenged me thru working with a large volume of data that needed to be organized and put into a dataframe. Joining the dataframes together for TTS required planning and knowing the specifics of the pd.merge, pd.concat, and pd.join methods. LightGBM was chosen first because of its iterative approach, minimization of the loss function and its computational lightness. Domain knowledge was used to select the features that would help predict daily fan engagement. Out of the 50-60 features in the 6 csv's, I chose:

* awards and date given
* stats such as RBI, AB, HR

These features will drive MLB fan engagement because of:

* excitement 
* sporting highlights
* excellence in the sport

The AWARDS.ipynb, EVENTS.ipynb, Standings.ipynb, PlayerEnagagmentTarget4.ipynb, season_EDA.ipynb contain the derived dataframes from which the .csv's were organized into. The dfs were pickled into the main notebook where the modelling took place.

Lowest MAE (so far):

*0.897

Lowest RMSE (so far):

*4.1

Competition eval metric (MAE)
mean across 4 targets: 
* 0.999
