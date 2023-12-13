# PriceSim: Navigating Markets with Probability Distributions


## *Context*


In the current context, the United States stands out as one of the world's leading oil exporters. Back in the 1990s, there were concerns about dwindling production.<br>

However, the introduction of shale oil revolutionized the industry, propelling the United States back into the ranks of major producers. This resurgence has significantly impacted the global energy landscape, with the U.S. now playing a vital role in supplying Europe with natural gas.<br>

The last factor is of utmost importance, given that numerous variables influence oil prices, such as weather conditions, concerns over supply disruption due to geopolitical conflicts or OPEC meetings, to name just a few. This is crucial because it directly impacts the price of oil and subsequently affects end-users, in the case of gasoline for our vehicles for example.
A notable example of this occurred in the spring of 2020 when the price of WTI plummeted into negative territory due to the COVID-19 pandemic. During this period, oil stocks in Cushing, Oklahoma reached full capacity, contracts were sold in negative values, and gasoline prices hit record lows. The question that arises is: Can we develop a method to model these scenarios and predict market movements?<br>

While it's extremely challenging to foresee such dramatic market crashes, we can attempt to model price behavior and generate scenarios that closely approximate reality. Making informed decisions based on these scenarios becomes imperative.


<img src="wti_price.png" alt="wti price" width="850">


### Introduction


For the present analysis, we've considered price data from 2019. It's worth noting two significant price drops, the first occurring in 2015 and the more pronounced one in 2020. However, from the beginning of 2021, we observe a steady upward trend in prices. This can be attributed to two key factors:

- The reopening of countries following the COVID-19 pandemic
- The geopolitical situation, particularly the conflict involving Ukraine and Russia in Europe.


<img src="wti_price_2019.png" alt="wti price" width="850">


Continuing with the previous discussion, as evident in the following chart, the most substantial variation occurred in the spring of 2020, with the next significant difference noticeable until 2022.


<img src="wti_price_2019_var.png" alt="wti price" width="850">


Now, to extract more insights from the data, we endeavor to decompose it into a time series. The primary objective is to determine if there are any seasonal patterns within the series that can aid in forecasting price movements.


*WTI price*


<img src="series_decom.png" alt="wti price" width="950">


*WTI price variation*


<img src="series_decom_var.png" alt="wti price" width="950">


After a comprehensive analysis, we've detected distinct seasonality in both pricing and price variations. Nevertheless, it's important to acknowledge that this seasonality might be affected by the existence of outliers. To enhance the precision of our understanding, it is imperative that we take steps to address and minimize the influence of these outliers.

It's evident that these outliers have a substantial effect on our analysis. Our next approach will be to consider a logarithmic transformation. However, before proceeding with that, we'll first experiment with the *Winsor* technique.


*WTI price*


<img src="series_decomw.png" alt="wti price" width="950">


*WTI price variation*


<img src="series_decom_varw.png" alt="wti price" width="950">


Examining the charts above, we've successfully *reduced the impact of outliers.* However, it's important to note that no distinct seasonal pattern can be assumed from the data. While we do observe a decrease in **prices** around May, it's primarily a result of the sharp drop in prices during the peak of the COVID-19 pandemic.


### Distributions


*`Context`*<br>

A probability distribution is a mathematical description of the potential outcomes of a random event. 
In simpler terms, it characterizes the likelihood of a random variable assuming specific values. Each conceivable value of the random variable is associated with a probability that signifies the likelihood of that value occurring.

Now that we have a grasp of what a *probability distribution* entails, let's proceed with our next objective is to continue the analysis of **prices** and their behavior. It is crucial to determine the type of distribution we are dealing with and with the next test aims to assess how closely the distribution resembles a normal distribution.


*WTI price*


<img src="norm_price.png" alt="wti price" width="950">


*WTI price variation*


<img src="var_norm.png" alt="wti price" width="950">


Our conclusion is that the distribution doesn't conform to a **normal distribution.**

```python

```
