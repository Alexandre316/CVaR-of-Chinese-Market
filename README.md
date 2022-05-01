# Conditional Value at Risk

## What is CVaR?

The original intention of Conditional Value at Risk is to decentralize and supervise the overall risks among large asset portfolios. In the actual market, the return rate of large assets usually shows the characteristics of "peak" and "thick tail", and the return rate of each asset does not conform to the assumption of multivariate normal distribution, and the tail extreme value is correlated. Therefore, it is considered to use t-copula to characterize the tail correlation of assets and reconstruct the tail distribution of asset return.

## Method

- It is hard to write fomula here. For more details, please refer to the reference.<sup>[1]</sup>
- Since we don't have enough historical data, we need to use Monte Carlo simulation to generate enough historical data and CVaR
- How to simulate? We all know that various characteristics of returns are expressed in the residual. How to express returns determines whether the residuals can be well expressed, and this comes to AR(1)+GJR-GARCH(1,1), which express the asymmetry and autocorrelation of returns well.
- Now we have standardized residuals for all three index, and I applied generalized pareto distribution to simulate upper tail (top 10%) and lower tail (tail 10%), when a normal distribution is used in the middle.
- From 3 return series, we have t-Copula, and now we can apply a series of mathmatic process and get CVaR.

## Results

As we can see,  declines of CVaR almost coincide with drawdowns, even 1~7 days in advance.
![a](https://github.com/Alexandre316/CVaR-of-Chinese-Market/blob/master/Output/WEEKLY_CVaR.png)

## References
[1]包卫军,徐成贤.基于多维t-Copula函数的投资组合的CVaR分析[J].统计与决策,2008(20):37-39.
