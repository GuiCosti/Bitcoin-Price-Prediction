# Bitcoin-Price-Prediction
Using historical bitcoin market data to predict future values.

### Project Content

This project is composed by 3 main folders:

1. **src**: In this folder, there are 3 files. the first one is an exploratory notebook, named *1_eda.ipynb*, where the exploratory data analysis and notes are contained. There is also a summary of all EDA insights on the *README.md* file, located on the root folder. The other file is  named *2_prediction.ipynb* with the prediction models for price and volume. The last file is *anomaly.py*, that stores the anomaly detection model and it's insights.
2. **data**: This folder contains all the project data (to store in github, the original dataset is zipped with .7, because of it's size).
3. **models**: This part contains the saved machine learning models for predictions and anomaly detection.

### Installing Dependencies

On the root directory of the project, execute the commands below on the terminal:

```bash
pip3 install -r requirements.txt
```

### Working with the dataset

Before start running the notebooks, make sure you have unzipped the data file.

### Summary

#### Part 1

**2 hypothesis that might be relevant for Bipa's business:**

**Hypothesis 1**: The analysis shows higher price volatility during specific trading hours, particularly around the opening of big financial markets (US, Europe), with more instability during early morning hours.

As Bipa integrates BTC into its payment services, price fluctuations during peak trading hours could impact transaction costs and margins. Bipa might benefit from adjusting its processing fees dynamically based on market volatility during these high-traffic periods, for example, during the US market hours, where the price swings are common, the company could raise the fee to cover losses due price changes between transactions intilization and confirmantion.

**Hypothesis 2**: In addition to the high volatility in specific hours, the analysis alse shows that BTC is experiencing high volatility of open, close, high, and low prices during the past few years (specially in 2021 ~ 2022). This scenario, combined with the intraday price fluctuations, offers an opportunity for day traders to capitalize on rapid price movements. They can benefit from this volatility by executing multiple trades in short periods, profiting from small price differentials throughout the day.

By highlighting the opportunities for short-term gains in BTC, praising for example, the cut in the interest rate in the US right now, that is increasing liquidity and risk appetite for investiments like cryptocurrencies, the company could attract businesses and customers who prefer quicker transactions to explore this volatility.

#### Part 2

**What are the most important features for the prediction models:**

For both **Price** and **Volume** models, the most importante variable are the Close Price of the previous day (and the Open Price of the current day). This is because this price is the start point of the next flutuation, and represents the acumulated result of the all previous price chain. Then, after that, comes the other lag of the last days and moving average of the price / volume of 3 days, and the others.

**How Bipa can benefit from prediction models**

There are many ways that Bipa could benefit from the prediction models, such as Price Forecasting, to antecipate the BTC price to better understanding tradings and investiments; Risk Management, to identify volatility periods and adjusting fees to prevent losses; Demand prediction, to be prepare for a higher volume of transactions or trafic in the services; Marketing timing, to do campaigns in the right moments of the market; Loss prevention, detecting irregular patterns to early stopping; Customer experience enhancement, to understand the profile of the customer and predict a favorable market for the client to operate (like in the case of Day Trading pointed in the Hypothesis 2), and others.


#### Part 3

**How can anomaly detection help identify market manipulation and other important events**

As we could see in the plot, the anomaly captured the peaks and valleys points in almost every dimension of the dataset. There is a lot to benefit from a model fitted like that, such as Early Detection, to flag unusual trading patterns or price spikes; Fraud Detection, to identify suspicious trading volumes; Real-Time Alerts, such as anormal price movements; and others.

### Potential Enhancements & Next Steps

+ **Feature Engineering:** create more features to better predicting the price
+ **Feature Selection:** exploring more the feature selection
+ **Test More Models (SVM, Boosts, CNNs)**
+ **Test different dataset terms (medium-term and short-term):** Use the last-year-dataset, for example, to see if the LSTM and the other models behave better
+ **Lags + MA + PCA:** could apply PCA with more lags and rollings, to condense the information
+ **Implement Early Stopping:** There were cases in the LSTM that it was fitter better than at the end of all epochs, could implement a early stopping
+ **Abstract duplicated Code into functions:** repeated functions between files, repeated plottings, duplicated code, etc.
