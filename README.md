# CAPM vs. Fama–French Three-Factor Model  
**Empirical Comparison of Explanatory Power**

---

## Data

The analysis uses monthly U.S. equity return data constructed from publicly available sources. Asset returns are converted to **excess returns** by subtracting the risk-free rate. Factor data for the market excess return (MKT), size (SMB), and value (HML) are obtained from the Fama–French data library and aligned by month with the return series.

The final dataset consists of a balanced monthly time series covering the same sample period across all models. All variables are expressed in percentage terms and checked for missing observations prior to estimation.

---

## Methodology

The project evaluates the Capital Asset Pricing Model (CAPM) and the Fama–French Three-Factor Model using **time-series regressions of excess returns on risk factors**.

### CAPM Specification

R<sub>t</sub> − R<sub>f,t</sub> = α + β<sub>m</sub>(R<sub>m,t</sub> − R<sub>f,t</sub>) + ε<sub>t</sub>

### Fama–French Three-Factor Specification

R<sub>t</sub> − R<sub>f,t</sub>  = α  
+ β<sub>m</sub>(R<sub>m,t</sub> − R<sub>f,t</sub>)  
+ β<sub>s</sub> SMB<sub>t</sub>  
+ β<sub>h</sub> HML<sub>t</sub>  
+ ε<sub>t</sub>

The primary quantities of interest are:
- **Alpha (α)** as a test of abnormal returns  
- **Factor loadings (β)** and their statistical significance  
- **Model fit (R<sup>2</sup>)** as a measure of explanatory power  

Nested model comparison is used to assess whether the additional Fama–French factors provide incremental explanatory power beyond CAPM.

---

## Specification and Diagnostic Tests

To validate time-series regression assumptions, the following diagnostic checks are conducted:

- Multicollinearity assessed using variance inflation factors (VIF)
- Serial correlation tested using the Breusch–Godfrey test
- Robust inference implemented using Newey–West standard errors to account for heteroskedasticity and autocorrelation

These checks ensure valid statistical inference under potential violations of classical OLS assumptions.

---

## Results

The Fama–French Three-Factor Model exhibits higher explanatory power than CAPM, reflected in improved goodness-of-fit measures and reduced unexplained variation in excess returns. Estimated alphas are smaller and less statistically significant under the three-factor specification, indicating that returns attributed to abnormal performance under CAPM are largely explained by exposure to size and value factors.

Formal model comparison supports the conclusion that the additional factors in the Fama–French model provide statistically meaningful information beyond the market factor alone. Robustness checks using Newey–West standard errors do not materially affect the qualitative conclusions.

---

## Interpretation

The results indicate that CAPM omits relevant sources of systematic risk captured by the Fama–French size and value factors. The reduction in estimated alpha under the three-factor model highlights the importance of correct model specification when evaluating abnormal returns and supports the use of multi-factor frameworks in empirical asset pricing.

---

## Repository Structure

data/        Raw and cleaned return and factor data   
report/      Final paper and figures (pdf and html)  

