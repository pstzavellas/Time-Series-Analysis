# Time-Series Analysis in R

Three independent **time-series studies** built in **R**, covering the full classical workflow: decomposition, stationarity diagnostics, **ARIMA / SARIMA** modelling, trend-significance testing, and out-of-sample forecasting.

> **Stack:** R · `forecast` · `tseries` · classical decomposition · ARIMA/SARIMA · ggplot2

---

## What's Inside

The project applies the same analytical toolkit to three different real-world series:

| # | Series | Focus | Key techniques |
|---|--------|-------|----------------|
| 1 | **Norway — Unemployment** | Trend + seasonal structure, forecasting | STL decomposition, ARIMA vs **SARIMA**, model selection by **AICc**, Ljung–Box residual diagnostics |
| 2 | **Ioannina — Weather** | Seasonal behaviour of a local climate series | Seasonal decomposition, exploratory analysis, smoothing |
| 3 | **Beer — Sales** | Isolating and testing a trend | Classical (multiplicative) decomposition, trend-significance regression |

---

## Methodology Highlights

**Model selection, not guesswork.** For the unemployment series, both non-seasonal (ARIMA) and seasonal (SARIMA) models were fitted and compared on **AICc**, with residuals checked via **Ljung–Box** to confirm they behaved like white noise before trusting any forecast. The series was decomposed into trend and seasonal components rather than assumed.

**A methodological correction I'm proud of.** In the beer-sales study, the trend was initially isolated with a naive ratio-to-moving-average approach. I reworked it using **relative cyclical residuals**, which yielded a **statistically significant trend (p ≈ 0.011, R² ≈ 0.38)** — a cleaner, defensible result. It's a small example of a habit that matters in analytics: questioning whether the method actually fits the question, not just running the default.

**Forecasting with honesty about uncertainty.** Forecasts are reported with prediction intervals, and flat or wide forecasts are explained (a well-specified model that says "we can't know much" is more useful than a confident wrong one).

---

## Repository Contents

```
Time Series Analysis With R/
├── ...   # R scripts for each of the three studies
└── ...   # figures / outputs
```

*(Source scripts live in the `Time Series Analysis With R/` folder.)*

---

## Running It

```r
# From R / RStudio, install dependencies once:
install.packages(c("forecast", "tseries", "ggplot2"))

# Then open and run the script for the study you want to reproduce.
```

Each study is self-contained: load the series → decompose → fit & compare models → forecast → diagnose residuals.

---

## Why This Project

Forecasting and trend analysis are the everyday bread of a data analyst: demand, sales, sensor readings, KPIs over time. This project shows the complete loop — from raw series to a validated model to a forecast you can defend — rather than a single canned example.

---

*Co-authored academic project — MSc in Information Systems, University of Piraeus.*
