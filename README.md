# Calendar Spread Pricing & Greeks-Based PnL Attribution

## Overview

This project analyzes the construction, pricing, and risk behavior of an option calendar spread using historical option market data for **AAPL**.

The objective is to construct a structured option position, price the product using market data, and analyze its daily performance through **Greeks-based PnL attribution**. The analysis demonstrates a full quantitative workflow used in derivatives trading and risk management.

The implementation is performed in **Python using a Jupyter Notebook**, combining option pricing, volatility forecasting, and portfolio risk analysis.

---

## Strategy Construction

A **calendar spread** is constructed using two options with the same strike but different maturities.

The structure is designed to be **net long gamma**, meaning the position benefits from larger price movements in the underlying asset.

Key elements of the strategy include:

- Selection of appropriate **expiries**
- Strike selection logic based on underlying price
- Long and short positions across maturities
- Analysis of payoff characteristics

---

## Payoff Analysis

The payoff profile of the calendar spread is analyzed at maturity to understand the economic behavior of the strategy.

The payoff diagram illustrates:

- Regions where the structure generates profit
- Regions where losses occur
- Why the strategy exhibits **long gamma characteristics**

The payoff analysis helps visualize the nonlinear behavior of the option structure.

---

## Pricing Methodology

The calendar spread is priced using historical option market data as of the trade date.

The pricing process includes:

- Extracting relevant option contracts from historical data
- Estimating forward volatility inputs
- Applying option pricing models to value each leg of the structure
- Computing the initial portfolio value

Assumptions may include approximating American options as European for pricing and Greeks calculations.

---

## Portfolio Implementation

After constructing the strategy, the portfolio is simulated forward in time using historical data.

Daily portfolio valuation is computed by:

- Marking each option position to market
- Updating the total portfolio value
- Calculating daily profit and loss (PnL)

This produces a time series of:

- Portfolio value
- Daily PnL
- Risk exposures

---

## Greeks and PnL Attribution

Risk exposures of the calendar spread are analyzed using option **Greeks**:

- **Delta** – sensitivity to underlying price changes  
- **Gamma** – sensitivity of delta to underlying price changes  
- **Vega** – sensitivity to volatility changes  
- **Theta** – sensitivity to time decay  

Daily PnL is decomposed into contributions from these risk factors.

PnL attribution includes:

- Delta effect
- Gamma effect
- Vega effect
- Theta effect
- Residual component

Residual PnL can arise from:

- model approximations
- discrete hedging effects
- higher-order risk exposures

---

## Risk Considerations

Calendar spreads carry several key risks:

- **Volatility risk**: the strategy relies on the relationship between short- and long-term implied volatility.
- **Time decay differences**: the short-dated option decays faster than the long-dated option.
- **Underlying price movement**: extreme moves can alter the intended gamma exposure.
- **Model risk**: approximations used in pricing may introduce valuation errors.

Understanding these risks is essential for managing option structures in practice.

---

## Tools and Technologies

- **Python**
- pandas
- numpy
- matplotlib

The analysis is implemented in a **Jupyter Notebook** to allow interactive exploration of the data and results.

---

## Dataset

The historical option dataset used in this project was provided as part of a research exercise and cannot be redistributed.
The notebook demonstrates the full analysis workflow assuming access to the dataset.
