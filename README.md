# MLB_Digital_Engagement1 - LightGBM/LSTM Notebook

## The Final_NB.ipynb is the LightGBM notebook of the project.
## The FinalNB_NN.ipynb is the LSTM notebook of the project


<img src='images/Screen Shot 2021-07-23 at 4.17.42 PM.png' width='125' > 


A model that can predict daily MLB fan engagement given a wide range of variables t+1 day in advance. This Kaggle competition project challenged me thru working with a large volume of data that needed to be organized and put into a dataframe. Data was organized and preprocessed. Joining the dataframes together for TTS required planning and knowing the specifics of the pd.merge, pd.concat, and pd.join methods. LightGBM was chosen first because of its iterative approach, minimization of the loss function and its computational lightness. Domain knowledge was used to select the features that would help predict daily fan engagement. Out of the 50-60 features in the 6 csv's, I chose:

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

<img src='images/Screen Shot 2021-07-21 at 5.45.09 AM.png'>  
<img src='images/Screen Shot 2021-07-21 at 5.45.25 AM.png'>
<img src='images/Screen Shot 2021-07-21 at 5.45.42 AM.png'>
<img src='images/Screen Shot 2021-07-21 at 5.45.56 AM.png'>  Most engagement scores are <= 20

Competition eval metric (MAE)
mean across 4 targets: 
* 0.999

The next model tested was a LSTM NN. This model uses a masking layer. A masking layer is necessary because there were a lot of Nan values in data which was converted to 0.0 during data cleaning. The masking layer will treat these values as non-factors during fitting. 2 LSTM layers + 1 dense layer + 1 output layer completes the LSTM NN. The batch size used for training was 50,000 while the entire dataset was +6 million rows. It ran for about 6-7 epochs before the loss function was stablilized and training halted. I also grouped out a validation set of +1 million datapoints while 5 million was for train/test. The predictions on our test data was mediocre while our validation data was predicted much better. There may be some bias in our model because we have only 7 features (simple model). 
