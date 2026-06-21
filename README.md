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
- Derivation of the variance of estimators ( Var(β̂) ) and standard errors
- The Coefficient of Determination ( R² ) and Adjusted R²
- Hypothesis testing: **t‑test** (individual significance) and **F‑test** (overall significance)

### 2. Multiple Linear Regression
- Matrix representation: y = Xβ + ε
- OLS estimation in matrix form:

  ```math
  \hat{\beta} = (X'X)^{-1}X'y
