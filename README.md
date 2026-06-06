# Emerging Markets Sentiment, Anomalies and Uncertainty Factors

## Overview

This project constructs a comprehensive empirical framework to analyze the interaction between **investor sentiment**, **macroeconomic uncertainty (EPU)**, and **asset pricing anomalies** across emerging markets.

We build firm-level and country-level sentiment indices using textual/market-based proxies and orthogonalize them with respect to market returns and economic policy uncertainty. The dataset spans multiple emerging economies and supports both **cross-sectional asset pricing** and **time-series macro-finance analysis**.

The framework is designed to be fully reproducible and modular, following best practices in empirical finance research.

---

## Research Objectives

This project addresses three main questions:

1. How does investor sentiment behave across emerging markets at firm and country levels?
2. What is the incremental role of macroeconomic uncertainty (EPU) in explaining sentiment dynamics?
3. How do sentiment measures relate to standard asset pricing anomalies (FF5-style factors)?

---

## Data Description

### Countries
- Brazil (BR)  
- Chile (CL)  
- Colombia (CO)  
- Mexico (MX)  
- Peru (PE)

### Data Frequency
- Daily (firm-level construction)
- Monthly (primary analysis)
- Yearly (robustness and aggregation)

### Main Data Sources
- Market prices and returns
- Trading volume
- Market capitalization
- Economic Policy Uncertainty (EPU)
- Constructed anomaly portfolios (FF5-style factors)

---

## Methodology

### 1. Firm-Level Sentiment Construction (SIF)

We construct a firm-level sentiment index (SIF) using technical and behavioral proxies:

- RSI (Relative Strength Index)
- PLI (Price Level Indicator)
- ATR (Volatility proxy)
- LTV (Liquidity/turnover proxy)
- Market return component (MKT)
- Economic Policy Uncertainty (EPU)

Each variable is orthogonalized using:

\[
SIF_{it} = \alpha + \beta_1 MKT_{t} + \beta_2 EPU_{t} + \varepsilon_{it}
\]

The residual defines the **orthogonal sentiment component**.

---

### 2. Decomposition of Sentiment

We decompose sentiment into three components:

- **Orthogonal Sentiment (Pure SIF)**  
  Idiosyncratic variation after controlling for MKT and EPU

- **Market-driven Sentiment Component**
  Exposure to aggregate market conditions

- **EPU-driven Sentiment Component**
  Exposure to macroeconomic uncertainty shocks

---

### 3. PCA-Based Sentiment Aggregation

For each firm, we estimate:

- Principal Component Analysis (PCA)
- First principal component defines firm-level SIF index

This ensures dimensionality reduction and factor consistency across variables.

---

### 4. Aggregation

We construct:

#### Firm-level measures
- Monthly SIF
- Annual SIF

#### Country-level measures
- Value-weighted SIF
- Equal-weighted SIF
- Lagged sentiment dynamics
- High/Low sentiment regimes

---

## Asset Pricing Factors

We incorporate standard FF5-style anomaly portfolios:

### Momentum
Short- and medium-term return continuation effects.

### Value
Book-to-market, earnings-to-price, dividend yield.

### Investment
Asset growth, investment intensity, capital expansion.

### Profitability
Return on assets, return on equity, gross profitability.

### Intangibles
Human capital, innovation proxies, intangibles intensity.

### Trading / Liquidity / Limits to Arbitrage
Turnover, liquidity constraints, Amihud illiquidity measures.

Each factor is classified as:

- Behavioral
- Fundamentals
- Limits-to-arbitrage

---

## Empirical Design

The empirical strategy includes:

- Panel regressions (firm and country level)
- Orthogonalized factor regressions
- PCA-based factor extraction
- Lagged sentiment specifications
- Cross-country comparisons

Standard errors are clustered at firm and/or time level.

---

## Output Structure

The pipeline generates:

### Firm-level datasets
- `df.mmSIFFirmFull.rds`

### Country-level datasets
- `df.mmSIFPaisFull.rds`

### Annual datasets
- `df.yySIFFirmFull.rds`
- `df.yySIFPaisFull.rds`

### Factor datasets
- Momentum, Value, Investment, Profitability, Intangibles, Trading

---

## Reproducibility

To reproduce the results:

1. Clone repository
2. Load R project
3. Run scripts in order:
   - `01_data_preparation.R`
   - `02_sentiment_pca.R`
   - `03_sif_decomposition.R`
   - `04_aggregation_monthly_yearly.R`
   - `05_anomaly_factors.R`

---

## Software Requirements

- R ≥ 4.2
- dplyr
- data.table
- lubridate
- tidyr
- stats
- ggplot2 (optional)

---


---

## Citation

If you use this code or methodology, please cite:

> Author (2026). *Emerging Markets Sentiment, Anomalies and Uncertainty Factors*. Working Paper.

---

## Contact

Jailson Duarte  
Research Project – Emerging Markets Asset Pricing

---

## License

This project is released for academic and research use only.

## Project Structure

