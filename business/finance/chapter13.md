# Chapter13

_Chapter 13_

## Return, Risk, and the Security Market Line

### Expected Returns and Variances

$$
Risk\; premium = E(R_U) - R_f
$$

### Portfolios

Portfolio: Group of assets such as stocks and bonds held by an investor

Portfolio weight: Percentage of a portfolio's total value that is invested in a particular assets

$$
E(r_P) = \sum_{i=1}^m r_i w_i
$$

* $w$ is the weight of the assets where $\sum w = 1$
* Variance on a portfolio is not generally a simple combination of the variances of the assets in the portfolio
  * Weights of the assets values?
* Risk is _expected volatility_ or _expected variance_ for rate of return

$$
E(r)= \sum_{i=1}^{m} P(r_i) r_i
$$

$$
\sigma^2 = \sum_{i=1}^m \sum_{j=1}^m w_i w_j \sigma_{ij}
$$

**Expected Return from a Time in History**

$$
E(r) = \frac 1 n \sum_{i=1}^{n} r_i
$$

$$
\sigma_P^2 = \frac 1 {n - 1} \sum_{i=1}^{n} (r_i - E(r))^2
$$

$$
r_P = w^T \cdot r
$$

**Variance of a Portfolio**

$$
\sigma_P^2 = w^T \cdot C \cdot w
$$

* $C$ is the covariance matrix

### Announcements, Surprises, and Expected Returns

Total return = Expected return + Unexpected

$$
R = E(R) + U
$$

Announcement = Expected part + Surprise

Systematic risk \(Market risk\): One that influences a large number of assets, each to a greater or lesser extend

Unsystematic risk \(Unique or asset-specific risk\): Risk that affects at most a small number of assets

$$
R = E(R) = Systematic \; portion + Unsystematic \; portion
$$

$$
\sigma^2_P = \bar \sigma^2 \cdot (\frac 1 m  + \bar \rho \cdot \frac {m-1} m)
$$

* As $m$ goes to infinity, the variance of the portfolio approaches the market's \(systematic risk\)

### Diversification and Portfolio Risk

Principle of diversification: Spreading an investment across a number of assets will eliminate some, but not all, of the risk

* Unsystematic risk is essentially eliminated by diversification, so a portfolio with many assets has almost no systematic risk

Total risk = Systematic risk + Unsystematic risk

Efficient frontier: The line showing the combination of assets with the greatest return rate for each standard deviation

### Systematic Risk and Beta Coefficient

Systematic risk principle: The expected return on a risky assets depends only on that asset's systematic risk

* Because unsystematic risk can be eliminated at virtually no cost \(by diversifying\), there is no reward for bearing it
* The market does not reward risks that are borne unnecessarily

Beta coefficient: How much systematic risk a particular assets has relative to an average asset

* An average asset has a beta of 1.0 relative to itself

**Risk**

Total rate of return on a stock = Risk free rate of return + \(Risk premium from market proportional risk \(Systematic risk\) + Risk premium from stock specific risk \(Non-systematic risk\) = Total risk premium\)

$$
\beta = \frac {\sigma_{iM}} {\sigma_M^2}
$$

**Capital Asset Price Model \(CAPM\)**

$$
E(r_i) = r_F + \frac {\sigma_{iM}} {\sigma_M ^ 2} \cdot (E(r_M) - r_f)
$$

* $\beta = 1$: Same risk as market
* $\beta &lt; 1$: Less risk than market
* $\beta &gt; 1$: Greater risk than market

Total risk: Standard deviation

Systematic risk: $\beta$

* Return on the market is the market risk premium less the risk free rate

### Security Market Line

$$
SML\;slope = \frac {E(R_M) - R_f} {\beta_M}
$$

#### Reward-to-Risk Ratio

* Risk premium per "unit" of systematic risk
* Reward-to-risk ratio must be the same for _all_ assets in the market
  * _Best met by NYS or other financial markets but not necessarily real asset markets_

Security market line \(SML\): Positively sloped straight line displaying the relationship between expected return and beta

* Average systematic risk, must have a beta of 1

**Expected return rate on an asset**

$$
r_E = r_F + \beta\cdot (r_M - r_F)
$$

**Cost of Capital**

* Minimum required return on a new investment

**Market Equilibrium**

$$
\frac {E(r_A) - r_F} {\beta_A} = \frac {E(r_M) - r_F} {\beta_M}
$$

