# Econometrics: From Theory to Application

## About This Repository
This repository is dedicated to the rigorous study of Econometric Theory, Manual Calculations, and Practical Applications.

It is divided into two major parts:
1. **Classical Linear Regression** (cross‑sectional data) — estimation, violations of assumptions, and diagnostic testing.
2. **Time Series Analysis** — dynamic models, stationarity, and forecasting.

Both parts follow the same educational pipeline:
- **Theory & Math**: Derivation of formulas using matrix algebra and calculus.
- **Manual Calculation**: Step‑by‑step computation using NumPy (from scratch) to understand the internal mechanics.
- **Validation**: Comparison with `statsmodels` to confirm correctness.
- **Practical Application**: Implementation on real‑world Kaggle datasets to derive economic/business insights.

---

## Part I: Classical Linear Regression (CLRM)

### 1. Pairwise (Simple) Linear Regression
- The Ordinary Least Squares (OLS) estimator
- The Gauss‑Markov Theorem (BLUE properties)
- Derivation of the variance of estimators ( $\text{Var}(\hat{\beta})$ ) and standard errors
- The Coefficient of Determination ( $R^2$ ) and Adjusted $R^2$
- Hypothesis testing: **t‑test** (individual significance) and **F‑test** (overall significance)

### 2. Multiple Linear Regression
- Matrix representation: $y = X\beta + \varepsilon$
- OLS estimation in matrix form:  
  $$ \hat{\beta} = (X'X)^{-1}X'y $$
- Interpretation of partial regression coefficients
- **t‑test** for individual slope parameters
- **F‑test** for joint restrictions (e.g., testing multiple exclusion restrictions)
- **Chow Test** for structural breaks (testing if coefficients differ across two sub‑samples)

### 3. Multicollinearity
- **Causes**: High correlations among explanatory variables, data collection methods, or model misspecification.
- **Consequences**: Inflated standard errors, unstable coefficient estimates, and reduced statistical power (insignificant t‑tests despite a high $R^2$).
- **Diagnostics**:
  - Pairwise correlation matrices
  - Variance Inflation Factor (VIF)
  - Condition Number of the $X'X$ matrix
- **Remedies**:
  - Dropping highly correlated variables (theoretically justified)
  - Principal Component Analysis (PCA) / Ridge Regression
  - Collecting more data

### 4. Heteroskedasticity
- **Causes**: Scale effects in data (e.g., variance increasing with income), outliers, or model misspecification.
- **Consequences**: OLS estimators remain unbiased but are **no longer BLUE** (lose efficiency). The standard OLS standard errors are biased, leading to invalid t‑ and F‑tests.
- **Diagnostics**:
  - Graphical analysis (residuals vs. fitted values)
  - **White’s General Test** (regressing squared residuals on all original variables, their squares, and cross‑products)
  - Breusch‑Pagan (BP) Lagrange Multiplier test
- **Remedies**:
  - Robust Standard Errors (White/Huber‑White "sandwich" estimators)
  - Weighted Least Squares (WLS)
  - Generalized Least Squares (GLS) — when the variance structure is known

### 5. Autocorrelation (Serial Correlation)
- **Causes**: Time‑ordered data, inertia (economic shocks persist), or model misspecification (e.g., omitted lagged variables).
- **Consequences**: Similar to heteroskedasticity — unbiased coefficients but inefficient estimates and biased standard errors.
- **Diagnostics**:
  - Durbin‑Watson (DW) statistic
  - Breusch‑Godfrey LM test (works with lagged dependent variables)
- **Remedies**:
  - Newey‑West (HAC) standard errors
  - Feasible Generalized Least Squares (FGLS) / Cochrane‑Orcutt procedure
  - Adding lagged dependent variables

### 6. Model Specification Errors (Omitted Variables & Functional Form)
- **Consequences of Omitted Variables**: Biased and inconsistent estimators (endogeneity).
- **Irrelevant Variables**: Inefficient estimators (higher variance).
- **Diagnostics**:
  - Ramsey RESET Test (detects non‑linearity or omitted interactions)
  - AIC / BIC criteria for model selection

---

## Part II: Time Series Econometrics

### 1. Stationarity and Unit Roots
- Weak stationarity (constant mean, constant variance, covariance dependent only on lag)
- **Causes of Non‑Stationarity**: Stochastic trends (random walks) and deterministic trends.
- **Consequences**: Spurious regression ( $R^2$ is high but relationships are meaningless).
- **Diagnostics**:
  - Visual analysis (ACF/PACF plots)
  - **Augmented Dickey‑Fuller (ADF) Test**
  - **KPSS Test** (null hypothesis of stationarity)

### 2. Auto‑Regressive (AR) and Moving‑Average (MA) Models
- **AR(p)**: Modeling current values as a linear function of past values.
- **MA(q)**: Modeling current values as a linear function of past error terms.
- **ACF and PACF analysis** to determine optimal lag orders (p, q).

### 3. ARIMA and SARIMA Models (Box‑Jenkins Approach)
- Integration (d): Differencing to achieve stationarity ( $I(d)$ ).
- **ARIMA(p, d, q)**: Estimation, parameter significance, and residual diagnostics (checking for white noise using the Ljung‑Box Q‑test).
- **SARIMA**: Extending ARIMA with seasonal components (P, D, Q, m) to handle quarterly/monthly patterns.

### 4. Cointegration and Error Correction Models (ECM)
- Testing for long‑run equilibrium relationships.
- **Engle‑Granger 2‑step method** and **Johansen Test**.
- **Vector Error Correction Model (VECM)**: Captures both short‑run dynamics and long‑run adjustments.

### 5. Volatility Modeling (ARCH/GARCH)
- Detecting volatility clustering in financial/economic data.
- **ARCH(q)** and **GARCH(p, q)**: Modeling variance as a function of past squared errors.
- Applications in risk management (Value at Risk).

### 6. Forecasting
- Generating rolling forecasts using the fitted models.
- **Evaluation Metrics**:
  - Mean Absolute Error (MAE)
  - Root Mean Squared Error (RMSE)
  - Mean Absolute Percentage Error (MAPE)
- Out‑of‑sample testing and backtesting.

---

## Practical Application (Kaggle Integration)
For **every topic** listed above, this repository contains a dedicated Jupyter Notebook that applies the theory to a competitive Kaggle dataset.

- **Classical Regression**: Applied to datasets like *House Prices*, *Wage Determination (Wooldridge)*, or *Boston Housing* to analyze feature importance, multicollinearity diagnostics (VIF), and robust standard errors.
- **Time Series**: Applied to datasets like *Air Passenger Traffic*, *Stock Prices (Yahoo Finance)*, or *Macroeconomic Indicators (GDP/Inflation)* to perform forecasting and volatility analysis.

---

## Repository Structure
