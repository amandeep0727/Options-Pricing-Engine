📊 Options Pricing Engine

 Overview

This project implements a "multi-stock options pricing engine" in Python. It retrieves real market data, builds theoretical valuations, and computes sensitivities (Greeks) to support "risk management" and "trading insights".

The engine combines:

* ✅ "Black–Scholes closed-form pricing" (vectorized in pandas/numpy)
* ✅ "Monte Carlo simulations" (contract-by-contract, class-based)
* ✅ "Greeks calculation" (Δ, Γ, Vega, Θ, ρ)
* ✅ "Mispricing analysis" (absolute & percentage difference between model and market)

---

 ✨ Features

* Pulls "historical stock prices" and "option chains" from Yahoo Finance (via `yfinance`).
* Computes "volatility estimates" from historical returns.
* Selects "ATM options" closest to 30 days to expiry.
* Calculates:

  * Theoretical option prices using "Black–Scholes" and "Monte Carlo"
  * Full "Greeks" for sensitivity analysis
  * "Mispricing signals" (over/undervaluation vs. market price)
* Outputs a "styled trader’s table" with color-coded mispricing.

---

 🛠️ Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/amandeep0727/Options-Pricing-Engine.git
cd Options-Pricing-Engine
pip install -r requirements.txt
```

---

 ▶️ Usage

Run the Jupyter notebook:

```bash
jupyter notebook BS_Options_Pricing_Final.ipynb
```

Example output (styled trader’s table):

| ticker | expiry     | strike | option_type | marketPrice | bs_price | mc_price | mispricing_pct | delta  | gamma | vega  | theta  |
| ------ | ---------- | ------ | ----------- | ----------- | -------- | -------- | -------------- | ------ | ----- | ----- | ------ |
| AAPL   | 2025-10-31 | 255    | call        | 9.00        | 10.77    | 10.64    | +19.7%         | 0.544  | 0.016 | 30.46 | -61.08 |
| NVDA   | 2025-10-31 | 180    | put         | 8.35        | 11.20    | 10.98    | +34.2%         | -0.486 | 0.015 | 21.36 | -54.27 |

---

 📈 Applications

* Identify "market mispricings" (undervalued/overvalued options).
* Analyze "risk exposures" via Greeks.
* Prototype a "trader’s desk tool" for decision support.

---

 📂 Repo Contents

* `BS_Options_Pricing_Final.ipynb` → Full workflow notebook
* `requirements.txt` → Python dependencies
* `README.md` → Project description & instructions

---

 ⚠️ Notes

* This project uses Yahoo Finance data, which may differ slightly from live market feeds.
* Current `S0` can be adjusted to use live prices if available (`yf.Ticker().info['currentPrice']`).

---