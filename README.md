# Stock-Market-DAP

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
|XL	XL Capital|Financials|
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

\Example dataset (AMAZON):
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

