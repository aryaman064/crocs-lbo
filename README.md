# Crocs, Inc. LBO Model

A leveraged buyout model for a hypothetical take-private of Crocs, Inc. (NASDAQ: CROX), built in Excel from the company's public SEC filings.

**Result:** at a 25% premium ($196.10 per share, $10.1B enterprise value, 10.0x LTM EBITDA) the deal returns an **11.7% IRR and 1.74x MOIC** over five years, below a 20% target. The model puts the highest price that still earns 20% at about **$164 per share (8.6x)**. The recommendation is to pass at a market premium. See the [investment memo](Investment_Memo.md).

This is a learning and interview-practice project, not investment advice. It was built with AI assistance (Claude); I set the scope and assumptions and checked the outputs.

## Files

| File | What it is |
|---|---|
| `Crocs_LBO_Model.xlsx` | The model. Every number is a live formula; inputs are in blue. Open in Excel. |
| `Investment_Memo.md` | One-page memo: thesis, returns, risks, recommendation. |
| `WALKTHROUGH.md` | How the model works, tab by tab, and how to rebuild it. |

## What the model covers

- **Historical**: FY2023 to FY2025 results and the last twelve months to 9/30/2026, by brand (Crocs and HEYDUDE), with Adjusted EBITDA that adds back the 2025 HEYDUDE impairments.
- **Sources & Uses**: purchase of equity, refinancing of existing debt, fees, and the mix of Term Loan B, Senior Notes and sponsor equity.
- **Model**: five-year forecast by brand, taxes, capital spending, working capital, and a debt schedule with mandatory amortization and a 100% cash sweep.
- **Returns**: exit value, MOIC, IRR, a value bridge, and the maximum price for the target IRR.
- **Sensitivity**: IRR and MOIC across offer premium, exit multiple and exit year.

## Base case

| | |
|---|---|
| Share price (close 2026-11-12) | $156.88 |
| Offer price (25% premium) | $196.10 |
| Equity purchase price | $8,967M |
| Enterprise value | $10,116M |
| LTM Adjusted EBITDA | $1,010M |
| Entry multiple | 10.0x |
| New debt (5.5x EBITDA) | $5,555M |
| Sponsor equity (46% of sources) | $4,952M |
| Debt repaid over five years | $2,368M |
| Leverage at exit | 2.7x |
| Exit multiple | 10.0x |
| MOIC / IRR | 1.74x / 11.7% |

### IRR sensitivity: offer premium vs exit multiple

| Premium | Offer price | 8.0x | 9.0x | 10.0x | 11.0x | 12.0x |
|---|---|---|---|---|---|---|
| 10% | $172.57 | 10.2% | 14.0% | 17.4% | 20.4% | 23.1% |
| 15% | $180.41 | 8.2% | 12.0% | 15.3% | 18.2% | 20.9% |
| 20% | $188.26 | 6.4% | 10.1% | 13.4% | 16.3% | 19.0% |
| 25% | $196.10 | 4.8% | 8.4% | 11.7% | 14.5% | 17.2% |
| 30% | $203.94 | 3.3% | 6.9% | 10.1% | 12.9% | 15.5% |
| 35% | $211.79 | 2.0% | 5.5% | 8.6% | 11.4% | 14.0% |

## Data sources

- Crocs Form 10-K for fiscal 2025, filed 2026-02-12 (SEC EDGAR)
- Crocs Form 10-Q for the quarter ended 2026-09-30, filed 2026-10-29 (SEC EDGAR)
- Share price: closing price on 2026-11-12

## Simplifications

- Basic share count; dilution from equity awards is ignored.
- Interest rates are fixed and interest is charged on beginning balances, which avoids circular references.
- Share-based compensation is not added back to EBITDA.
- Financing fees are treated as a cash cost at close and are not amortized.
- The last twelve months to 9/30/2026 stand in for fiscal 2026 as the starting year.

## Checks

The Summary tab runs five checks (sources equal uses, historical figures tie, brand revenue ties, balances stay valid, two IRR methods agree). All show TRUE. The model was also recalculated independently outside Excel and the results matched.
