# Data Analysis and Financial Portfolio
This repository showcases a comprehensive collection of data analysis and Financial projects completed during my Master's program in International Trade and Finance. The projects demonstrate Financial Knowledge, proficiency in statistical analysis, econometric modeling, and data visualization techniques applied to real-world economic and financial datasets.

---

# Project 10: Macroeconomic Impact Analysis on Financial Markets

## Executive Summary

## 1. Project Objective
This project conducts a data-driven analysis to answer a fundamental question in finance: **How do key macroeconomic variables, specifically central bank interest rates and inflation, influence the performance of the French stock market?** Using a decade-and-a-half of data, this study moves beyond simple theory to test these relationships with real-world evidence, focusing on the CAC 40 index.

## 2. Methodology
The analysis was performed entirely in Python, following a structured time-series workflow:
1.  **Data Acquisition:** Programmatic download of daily CAC 40 market data (`yfinance`) and monthly macroeconomic indicators—the ECB Main Refinancing Rate and Euro Area HICP Inflation—from the Federal Reserve Economic Data (FRED) database via the `fredapi`.
2.  **ETL & Resampling:** The core technical challenge involved aligning disparate data frequencies. All datasets were resampled to a consistent **monthly** frequency using the `pandas` library, creating a robust, unified dataset for comparative analysis.
3.  **Visualization & Statistical Analysis:** The analysis employed dual-axis time-series charts to visualize long-term trends, scatter plots to investigate correlations, and a correlation matrix to statistically quantify the relationships between the variables.

## 3. Key Findings & Insights
The analysis revealed a nuanced and forward-looking relationship between the macro environment and market performance, challenging simplistic assumptions:

*   **No Direct Correlation Between Inflation and Monthly Returns:** The scatter plot and correlation matrix (correlation of 0.00) show **no statistically significant linear relationship** between the level of inflation and the CAC 40's monthly returns. This indicates that the market's reaction to inflation is complex and highly context-dependent, rather than mechanical.

*   **Markets React to *Anticipation*, Not Just Levels, of Interest Rates:** The primary time-series chart clearly shows that the market's major downturn in 2022 began *before* the ECB's aggressive rate hikes, as investors priced in the future tightening cycle. Conversely, the market began its strong recovery in late 2023, well before rates were actually cut, as it started anticipating the "peak" of the hiking cycle.

*   **Corporate Resilience Can Override Macro Headwinds:** Despite the high-interest-rate environment post-2022—a period traditionally seen as negative for equities—the CAC 40 reached new all-time highs. This counter-intuitive performance highlights the fundamental strength and pricing power of the index's leading companies (e.g., in luxury and industrials), whose robust earnings can outweigh macroeconomic pressures.

## 4. Conclusion
This project demonstrates that while macroeconomic indicators are crucial, their impact on the stock market is not linear or immediate. The market operates as a **forward-looking mechanism**, reacting to expectations and future shifts in policy. Furthermore, the underlying strength of the constituent companies of an index can serve as a powerful buffer against a challenging macro environment. The analysis confirms that a sophisticated understanding of market dynamics requires looking beyond simple correlations to interpret the interplay between data, expectations, and fundamental corporate health.

---

# Project 8: Optimizing a Multi-Asset Portfolio (MPT)

## Executive Summary

## 1. Project Objective
This project addresses a real-world investment scenario: **how to optimally allocate a €10,000 capital across a diverse universe of 18 global assets**, including stocks, ETFs, bonds, and cryptocurrency. The primary goal is to move beyond naive allocation strategies and apply the principles of **Modern Portfolio Theory (MPT)** to construct a portfolio that **maximizes the risk-adjusted return (Sharpe Ratio)**, while adhering to a specific set of realistic investment constraints.

## 2. Methodology
The entire analysis was conducted in Python within this Jupyter Notebook, following a structured, end-to-end quantitative workflow:

1.  **Data Engineering (ETL):** Acquired and processed over 5 years of daily historical price data for all assets using the `yfinance` API. The data was cleaned, aligned, and transformed into daily returns using the `pandas` library.
2.  **Quantitative Analysis:** Calculated the two essential inputs for the Markowitz model: the **annualized mean returns** and the **annualized covariance matrix**, which serve as our estimates for future performance and risk.
3.  **Constrained Optimization:** Utilized the `PyPortfolioOpt` library to find the optimal asset weights. Crucially, the optimization was performed under a specific mandate, including constraints for **diversification** (max 12.5% per asset) and **strategic inclusion** (minimum allocation per asset class).
4.  **Visualization & Projection:** Visualized the results by plotting the **Efficient Frontier** to prove the superiority of the optimized portfolio against simpler benchmarks. A **20-year growth projection** was also created to illustrate the long-term impact of the strategy.

## 3. Key Findings
The analysis revealed several key insights:
*   The **constrained optimal portfolio** provides a significantly better risk-return profile than a naive equal-weight strategy and offers a competitive alternative to a passive market benchmark (S&P 500).
*   The final portfolio is expected to yield a return of **19.2%** for an annual volatilty of **15.2%**, resulting in a Sharpe Ratio of **1.26**.
*   The long-term projection demonstrates that this optimized allocation, through the power of compounding, leads to **substantially greater wealth creation** over a 20-year horizon compared to the benchmarks.

## 4. Final Recommendation
The final, data-driven recommendation is to allocate the €10,000 capital according to the weights derived from the **constrained optimization model**. This notebook provides the exact, actionable plan, detailing the discrete number of shares to purchase for each selected asset. The resulting portfolio is strategically diversified, adheres to all investment rules, and is mathematically optimized for the best possible risk-adjusted performance based on historical data.

---

# Project 7: Portfolio Analysis and Asset Valuation with the CAPM Model

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