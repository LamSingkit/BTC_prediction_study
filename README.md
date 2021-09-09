# Study of Bitcoin Prediction using RNN 
## Problem statement: 
Make a model that predict Bitcoin price. See if it's **usable** in real world application. 
## My approach:
Multivariate time series forecasting with LSTM:
- Research and find **features** that might affect Bitcoin price. Combine all the features with Bitcoin into one Dataframe. Feed it into a Recurrent Neural Network with LSTM layers. 

Pros:
- Add features easily in the future
- Data don't need to be stationary 	

Cons:
- Hard to set up initially compare to standard machine learning model
- Computationally expensive
- Some features might weaken the model. 


![](https://i.postimg.cc/zfL9K32z/pasted-image-0.png)
## Features that might affect stock prices
### Indicator of countries economic situation
- Gold Price: Also a decentralized asset, similar to Bitcoin
![](https://i.postimg.cc/vTRzkZvv/gold.png)
- Market Volatility: A measure of market dispersion. Bigger swing in either direction in stock market means higher volatility. ![](https://i.postimg.cc/QtKmfTct/volatility.png)
- 10 years minus 2 years treasury: is considered to be an advance warning of severe weakness in the stock market. Negative spreads occurred prior to the recession of the early 1990s, the tech-bubble crash in 2000-2001, and the financial crisis of 2007-2008![](https://i.postimg.cc/5yw3VW7W/10y2y.png)
- Overall Market Performance: S&P 500 stock price![](https://i.postimg.cc/TP4Qj9LF/sp500.png)
### Indicator of web speculation
- Google Trend on 'Cryptocurrency': Daily google trend data. ![](https://i.postimg.cc/nV7T7qHS/gtrend.png)
### Blockchain information (four most popular chart on blockchain.com)
- Average Block Size![](https://i.postimg.cc/xdCtb7CL/btc-blocksize.png)
- Total Hash Rate (TH/s)![](https://i.postimg.cc/3x9tN7KK/btc-hashrate.png)
- Transaction Per Day![](https://i.postimg.cc/dtY69D3s/btc-trans.png)
- Mempool Size (Bytes)![](https://i.postimg.cc/3x3L3WQS/btc-mempool.png)
## Results
The validation lost is 0.0136. It is slightly better than training it without features. The validation score of model without features is 0.016

<img src="https://i.postimg.cc/fLbpDK1R/valloss.png" width="400">

The model takes in 60 days of data and predict 14 days ahead. The graph below shows the prediction. The blue line is the actual BTC price, the black lines are the 14 days BTC prediction (Only part of them are drawn so it won't block the blue line), the black dots are all the day 1 data in the 14 days prediction. 
As shown in the graph, the model always tries to predict a upward trend. ![](https://i.postimg.cc/G2SN2D1J/pred.png)
## Conclusion and Future works
The model is not suitable for real life application. The reason behind this can be Bitcoin's short lifespan, also the lack of good and relevant features. In the future, I would like to experiment with reducing and adding number of features into the model, observe how it will affect the test score. Also, I will add key information such as reddit speculation (when pushshift API's aggregation function is available), twitter hashtag usage history, and whale account trading history.
