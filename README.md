# Data Analysis and Financial Portfolio
This repository showcases a comprehensive collection of data analysis and Financial projects completed during my Master's program in International Trade and Finance. The projects demonstrate Financial Knowledge, proficiency in statistical analysis, econometric modeling, and data visualization techniques applied to real-world economic and financial datasets.

# Project 1: Portfolio Analysis and Asset Valuation with the CAPM Model

## Executive Summary

This project is a comprehensive quantitative analysis of a French stock portfolio from the CAC 40, conducted in **Python**. The objective is to progress from raw market data to an evaluation of systematic risk and expected return for each asset, using the **Capital Asset Pricing Model (CAPM)**.

**Analyzed Portfolio:**
*   LVMH (`MC.PA`)
*   TotalEnergies (`TTE.PA`)
*   BNP Paribas (`BNP.PA`)
*   Airbus (`AIR.PA`)
*   **Market Index:** CAC 40 (`^FCHI`)

**Methodology:**
1.  **Data Collection:** Downloading 7 years of daily price data via the `yfinance` API.
2.  **Exploratory Analysis:** Visualization of normalized performance (Base 100) for fair comparison.
3.  **Return Calculation:** Transformation of prices into daily returns using `pandas`.
4.  **Beta Calculation:** For each stock, Beta was determined through **linear regression** (Ordinary Least Squares) of its returns against market returns, using the `statsmodels` library.
5.  **CAPM Application:** Estimation of expected annual return for each asset based on its Beta and market assumptions (Risk-free rate, Market risk premium).

**Key Findings:**
*   The analysis revealed that **Airbus (Beta = 1.45)** and **BNP Paribas (Beta = 1.32)** stocks present the highest systematic risk, amplifying market movements.
*   In accordance with financial theory, these higher-risk stocks are also those that offer the **highest expected return** according to the CAPM model (10.26% and 9.60% respectively).
*   **TotalEnergies** proved to be the most "defensive" stock in the portfolio, with a Beta close to 1.