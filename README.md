# Prediction of Current Account Surplus in Asian Economies

## Project Overview
This research project investigates the key macroeconomic drivers behind current account imbalances (surpluses and deficits) across Asian nations. Using standardized country-level data from the World Bank’s World Development Indicators (WDI) database, we analyze how indicators like trade flows, foreign investments, reserve levels, and domestic economic conditions affect external balances. 

The study leverages multiple linear regression modeling in IBM SPSS Statistics to provide policymakers with evidence-based insights for managing currency valuations, trade policies, and macroeconomic stability in one of the world's most dynamic economic regions.


## Key Features & Methodology

### 1. Data Collection & Preprocessing
* Initial Dataset: Downloaded global country-level annual metrics spanning 217 economies from the World Bank WDI database.
* Regional Filtering: Isolated **25 Asian nations** based on the World Bank's East Asia & Pacific and South Asia regional classifications.
* Missing Data Treatment: Addressed a random sim3 missing value rate across indicators using time-based historical trend estimation and regional averages to maintain dataset integrity

### 2. Outlier Treatment & Transformations
To meet the assumptions of linear regression, the raw data underwent extensive statistical preparation:
* Logarithmic Transformation: Applied to all continuous variables to compress extreme values, stabilize variance, and capture linear relationships.
* Standard continuous variables: log_Exports =ln({Exports})
* Zero/Negative values: log_GDPgrowth = (GDPgrowth) times ln({GDPgrowth} + 1)
* Winsorization: Post-transformation data was capped at the 99th percentile and floored at the 1st percentile to diminish outlier influence while preserving 98% of core observations.
* Result: Post-treatment skewness was successfully reduced to within pm1 for all variables.


## Statistical Output & Regression Results

### Model Summary
The linear regression model was executed using the Enter method in SPSS, evaluating 10 independent predictors against the dependent variable (log{CurrentAccountBalance}).

| Metric | Value | Interpretation |
| R | 0.807 | Strong positive correlation between the collective predictors and external balance. |
| R^2 (R-Square) | 0.652 | The model successfully explains 65.2% of the variance in Asian current account balances. |
| Adjusted R^2 | 0.648 | Robust explanatory power adjusting for the number of predictors; no overfitting. |
| Durbin-Watson | 1.021 | Within acceptable thresholds (1.0 - 3.0); minor positive autocorrelation, but not a serious issue. |
| Std. Error of the Estimate | 0.51708 | Average distance that observed values fall from the regression line. |

### ANOVA (Overall Model Significance)
* Null Hypothesis (H0): All regression coefficients are equal to zero (no predictors affect the balance).
* Alternative Hypothesis (H1): At least one predictor significantly affects the current account balance.

Result:  F = 187.486  (p = 0.000)

Decision: Reject H0. The model is highly statistically significant, confirming that the predictors collectively explain variations in current account balances.

---

## Predictor Breakdown & Coefficients

The following table summarizes the performance, significance, and effects of individual macroeconomic drivers under the model (N = 1013):

| Independent Variable (Log-Transformed) | Unstandardized Coefficient (B) | Standardized Beta (beta) | p-value ({Sig.}) | Status | Economic Interpretation |

| {log_GNI} | +0.525 | 0.544 |  Significant | Strongest positive driver. Higher national income significantly improves the balance. |
| {log_TotalReserve} | +0.412 | 0.477 |  Significant | Strong predictor ({Partial Eta Sq} = 0.169). Reserves boost external stability. |
| {log_totalPopulation} | -0.364 | -0.345 | Significant | Higher population downwardly pressures the balance due to import dependence. |
| {log_PersonalRemittance_Winsor} | -0.119 | -0.110 | Significant | Negatively associated, indicating potential capital outflow nuances. |
| {log_Exports} | -0.064 | -0.069| 0.013 | Significant | Counterintuitive negative link; justified via regional supply chain/trade suppression dynamics. |
| {log_ForeignDirectInvestment} | +0.059 | 0.065 | 0.030 | Significant | Modest positive impact; tracking patterns rise alongside macro performance. |
| {log_OfficialExchangeRate} | -0.035 | -0.055 | 0.010 | Significant | Moderate negative impact; currency depreciation reduces the balance within this model context. |
| {log_Inflation_Winsor} | +0.159 | 0.081 | Significant | Shows a positive shift under regression control, despite a negative baseline correlation. |
| {Log_TotalUnemployement_Winsor} | +0.072 | 0.030 | 0.115 | Not Significant | Weak baseline relationship; does not explicitly impact external balances. |
| {log_GDPgrowth_Winsor} | -0.004 | -0.002 | 0.938 | Not Significant | Statistically redundant when broader national income indicators {GNI}) are accounted . |


## Diagnostic Plots & Evaluation

The validity of the linear model is cross-checked with standard regression residual visualizations:

1. Normality of Residuals: The Normal P-P Plot points align cleanly along the $45 diagonal line. Furthermore, the residual Histogram displays a symmetrical bell-shaped curve centered near zero, confirming the data fits normality criteria smoothly.
2. Multicollinearity: VIF values are strictly < 10 (all values < 8) and Pearson correlation coefficients between independent metrics remain comfortably under 0.9, indicating no severe multicollinearity concerns.
3. Homoscedasticity: The residual vs. predicted value Scatterplot flags a mild, non-severe funnel shape. While homoscedasticity assumptions are largely acceptable, caution is suggested regarding standard error interpretations.

---

## Conclusion & Policy Relevance
This analysis confirms that Gross National Income (GNI), foreign currency/gold reserves, and population size act as the primary structural anchors for external balance accounts across Asia. Quantifiable indicators show that a 1 rise in GNI correlates directly to a 0.54 improvement in a country's current account trajectory. These findings give planners clear targets for currency market stabilization, trade policies, and growth agendas.


