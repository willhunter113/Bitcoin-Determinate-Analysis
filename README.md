# Bitcoin Analysis

*authors*: Will Hunter

*Introduction*

Data Analytics 401 senior capstone project about the relationship between macroeconomics and Bitcoin. The analysis aims to find correlations between the macroeconomic landscape of the United States and the volatility of a common cryptocurrency Bitcoin. I believe this anysis is important for retail investors to see if bitcoin has any correlation to the largest economy in the world; Moreover, it is important to compare the price movements of Bitcoin to other assets, such as stock indicies, which we know are tied to our economy. 

*Methods*

The project aims to do an analysis on the macroeconomic variables correlation to Bitcoin, as well as three of the major United States stock indices (the S&P 500, Dow Jones Industrial Average, and the Nasdaq Composite). The two sections of the analysis are variable selection and the predictive models. The variable selection process consists of using LASSO regression and Random Forests in r to find important variables in predicting the assets. The variables will then be qualitatively analyzed to compare and contrast the important variables for each of the assets. The predictive model is a Long Short-Term Memory (LSTM) neural network conducted in python. Metrics (RMSE and MAE) will then be used to evaluate how the models perform and if there is correlation between the macroeconomic variables and Bitcoin, and how this correlative compares in magnitude to that of the stock indices.

*Data*

The data being used in this study is a combination of economic metrics, as well as consumer opinion data. The economic metrics were compiled from the Federal Reserve Fred Database via the Nasdaq Data Link API and Quandl package in r. The pricing data of the three indices and bitcoin was obtained through the Bloomberg terminal database. The consumer data was obtained from the University of Michigan also using the Nasdaq Data Link API and Quandl package in r. The consumer data has been deidentified by the University of Michigan befor ebeing released to the public so there are not personal information ethical concerns and an IRB was not neccessary for the study. Both data sets have been published for use by the public given a proper citation in the work that stems from it. Some of the data sources do require you to set uo a free account to access the data. The data can be reached from the following links:

FRED: https://data.nasdaq.com/data/FRED-federal-reserve-economic-data

U of M: https://data.nasdaq.com/data/UMICH-consumer-sentiment

*Packages*

R packages to use:
- Quandl
- dplyr
- lubridate
- caret
- Hmisc
- tidyverse
- corrplot

Python packages to use:
- tensorflow
- from tensorflow: keras
- from keras: Sequential, layers, callbacks
- from keras layers: Dense, LSTM, Dropout, GRU, Bidirectional
- from keras callbacks: ModelCheckpoint
- from keras losses: MeanSquaredError
- from keras metrics: RootMeanSquaredError
- from keras optimizers: Adam
- pandas 
- numpy
- from matplotlib: pyplot

*Data Files*

- Indexdata.csv: Pricing data collected from the Bloomberg Terminal Database on the 3 stock indices and Bitcoin
- BtcoinData.csv: Cleaned & aggregated dataset for analysis from all 3 data sources
- BitcoinPredictive.csv: Data for bitcoin predictive model cleaned from varibale selection proccess 
- SP500Predictive.csv: Data for S&P 500 predictive model cleaned from varibale selection proccess
- NasdaqPredictive.csv: Data for Nasdaq predictive model cleaned from varibale selection proccess
- DowPredictive.csv: Data for Dow Jones Industrial Average predictive model cleaned from varibale selection proccess
- BitcoinTrainResults: Train predictions and actual data from bitcoin predictive model used for visuals after the models are conducted
- BitcoinTestResults: Test predictions and actual data from bitcoin predictive model used for visuals after the models are conducted
- SPTrainResults: Train predictions and actual data from S&P 500 predictive model used for visuals after the models are conducted
- SPTestResults: Test predictions and actual data from S&P 500 predictive model used for visuals after the models are conducted
- DowTrainResults: Train predictions and actual data from Dow Jones Industrial Average predictive model used for visuals after the models are conducted
- DowTestResults: Test predictions and actual data from Dow Jones Industrial Average predictive model used for visuals after the models are conducted
- NasdaqTrainResults: Train predictions and actual data from Nasdaq predictive model used for visuals after the models are conducted
- NasdaqTestResults: Test predictions and actual data from Nasdaq predictive model used for visuals after the models are conducted

*Code Files*

Stage 1 (R)

Data Cleaning file that will pull all of the data from through Nasdaq API, clean the consumer data so it can be used in the analysis, and aggregate all data together into the "BitcoinData.csv" file.

- DataCleaning.Rmd

Stage 2 (R)

Variable selection files for each of the 4 assets being studied. Includes testing of LASSO regression assumptions, LASSO regression on full and subset data, and Random forest algorithms for each asset. Aggregates the important variables from algorithms into a subset of "BitcoinData.csv" named "___Predictive" for each asset. This data file is used in the predictive model.

- BitcoinVarSelection.Rmd
- S&PVarSelection.Rmd
- DowVarSelection.Rmd
- NasdaqVarSelection.Rmd

Stage 3 (Python)

LSTM model files that include 2 LSTM models. Model 1 is a simple single layer LSTM neural network. Model 2 is a multi-layered LSTM neural network. The variable selection output data is reshaped to fit the requirements of the LSTM model and scaled. The models are set up and executed. Metrics from the best model are produced and the best model created is saved for further use to the datafile. 

- LSTMBitcoin.ipynb
- LSTMSP500.ipynb
- LSTMDowJones.ipynb
- LSTMNasdaq.ipynb
- FinalPlots.ipynb


