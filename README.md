# Uk-retail-seasonality-timeseries
Analyzing seasonality in UK mail order retail sales using autocorrelation and exponential smoothing, built with NumPy and Matplotlib on ONS time series data.
# UK Mail Order Retail Sales: Time Series Seasonality Analysis

A short applied time series project analysing seasonality in UK mail order / online retail sales, built with **numpy**, **matplotlib**, and **pandas** (pandas used only for data loading and array conversion).

## Overview

This project investigates whether monthly UK mail order retail sales show seasonality, and uses two time series concepts; **autocorrelation** and **simple exponential smoothing**  to explain that pattern to a non-technical decision maker.

## Dataset

- **Series:** RSI: Retail Sale via Mail Order Houses (Vol NSA): All Business Index
- **Source:** [Office for National Statistics — Time Series Explorer](https://www.ons.gov.uk/businessindustryandtrade/retailindustry/timeseries/eaqp/drsi)
- **Series ID:** EAQP
- **Range:** January 1988 – December 2025 (456 monthly observations)

The raw CSV (`retaildata1.csv`) was downloaded from the ONS Time Series Explorer and trimmed to monthly observations only.

## What's in this repo

| File | Description |
|---|---|
| `task2_report.md` | Full write-up: dataset intro, time series plot, autocorrelation analysis, exponential smoothing analysis, references |
| `retaildata1.csv` | Source data|
| `figure1_time_series.png` | Plot of the raw monthly series |
| `figure2_acf.png` | Autocorrelation function, lags 1–60 months |
| `figure3_ses.png` | Simple exponential smoothing (α = 0.3) vs actual values |



## Key findings

- The series shows strong, repeating annual seasonality; sales peak every November/December and dip in January.
- Autocorrelation is high at both short lags (lag 1 ≈ 0.98) and the seasonal lag (lag 12 ≈ 0.97), confirming the yearly cycle is stable across the full 1988–2025 period.
- A simple exponential smoothing model (α = 0.3) smooths out the seasonal noise to reveal the underlying trend, but lags during sharp shocks like the 2020 COVID-19 disruption.

## Requirements

```
numpy
matplotlib
pandas
```

## Running it

```bash
pip install numpy matplotlib pandas
python task2_analysis.py
```

## License

Data © Office for National Statistics, licensed under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).

