# Can Companies Hedge the Weather?

**Evaluating Prediction Markets and CME Futures as Weather-Hedging Instruments**

ESFS Research · Alternatives Team · November 2026

This repository contains the models and data behind the ESFS Alternatives research paper *Can Companies Hedge the Weather?*. The paper explores to what extent weather event contracts on prediction markets (Kalshi, Polymarket, ForecastEx) and CME weather futures can offset the weather-related losses of companies that differ in size and sector.

> **Research only.** All calculations use public data. No positions were traded, and nothing in this repository is investment advice.

---

## Repository structure

```
.
├── README.md
├── engine/
│   └── Climate_Hedge_Model_v12.xlsx      # General model: contract catalogue, pricing, cost and capacity engine
├── data/
│   └── [raw and cleaned data files]
└── paper/
    └── [paper PDF, once published]
```

[Update this tree to match the final folder and file names.]

---

## The models

### 1. General engine (`engine/`)

A single Excel workbook that stores the contract catalogue and calculates the cost, payout and capacity of a hedge for any selected contract. It is a calculation tool: **its default inputs are illustrative and are not results of the paper.**

Visible sheets:

| Sheet | Purpose |
|---|---|
| `Dashboard` | Selected contract, cost, payout and loss scenarios |
| `Market_Search` | Search and select contracts by provider, variable, location and date |
| `Timing` | Compare the cost of the same contract at different entry times |
| `Results` | Monthly hedge results from recorded positions |
| `Inputs` | All editable assumptions (yellow cells) |
| `CME_Hedge` | Independent engine for CME weather futures (HDD/CDD) |

Hidden sheets hold the raw catalogue, price data, depth data and the project log (`Checks_and_Log`).
n when there is no order-book evidence.** Volume and open interest are not treated as available depth.
- Every figure is labelled as **observed** (taken from a source), **reconstructed** (estimated with a model) or **assumed** (an explicit research assumption).

## Data sources

| Source | Used for |
|---|---|
| City of Mesa: daily course activity and revenue | Dobson Ranch receipts |
| Iowa Environmental Mesonet (IEM) and NOAA GHCN | Observed daily weather |
| Company financial results (e.g. NW Natural Q1 2024) | Utility weather exposure |
| Kalshi, Polymarket, ForecastEx | Contract prices, rules and outcomes |
| CME Group | Degree-day futures rules, multipliers and settlements |

Full references and access dates are in the paper (Works Cited and Appendix E).

---

## How to use

1. Download the repository (see **Large files** below).
2. Open the engine in Microsoft Excel and allow it to recalculate.
3. Check that all checks in `Checks_and_Log` return `TRUE`.
4. To reproduce a case, open its folder in `cases/` and follow the notes in its first sheet.

## Limitations

- Company losses are estimated or reconstructed from public data, not audited losses.
- Historical order-book depth was not recovered, so the executable size of each hedge is unknown.
- Polymarket price history is limited, and Polymarket International is restricted for US users.
- Results are case studies, not general statistical estimates.

---

## Authors

Martí Tomàs, Timothée Lassalle, Lorenzo Imeneuraet, ESFS Research, Alternatives vertical, Esade Student Finance Society.
