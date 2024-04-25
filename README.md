A. WHAT IS TIME SERIES FORECASTING ?

Time series forecasting is a techniques for the prediction of events through a sequence of time. The techniques predict future events by analyzing the trends of the past, on the assumption that future trends will hold similar to historical trends. “The purpose of time series analysis is generally twofold: to understand or model the stochastic mechanisms that gives rise to an observed series and to predict or forecast the future values of a series based on the history of that series.”

**Type of Time series data
exogenous variables

endogenous and exogenous variable

ARIMA ARIMAX

SARIMA SARIMAX

B. Components of a Time-Series

1. Level :The average value in the series

2. Trend : The increasing or decreasing value in the series.

3. Seasonality : The repeating short – term cycle in the series.

4. Noise : The random variation in the series.

* There are 4 Variations of Time Series are Seasonal variations; Trend Variation; Cyclic Variations; rabdom Variations

C. Time Series terminology 

There are various terms and concepts in time series that we should know. These are as follows:-

1 Dependence- It refers to the association of two observations of the same variable at prior time periods.

2 Stationarity- It shows the mean value of the series that remains constant over the time period. If past effects accumulate and the values increase towards infinity then stationarity is not met.

3 Differencing- Differencing is used to make the series stationary and to control the auto-correlations. There may be some cases in time series analyses where we do not require differencing and over-differenced series can produce wrong estimates.

4 Specification - It may involve the testing of the linear or non-linear relationships of dependent variables by using time series models such as ARIMA models.

5 Exponential Smoothing - Exponential smoothing in time series analysis predicts the one next period value based on the past and current value. It involves averaging of data such that the non-systematic components of each individual case or observation cancel out each other. The exponential smoothing method is used to predict the short term prediction.

6 Curve fitting - Curve fitting regression in time series analysis is used when data is in a non-linear relationship.

7 ARIMA - ARIMA stands for Auto Regressive Integrated Moving Average.

D. Time Series Analysis and Forcasting
![Capture](https://github.com/sspheng/Time-Series-Forcasting/assets/78303183/6b9b7565-146d-423f-a4d9-0872e341eda2)

E. Visualisation 

![Capture](https://github.com/sspheng/Time-Series-Forcasting/assets/78303183/4524404d-f1c8-4ee6-85c4-461ac23f4764)

F. Decompose Time Series 

![Capture](https://github.com/sspheng/Time-Series-Forcasting/assets/78303183/871c4c17-9a88-4a4d-b4c7-323ab05a5b1c)

![Capture](https://github.com/sspheng/Time-Series-Forcasting/assets/78303183/1ffbf113-5c4a-41c2-b6b0-6a1cb0afb662)


plt.figure(figsize=(10,10))
plt.subplot(411)
plt.plot(ts_log, label='Original')
plt.legend(loc='best')

plt.subplot(412)
plt.plot(trend, label='Trend')
plt.legend(loc='best')

plt.subplot(413)
plt.plot(seasonal,label='Seasonality')
plt.legend(loc='best')

plt.subplot(414)
plt.plot(residual, label='Residuals')
plt.legend(loc='best')

plt.tight_layout()

![Capture](https://github.com/sspheng/Time-Series-Forcasting/assets/78303183/9ec1d341-2329-485c-9ecd-f0d72437a256)


*** Additive and Multiplicative Time Series 

We may have different combinations of trends and seasonality. Depending on the nature of the trends and seasonality, a time series can be modeled as an additive or multiplicative time series. Each observation in the series can be expressed as either a sum or a product of the components.
Additive time series:
Value = Base Level + Trend + Seasonality + Error

Multiplicative Time Series:
Value = Base Level x Trend x Seasonality x Error

G. Stationary and Non-Stationary Time Series 

We will talk about Stationary and Non-Stationary of Time Series. Stationarity is a property of a time series. A stationary series is one where the values of the series is not a function of time. So, the values are independent of time. Hence the statistical properties of the series like mean, variance and autocorrelation are constant over time. Autocorrelation of the series is nothing but the correlation of the series with its previous values. A stationary time series is independent of seasonal effects as well. Now, we will plot some examples of stationary and non-stationary time series for clarity.

**There are reasons why we want to convert a non-stationary series into a stationary one. These are given below:

a. Forecasting a stationary series is relatively easy and the forecasts are more reliable.

b. An important reason is, autoregressive forecasting models are essentially linear regression models that utilize the lag(s) of the series itself as predictors.

c. We know that linear regression works best if the predictors (X variables) are not correlated against each other. So, stationarizing the series solves this problem since it removes any persistent autocorrelation, thereby making the predictors(lags of the series) in the forecasting models nearly independent.

H. Make a time series to stationary

We can apply some sort of transformation to make the time-series stationary. These transformation may include:
+ Differencing the Series (once or more)
  
+ Take the log of the series

+ Take the nth root of the series

+ Combination of the above

The most commonly used and convenient method to stationarize the series is by differencing the series at least once until it becomes approximately stationary.

Differencing the Series

If Y_t is the value at time t, then the first difference of Y = Yt – Yt-1. In simpler terms, differencing the series is nothing but subtracting the next value by the current value. If the first difference doesn’t make a series stationary, we can go for the second differencing and so on. For example, consider the following series: [1, 5, 2, 12, 20] First differencing gives: [5-1, 2-5, 12-2, 20-12] = [4, -3, 10, 8]. Second differencing gives: [-3-4, -10-3, 8-10] = [-7, -13, -2]

I. Testing for stationarity 

The stationarity of a series can be checked by looking at the plot of the series. Another method is to split the series into 2 or more contiguous parts and computing the summary statistics like the mean, variance and the autocorrelation. If the stats are quite different, then the series is not likely to be stationary. There are several quantitative methods we can use to determine if a given series is stationary or not. This can be done using statistical tests called Unit Root Tests. This test checks if a time series is non-stationary and possess a unit root. There are multiple implementations of Unit Root tests like:

1. Augmented Dickey Fuller test (ADF Test): The most commonly used test to detect stationarity is ADF Testing. Here, we assume that the null hypothesis is the time series possesses a unit root and is non-stationary. Then, we collect evidence to support or reject the null hypothesis. So, if we find that the p-value in ADF test is less than the significance level (0.05), we reject the null hypothesis.

2. Kwiatkowski-Phillips-Schmidt-Shin – KPSS test (trend stationary): The KPSS test, on the other hand, is used to test for trend stationarity. The null hypothesis and the P-Value interpretation is just the opposite of ADH test.

3. Philips Perron test (PP Test):The Philips Perron or PP test is a unit root test. It is used in the time series analysis to test the null hypothesis that a time series is integrated of order 1. It is built on the ADF test discussed above.

J. Detrend a Time Series

Detrending a time series means to remove the trend component from the time series. There are multiple approaches of doing this as listed below:

Subtract the line of best fit from the time series. The line of best fit may be obtained from a linear regression model with the time steps as the predictor. For more complex trends, we may want to use quadratic terms (x^2) in the model.We subtract the trend component obtained from time series decomposition. Subtract the mean. Apply a filter like Baxter-King filter(statsmodels.tsa.filters.bkfilter) or the Hodrick-Prescott Filter (statsmodels.tsa.filters.hpfilter) to remove the moving average trend lines or the cyclical components.

K. Deseasonalize a Time Series 

There are multiple approaches to deseasonalize a time series. These approaches are listed below:

Take a moving average with length as the seasonal window. This will smoothen in series in the process.

Seasonal difference the series (subtract the value of previous season from the current value).

Divide the series by the seasonal index obtained from STL decomposition.

If dividing by the seasonal index does not work well, we will take a log of the series and then do the deseasonalizing. We will later restore to the original scale by taking an exponential.

L.  Autocorrelation and Partial Autocorrelation Functions 

Auto-Correlation Function is simply the correlation of a series with its own lags. If a series is significantly autocorrelated, that means, the previous values of the series (lags) may be helpful in predicting the current value. 

Partial Auto-Correlation Function also conveys similar information but it conveys the pure correlation of a series and its lag, excluding the correlation contributions from the intermediate lags.

M. Smoothening a Time Series

Smoothening of a time series may be useful in the following circumstances:

Reducing the effect of noise in a signal get a fair approximation of the noise-filtered series.

The smoothed version of series can be used as a feature to explain the original series itself.

Visualize the underlying trend better.

We can smoothen a time series using the following methods:

Take a moving average

Do a LOESS smoothing (Localized Regression)

Do a LOWESS smoothing (Locally Weighted Regression)

Moving Average

Moving average is the average of a rolling window of defined width. We must choose the window-width wisely, because, large window-size will over-smooth the series. For example, a window-size equal to the seasonal duration (ex: 12 for a month-wise series), will effectively nullify the seasonal effect.

Localized Regression

LOESS, short for ‘Localized Regression’ fits multiple regressions in the local neighborhood of each point. It is implemented in the statsmodels package, where you can control the degree of smoothing using frac argument which specifies the percentage of data points nearby that should be considered to fit a regression model.

Modelling
ML Models
Main Models

AR
MA
ARMA
ARIMA
SARIMA
EXPONENTIAL SMOTHING

EM model [single/double/triple]
EM -- HOLT WINTERS MODEL
Nueral Networks

RNN
LSTM

Reference and contact info:

https://www.machinelearningplus.com/time-series/time-series-analysis-python/

https://towardsdatascience.com/an-end-to-end-project-on-time-series-analysis-and-forecasting-with-python-4835e6bf050b

https://towardsdatascience.com/time-series-analysis-in-python-an-introduction-70d5a5b1d52a

https://www.digitalocean.com/community/tutorials/a-guide-to-time-series-visualization-with-python-3

https://github.com/sspheng/
