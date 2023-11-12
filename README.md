# Forecasting Net Prophet

## Unusual Patterns in Hourly Google Search Traffic

### Task
The goal of this step is to identify unusual patterns in Mercado Libre's hourly Google search traffic and connect them to corporate financial events.

### Steps
1. Read the search data into a DataFrame and slice it to include only the month of May 2020.
2. Visualize the results using hvPlot to identify any unusual patterns.
3. Calculate the total search traffic for May 2020 and compare it to the monthly median. Determine if the traffic increased during the release of quarterly financial results.

### Results
 __The google search trend increased by 8.55% when Mercadolab released its financial results.__

![1](Plots/Trends_may_2020.png)


## Mine the Search Traffic Data for Seasonality

### Task
This step involves mining the search traffic data for predictable seasonal patterns of interest in the company, focusing on hourly data.

### Steps
1. Group the hourly search data to plot the average traffic by the day of the week.
2. Visualize the traffic as a heatmap using hvPlot, referencing the hour and day of the week.
3. Group the data by the week of the year and observe if search traffic increases during the winter holiday period.

### Results
![12](Plots/Avg_traffic_by_weekday.png)
![12](Plots/Hours_trading_trends.png)
![12](Plots/Avg_traffic_by_year.png)

* __Search Traffic is very high at the mid night hours of a given day, especially on the weekdays.__
* __The search traffic rather tends to decrease during the winter holiday period.__


## Relate the Search Traffic to Stock Price Patterns

### Task
Explore the relationship between Google search data and the company's stock price patterns.

### Steps
1. Read and plot the stock price data, concatenate it with the search data.
2. Slice the data to the first half of 2020 and plot the time series. Assess if both indicate a common trend.
3. Create lagged search trends and additional columns for stock volatility and hourly stock return.
4. Review the time series correlation to identify relationships.

### Results
![12](Plots/Closing_price.png)
![12](Plots/Trends_2020_first_half.png)
![12](Plots/Volatility.png)

* __The search trends did not observe any comparable or significant changes through the first half in 2020 but the stock closing price consistenly grew over the tenure indicating the increase in the number of customers and therefore revenue.__

* __Note how volatility spiked, and tended to stay high, during the first half of 2020. This is a common characteristic of volatility in stock returns worldwide: high volatility days tend to be followed by yet more high volatility days. When it rains, it pours.__

## SCreate a Time Series Model by Using Prophet

### Task
Build a time series model to analyze and forecast patterns in the hourly search data.

### Steps
1. Set up the Google search data for a Prophet forecasting model.
2. Estimate the model and plot the forecast.
3. Analyze individual time series components to answer specific questions about popularity and search traffic.

### Results
![12](Plots/Forecast_trends.png)

* __The forecast model indicates that the search trend for mercado will decrease in the near term.__

![12](Plots/search_trends_forecast.png)
![12](Plots/plot_comp1.png)
![12](Plots/Plot_comp2.png)

* __The midnight hours exhibit the greatest popularity in the trends i.e., 12am__
* __Tuesdays get the most traffic__
* __October indicates the lowest point of search traffic in the calendar year__


## Forecast the Revenue by Using Time Series Models

### Task
Create a forecast for total sales in the next quarter using historical revenue figures.

### Steps
1. Read in daily historical sales figures and apply a Prophet model.
2. Interpret the model output to identify seasonal patterns in company revenue.
3. Produce a sales forecast for the finance group, including best- and worst-case scenarios.

### Results
![12](Plots/daily_sales.png)

![12](Plots/plot_comp3.png)
* __Wednesdays have the highest revenue__

![12](Plots/sales_forecast.png)
---

We can predict next quarter's total sales with 95% certainty as follows:

* ___Best case: $1.051 billion___

* ___Worst case: $888.23 million___

* ___Most likely: $969.63 million___
