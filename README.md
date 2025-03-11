java c
Applied Econ 440.614: Macroeconometrics
Problem Set 2
Spring, 2025
1. Reliability of Unit Root Tests.   This question will have you perform. some simulation experiments to assess the reliability of unit root tests. We’ll simulate two processes. The first is a random walk with drift:

initialized with x1 ~ N (0, σ2). The second is a trend-stationary autoregressive process:

initialized with y1 → N (0, σ2/ (1 - ρ2)). The two unit root tests that we’ll consider are the augmented Dickey-Fuller (ADF) test and the Kwiatkowski-Phillips-Schmidt-Shin (KPSS) test. The commands to perform. these tests in Matlab are adftest and kpsstest, so you should read the documentation for both commands. In this exercise, when conducting the ADF test in Matlab, you should select the setting Model = "TS"; doing so tells Matlab to test the null hypothesis of a unit root against the alternative hypothesis of trend-stationary data. (Effectively, this tells Matlab to include a constant and linear time trend when performing the regression that is used to formulate the test statistic.) By default, the ADF regression in Matlab does not include any lags of the first difference of the data, which happens to be appropriate for the processes above. When conducting the KPSS test in Matlab, you should select the setting Lags = ceil(.75*T^(1/3)). (To compute the KPSS test statistic, Matlab uses several lags of the empirical autocovariance function, and this is a common rule of thumb for determining how many lags to use. This is not the same as specifying the number of autoregressive lags in the ADF test.) For each test, use the 5% threshold of statistical significance.
(a) Simulate 10, 000 artificial samples of length T = 200 for xt. Set µ = .1 and σ = .5. For each artificial sample, conduct an ADF test and a KPSS test.
i. In what fraction of samples does the ADF test reject the null hypothesis of a unit root in xt?
ii. In what fraction of samples does the KPSS test reject the null hypothesis of trend-stationarity in xt?
iii. In what fraction of samples do both the ADF test and the KPSS test reject their null hypotheses?
iv. In what fraction of samples do both the ADF test and the KPSS test fail to reject their null hypotheses?
(b) Simulate 10, 000 artificial samples of length T = 200 for yt. Set µ = .1, σ = .5, and ρ = .95. For each artificial sample, conduct an ADF test and a KPSS test.
i. In what fraction of samples does the ADF test reject the null hypothesis of a unit root in yt?
ii. In what fraction of samples does the KPSS test reject the null hypothesis of trend-stationarity in yt?
iii. In what fraction of samples do both the ADF test and the KPSS test reject their null hypotheses?
iv. In what fraction of samples do both the ADF test and the KPSS test fail to reject their null hypotheses?
(c) Recall that the significance of a statistical test is the probability of rejecting the null hypothesis, conditional on the null hypothesis being true. In theory, because we代 写Econ 440.614: Macroeconometrics Problem Set 2 Spring, 2025Matlab
代做程序编程语言 adopted a 5% threshold of statistical significance, we should expect to reject the null hypothesis about 5% of the time when the null hypothesis is true and the sample is large. However, in a finite sample, the significance of a statistical test may not be exactly 5%. Based on the results of the simulation experiments, are the significance levels for the ADF test and the KPSS test close to 5% when the sample size is T = 200?
(d) Recall that the power of a statistical test is the probability of rejecting the null hypothesis, conditional on the null hypothesis being false. Based on the results of the simulation experiments, how powerful is each test?
(e) Based on the results of the simulation experiments, do you think that the ADF and KPSS tests work well? Is the situation better or worse when the underlying data are genuinely non-stationary, or when the underlying data are genuinely trend-stationary? Explain your reasoning.
2. Comparing Statistical Trends. Go to FRED (fred.stlouisfed.org) and download data on the employment-population ratio (code: EMRATIO) from January, 1950, through December, 2019. For this exercise, let yt denote the employment-population ratio.
(a) One step in computing the Hamilton trend for a time series yt entails regressing yt+h on a constant and {yt, yt→1,...,yt→p+1}. Hamilton’s default recommendation for quarterly data is h = 8 and p = 4, corresponding to a forecast horizon of two years, with one year’s worth of lags used in constructing the forecast. Here, we’re using monthly data, so run this regression with h = 24 and p = 12. For each of the regression coefficients, what is the point estimate, what is the conventional (uncorrelated, homoskedastic) standard error, and what is the HAC (heteroskedasticity and autocorrelation consistent) standard error?
(b) One step in computing the Beveridge-Nelson trend is fitting an ARMA(p, q) model to Δyt. What values of p and q are selected by the BIC, when you consider all p ≤ 12 and all q ≤ 6?
(c) Compute the Hodrick-Prescott trend, the Hamilton trend, and the Beveridge-Nelson trend for the employment-population ratio. For the HP trend, use a smoothing parameter of 129, 600, because the data are monthly, not quarterly. (Read the documentation for the Matlab function hpfilter to adjust the smoothing parameter.) For the Hamilton trend, use h = 24 and p = 12. (Instead of using the output of your regression from part (a), you’re free to use Matlab’s built-in function hfilter, but read the documentation to adjust h and p.) For the Beveridge-Nelson trend, use the values of (p, q) selected by the BIC. Construct a plot that has yt and each of these three trends on a single set of axes. Make sure each line is labeled, and so are the axes.
(d) The cyclical component of a time series is defined as the di!erence between yt and its trend. On a single set of axes, plot the three measures of the cyclical component of yt. Make sure each line is labeled, and so are the axes.

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
