I. WHAT IS TIME SERIES FORECASTING ?

Time series forecasting is a techniques for the prediction of events through a sequence of time. The techniques predict future events by analyzing the trends of the past, on the assumption that future trends will hold similar to historical trends. “The purpose of time series analysis is generally twofold: to understand or model the stochastic mechanisms that gives rise to an observed series and to predict or forecast the future values of a series based on the history of that series.”

II. Components of a Time-Series

1. Level :The average value in the series

2. Trend : The increasing or decreasing value in the series.

3. Seasonality : The repeating short – term cycle in the series.

4. Noise : The random variation in the series.

* There are 4 Variations of Time Series are Seasonal variations; Trend Variation; Cyclic Variations; rabdom Variations

III. Time Series terminology 

There are various terms and concepts in time series that we should know. These are as follows:-

1 Dependence- It refers to the association of two observations of the same variable at prior time periods.

2 Stationarity- It shows the mean value of the series that remains constant over the time period. If past effects accumulate and the values increase towards infinity then stationarity is not met.

3 Differencing- Differencing is used to make the series stationary and to control the auto-correlations. There may be some cases in time series analyses where we do not require differencing and over-differenced series can produce wrong estimates.

4 Specification - It may involve the testing of the linear or non-linear relationships of dependent variables by using time series models such as ARIMA models.

5 Exponential Smoothing - Exponential smoothing in time series analysis predicts the one next period value based on the past and current value. It involves averaging of data such that the non-systematic components of each individual case or observation cancel out each other. The exponential smoothing method is used to predict the short term prediction.

6 Curve fitting - Curve fitting regression in time series analysis is used when data is in a non-linear relationship.

7 ARIMA - ARIMA stands for Auto Regressive Integrated Moving Average.

IV. Time Series Analysis and Forcasting
![Capture](https://github.com/sspheng/Time-Series-Forcasting/assets/78303183/6b9b7565-146d-423f-a4d9-0872e341eda2)

V. Visualisation 

![Capture](https://github.com/sspheng/Time-Series-Forcasting/assets/78303183/4524404d-f1c8-4ee6-85c4-461ac23f4764)

VI Decompose Time Series 


*** Additive and Multiplicative Time Series 
Table of Contents

We may have different combinations of trends and seasonality. Depending on the nature of the trends and seasonality, a time series can be modeled as an additive or multiplicative time series. Each observation in the series can be expressed as either a sum or a product of the components.
Additive time series:
Value = Base Level + Trend + Seasonality + Error

Multiplicative Time Series:
Value = Base Level x Trend x Seasonality x Error
