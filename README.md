# Equity Factor Modeling — CAPM & Fama-French

A practical, hands-on walkthrough of single- and multi-factor asset pricing in Python.
These notebooks estimate **alpha** and **beta** via OLS, evaluate **risk-adjusted performance**
(Sharpe), construct **market-neutral long-short** signals, and score cross-sectional predictions
with the **Information Coefficient (IC)** — all on real market data from Yahoo Finance and the
Ken French Data Library.

> Built as a structured self-study of quantitative equity research methods — the same toolkit
> used to separate genuine skill (alpha) from cheap market exposure (beta).

---

## What's inside

### 1. CAPM — Single-Factor Asset Pricing
- Download and clean real price data; convert to returns
- Compute excess returns over the risk-free rate
- Estimate **alpha** and **beta** per asset via OLS regression
- Visualize the **Security Characteristic Line**
- Compute and interpret **Sharpe ratios**
- Build a long-short view and stress-test it for **lookahead bias** (walk-forward validation)

### 2. Fama-French — Multi-Factor Asset Pricing
- Pull the official **Fama-French 3-factor** data (MKT, SMB, HML) from the Ken French Data Library
- Decompose returns into market, size, and value exposures
- Compare **CAPM alpha vs FF3 alpha** — how much "alpha" is really just factor exposure?
- Build a momentum signal and evaluate it with the **Information Coefficient**
- Examine **rolling IC** for signal stability over time

---

## Key concepts demonstrated

| Concept | What it answers |
|---|---|
| **Beta** | How much market risk does this asset carry? |
| **Alpha** | Is there return the factors *can't* explain — i.e. genuine edge? |
| **Statistical significance (t-stats)** | Is the alpha real, or just noise? |
| **Sharpe ratio** | Is the return worth the risk taken? |
| **Information Coefficient** | Does my ranking of assets match what actually happened? |
| **Beta-neutral long-short** | How to isolate alpha by hedging out market risk |
| **Lookahead bias / walk-forward** | Is the result honest, or did it secretly use future data? |

---

## Data sources

- **Prices** — [Yahoo Finance](https://finance.yahoo.com) via `yfinance` (dividend/split-adjusted)
- **Factors** — [Ken French Data Library](https://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html)
  via `pandas_datareader` (MKT, SMB, HML, and the real 1-month T-bill risk-free rate)

No data files needed — everything is pulled live.

---

## Getting started

```bash
# Install dependencies
pip install numpy pandas matplotlib statsmodels scipy yfinance pandas_datareader

# Launch
jupyter notebook
```

Then open a notebook and run the cells top to bottom. Each section builds on the previous one.

---

## Requirements

```
python >= 3.9
numpy
pandas
matplotlib
statsmodels
scipy
yfinance
pandas_datareader
```

---

## Notes & limitations

These notebooks are a **learning resource**, not production trading code. A few things are
deliberately simplified, and the notebooks discuss each one:

- A small, hand-picked universe (toy example) — real research ranks broad universes and accounts
  for survivorship bias
- In-sample estimates in places — a production workflow validates everything out-of-sample
- No transaction costs or borrow fees modeled
- US-only factors — non-US assets would require regional factor data

The point is to understand the **machinery** clearly before scaling it up.

---
