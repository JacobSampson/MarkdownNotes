# Chapter12

_Chapter 12_

## Capital Market Models

There is a reward for bearing risk

### Equity

#### Returns

Total dollar return = Income from investment + Capital gain \(loss\) due to change in price

#### Rates of Return

Dividends yield = Income / Beginning price

Capital gains yield = \(Ending price - Beginning price\) / Beginning price

Arithmetic average

Geometric average

* _Can calculate the final price_

### Historical Return and Risk

Risk premium

* Additional reward for bearing risk

$r_{total} = r_{risk\,free} + r\_{risk\,premium}$

Historical variance = Sum of squared deviations from the mean / \(Number of observations - 1\)

Standard deviation = Square root of the variance

**Blume's Formula**

$$
R(T) = \frac {T-1} {N-1} *Geometric\,average + \frac {N - T} {N - 1} * Arithmetic\,average
$$

* $N$ years of data
* $T$ years of forecast, where $N &gt; T$

### Equity Price Models

#### Brownian Motion

$$
P_i = P_{i - 1} (1 + r_i)
$$

**Simple rate of return**

$$
r_i = \frac {P_i - {P_{i - 1}}} {P_{i - 1}}
$$

**Mean simple rates of return**

$$
\alpha = \frac 1 n \sum_{i=1}^{n}r_i
$$

**Variance of simple rates of return**

$$
\sigma^2 = \frac 1 {n - 1} \sum_{i=1}^{n}(r_i - \alpha)^2
$$

$$
r_i \approx N(\alpha, \sigma^2)
$$

**Standard normal**

$$
z_i = \frac {r_i - \alpha} \sigma
$$

$$
r_i = \alpha + \sigma z_i
$$

$$
P_i = P_{i-1}(1 + \alpha + \sigma z_i)
$$

#### Geometric Brownian Motion

$$
P_i = P_{i - 1} e^{v_i}
$$

$$
v_i = \ln(P_i) - \ln(P_{i - 1})
$$

$$
\mu = \frac 1 n \sum_{i=1}^{n}v_i
$$

$$
\sigma^2 = \frac 1 {n - 1} \sum_{i = 1}^n (v_i - \mu)^2
$$

$$
v_i \approx e ^ {N(\mu,, \sigma^2)}
$$

$$
v_i = \mu + \sigma z_i
$$

$$
P_i = P_{i - 1}e^{\mu + \sigma z_i}
$$

#### Premium

**Equity Risk Premium**

$$
{ERP} = \frac 1 n \sum_1^n (r_{E_i} - r_{F_i})
$$

* $r\_{E\_i}$: Return on equity in period $i$
* $r\_{F\_i}$: Return on treasury bill in period $i$
  * _Treasury bills are considered risk free in USD_

**Market Risk Premium**

$$
{MRP} = \frac 1 n \sum_1^n (r_{M_i} - r_{F_i})
$$

* $r\_{M\_i}$: Total return on the market

### Capital Market Efficiency

**Fair Game**

$$
E(\Delta P) = 0
$$

$$
E(r) = 0
$$

**Efficient Market Hypothesis**

_"A market in which prices always fully reflect available information is called efficient. - Prof. Eugene Fama"_

$$
\sigma_{XY} = 0
$$

**Martingale**

$$
E(P \, | \, P_{i - 1}, P_{i - 2}...) = P_{i - 1}
$$

### Market Models

**Efficient Market Hypothesis**

Capital markets are efficient

* _Fama, Samuleson_
* Does _not_ imply a positive return cannot be earned
* Many investors are doing investment research
  * Without researching investments, the market would not be efficient
* New information is analyzed and trades are made
  * Prices should reflect all available public information

$$
\sum_i \Delta W_i > 0
$$

**Fractal Market Hypothesis**

* _Mandelbrot_

**Adaptive Market Hypothesis**

* _Andrew Lo_

**Behavioral Finance**

* _Thaler, Shiller, Kahneman_

#### Testable Methods

**Weak Form Hypothesis**

* Prices reflect all past investment information such as price and volume
* Investors cannot earn _abnormal_ returns by trading on market information
  * Implies that _technical analysis_ will not lead to abnormal returns 
* Empirical evidence indicates that markets are generally weak form efficient

$$
E(P_{i + 1} \,|\, P_i, P_{i-1}, P_{i-2}...) = P_i
$$

**Semi-strong Form Hypothesis**

* Prices reflect all publicly available information including trading information, annual reports, press releases...
* Investors cannot earn abnormal returns by trading on public information
  * Implies that _fundamental analysis_ will not lead to abnormal returns 

**Strong Form Hypothesis**

* Prices reflect all information, including public and private 
* Investors could not earn abnormal returns regardless of the information they possessed
  * Empirical evidence indicates that markets are _not_ strong form efficient and that insiders could earn abnormal returns

