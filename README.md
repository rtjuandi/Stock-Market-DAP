# Stock-Market-DAP
In this project, we would apply different machine learning models on various datasets to analyze the stock market. Datasets used are listed at the bottom.

# Findings
##DAP2: Data Pre Porcessing and Exploratory Data Analysis##
We attempted to clean out any redundant data by checking if an entry consists of any cell that does not have a numerical value by checking if an attribute is equal to np.NaN for each dataset. Fortunately for us all our value datasets are clean and all entries are valid.

We plotted close price, open price, low price, high price, and volume to the date and looked at the trends for S&P500 prices.
We found that all of the prices had the same trend, however, the volume of the S&P 500 did not directly correlate to the prices.

Further, we plotted the closing price of a company from each sector and found out that most of the companies price movements are pretty similar despite being in different sectors.

Amazon however had more drastic price movements with its prices increasing rapidly over the years. This is not due to the sector it is in. We plotted the closing price of Amazon and another relatively large company in the same sector, Nordstrom and realized that Nordstrom’s price movements are relatively similar to the other companies.

##DAP3: Classification##
**Decision Trees:**\
Performance:
●	60 - 70% accuracy

Technical Indicators:
●	Relative Strength Index (RSI) -> Shows overbuying and overselling
●	Estimated Moving Average (EMA)
●	Moving Average Convergence Divergence (MACD) 
●	Average True Range (ATR) 

Indicator Rules:
EMA signals:
Buy: shorter-term EMA (EMA12) moves above a longer-term EMA (EMA26)
Sell: short-term EMA (EMA2) moves below a longer-term EMA line (EMA26).

MACD signals:
Signal Crossover, Zero Crossover

Optimal Parameters: leaf depth = 5, 30% test set

**k-NN**\
Performance:
●	55 - 65% accuracy

Optimal Parameters: k-neighbors = 1, 30% test set
	

**Naive Bayes**\
Performance:
●	50 - 60% accuracy
Attributes:
●	Follow (whether or not if the stock is following an Upward or Downward trend i.e. going up or down multiple days in a row)
●	Strength of Percent Change (how much the stock price changed in a day)

Prediction:
●	Movement (if the stock price went Up or Down since the last closing price)

Overall, our accuracies usually sit in the 45 - 70 percent range across all classification algorithms. For decision trees the accuracy range is about 60% - 70% which was likely a result of using technical indicators to make the decisions. Our most accurate test was the Gini decision tree, although the entropy decision tree was a close second being less than one percent off. Stocks are generally very hard to predict, and it is almost impossible to predict random events that may happen to a company. Furthermore stocks are a result of human buying and selling and it is very difficult to predict human behaviour accurately. Machine learning could be used to aid making decisions on whether to buy or sell a stock but should not be used on its own to make a decision.

Note: For the decision trees we used Ta-Lib to calculate the technical indicators for the stocks.

##DAP4: Regression##
Linear Regression (Multivariate, Ridge, Lasso):
We conducted several linear regression models on our S&P 500 Dataset.

For multivariate linear regression, we got a Coefficient of Determination of 0.994 on our test set. This shows that it closely fits the linear regression line
For Ridge Regression and Lasso Regression we found that the regularization parameter being 0 yields the best result. This shows that an ordinary least square regression line is sufficient enough. 

This is probably because S&P500’s price is constantly going up over the years and not very volatile.

Gradient Descent:
Our data covers a wide range as the cost of the S&P 500 stock constantly increased over the 5-year span we are studying. This accounts for our graphs being hard to read as the data covers a range of about $1500 - $2800. We also had to make our learning rate much smaller as the optimal rate was around 0.00000001. The data never fluctuate making our plots trend very linearly in a positive direction.

Polynomial Regression Model:
We came across a similar output for a polynomial regression model. The R2 score is best at 0.994 with a degree of 1. We tried a degree of 2 and the R2 score is 0.990.
Again, this is probably the because S&P500 is not very volatile and the price is constantly increasing across the years.

Investing in S&P 500 and holding it long term would be a low risk investment as the prices are predicted to go up in years.

##DAP5: Neural Networks##
**Neural Network Models:**\
We used the time series data set similar to the one we did for regression. However, instead of using the S&P 500 dataset, we decided to use Apple because the prices are better scaled than the S&P 500 prices. We forecasted for 10 days out instead of 1 day which we did for linear regression. 

We used two hidden layers with 100 neurons each for our neural network models using Keras. After several tests, we found out that the most optimal optimizer for our problem was the Adam optimizer.

Each activation function resulted in differing results. Especially the loss value.

Loss Values for Each Function:
  Relu: 0.000773726380430162
  Tanh: 0.0027320224326103926
  Sigmoid: 0.0012143859639763832

For our case, the Relu activation function seems to work best for us.

**Hyper-Parameter Tuning:**\
We conducted hyper-parameter tuning to find our best, most optimal parameters. These are our results:

Best Params:
		Learning Rate: 0.0008763224455697141
		Num of Hidden: 1
		Num of Neurons: 47

Best score: -0.006228178758950283
Model evaluation score: 0.0012143859639763832


# Datasets

**SP500_Prices**\
Dataset contains time-series of S&P500 prices from 2013 to 2018. Contains 1259 entries with 7 attributes.

|Date|Open|High|Low|Close|Adj Close|Volume|
|---|---|---|---|---|---|---|
|2013-02-08|1509.390015|1518.310059|1509.390015|1517.930054|1517.930054|2986150000|
|2013-02-11|1517.930054|1518.310059|1513.609985|1517.010010|1517.010010|2684100000|
|2013-02-12|1517.010010|1522.290039|1515.609985|1519.430054|1519.430054|3414370000|
|2013-02-13|1519.430054|1524.689941|1515.930054|1520.329956|1520.329956|3385880000|
|2013-02-14|1520.329956|1523.140015|1514.020020|1521.380005|1521.380005|3759740000|
| ... | | | | | | |
|2018-01-31|2832.409912|2839.260010|2813.040039|2823.810059|2823.810059|4261280000|
|2018-02-01|2816.449951|2835.959961|2812.699951|2821.979980|2821.979980|3938450000|
|2018-02-02|2808.919922|2808.919922|2759.969971|2762.129883|2762.129883|4301130000|
|2018-02-05|2741.060059|2763.389893|2638.169922|2648.939941|2648.939941|5283460000|
|2018-02-06|2614.780029|2701.040039|2593.070068|2695.139893|2695.139893|5891660000|



**SP500_Individual**\
Dataset contains all companies, their market symbol, name, and sector. Contains 506 entries with 3 attributes.

|Symbol|Name|Sector|
|---|---|---|
|MMM|3M Company|Industrials|
|AOS|A.O. Smith Corp|Industrials|
|ABT|Abbott Laboratories|Health Care|
|ABBV|AbbVie Inc.|Health Care|
|ACN|Accenture plc|Information Technology|
|...| | |
|XYL|Xylem Inc.|Industrials|
|YUM|Yum! Brands Inc|Consumer Discretionary|
|ZBH|Zimmer|Biomet Holdings	Health Care|
|ZION|Zions|Bancorp	Financials|
|ZTS|Zoetis|Health Care|

**all_stocks_5yr**\
Dataset listing daily open, high, low, close, volume for each company listed in S&P500 sorted by company symbol from 2013 to 2018. Contains 619041 entries with 7 attributes.

|date|open|high|low|close|volume|Name|
|---|---|---|---|---|---|---|
|2013-02-08|15.07|15.12|14.63|14.75|8407500|AAL|
|2013-02-11|14.89|15.01|14.26|14.46|8882000|AAL|
|2013-02-12|14.45|14.51|14.1|14.27|8126000|AAL|
|2013-02-13|14.3|14.94|14.25|14.66|10259500|AAL|
|2013-02-14|14.94|14.96|13.16|13.99|31879900|AAL|
|...| | | | | | |
|2018-02-01|76.84|78.27|76.69|77.82|2982259|ZTS|
|2018-02-02|77.53|78.12|76.73|76.78|2595187|ZTS|
|2018-02-05|76.64|76.92|73.18|73.83|2962031|ZTS|
|2018-02-06|72.74|74.56|72.13|73.27|4924323|ZTS|
|2018-02-07|72.7|75.0|72.69|73.86|4534912|ZTS|

**indivudal_stock_5yr**\
File contains datasets of daily open, high, low, close, volume for a company listed in S&P500. Contains 1260 entries for each company with 7 attributes.

Example dataset (AMAZON):
|date|open|high|low|close|volume|Name|
|---|---|---|---|---|---|---|
|2013-02-08|261.4|265.25|260.555|261.95|3879078|AMZN|
|2013-02-11|263.2|263.25|256.6|257.21|3403403|AMZN|
|2013-02-12|259.19|260.16|257.0|258.7|2938660|AMZN|
|2013-02-13|261.53|269.96|260.3|269.47|5292996|AMZN|
|2013-02-14|267.37|270.65|265.4|269.24|3462780|AMZN|
|...| | | | | | |
|2018-02-01|1445.0|1459.88|1385.14|1390.0|9113808|AMZN|
|2018-02-02|1477.39|1498.0|1414.0|1429.95|11125722|AMZN|
|2018-02-05|1402.62|1458.98|1320.72|1390.0|11494985|AMZN|
|2018-02-06|1361.46|1443.99|1351.79|1442.84|11066819|AMZN|
|2018-02-07|1449.0|1460.99|1415.15|1416.78|7162741|AMZN|

