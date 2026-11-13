# Walkthrough: how the Crocs LBO model works

Read this with `Crocs_LBO_Model.xlsx` open. The goal is that you can explain every tab and rebuild the Returns tab from a blank sheet.

All figures are in $ millions. Blue cells are inputs; black cells are formulas.

## The idea in four sentences

A buyout fund buys a company using mostly borrowed money. The company's own cash flow repays that debt over about five years. The fund then sells the company. Its return comes from three places: profit growth, selling at a higher multiple, and having less debt at the end.

## Tab by tab

### 1. Historical
Figures typed in from Crocs' 10-K and 10-Q.

- **LTM (last twelve months)** = full year 2025 + first nine months of 2026 - first nine months of 2025. This gives the most recent full year of results.
- **Adjusted EBITDA** = income from operations + impairments + depreciation and amortization. The 2025 HEYDUDE write-down of $737M is added back because it is a one-time, non-cash charge.
- LTM Adjusted EBITDA is **$1,010M**. This is the number the whole deal is priced on.

### 2. Assumptions
- **Offer price** = share price x (1 + premium) = $156.88 x 1.25 = $196.10.
- **Equity purchase price** = offer price x shares = $8,967M.
- **Enterprise value** = equity + debt - cash = $8,967M + $1,313M - $163M = $10,116M.
- **Entry multiple** = enterprise value / EBITDA = 10.0x.

### 3. Sources & Uses
Uses are what the money is spent on; sources are where it comes from. They must be equal.

- **Uses:** buy the shares ($8,967M), repay existing debt ($1,313M), fees ($291M), leave $100M of cash in the business. Total $10,670M.
- **Sources:** Term Loan B at 4.0x EBITDA ($4,040M), Senior Notes at 1.5x ($1,515M), the company's own cash ($163M), and the fund's equity.
- **Sponsor equity is the plug:** total uses minus debt minus cash = **$4,952M**.

### 4. Model
- **Revenue** grows by brand using the growth rates on the Assumptions tab.
- **EBITDA** = revenue x margin (24.5%).
- **Free cash flow** = EBITDA - taxes - capital spending - working capital - interest.
- **Debt schedule:** each year the Term Loan B is reduced by a required 1% payment plus all spare cash above the $100M minimum (the "cash sweep"). The Senior Notes are not repaid until exit.
- **Interest** is charged on the balance at the start of each year. This keeps the model free of circular references.

Result: debt falls from $5,555M to $3,187M, and leverage falls from 5.5x to 2.7x.

### 5. Returns
- **Exit enterprise value** = year 5 EBITDA x exit multiple = $1,168M x 10.0 = $11,683M.
- **Exit equity** = exit enterprise value - net debt = $11,683M - $3,087M = $8,596M.
- **MOIC** = exit equity / equity invested = $8,596M / $4,952M = 1.74x.
- **IRR** = MOIC ^ (1 / years) - 1 = 1.74 ^ (1/5) - 1 = 11.7%.
- **Maximum price:** works backwards from a 20% IRR to the most the fund could pay, about $164 per share.

### 6. Sensitivity
Shows how IRR and MOIC change with the offer premium, the exit multiple and the exit year. Each cell is an ordinary formula you can click on and trace.

## Questions to be ready for

1. **Why is the IRR only 11.7%?** The price is 10.0x for a business growing about 3% a year, with no multiple expansion. Debt paydown alone does not get to 20%.
2. **What drives returns in an LBO?** EBITDA growth, multiple expansion and debt paydown. Here: $1.6B, about zero, and $2.1B.
3. **Why add back the impairment?** It is non-cash and one-time, so it does not reflect ongoing earnings.
4. **What happens to IRR if you use more debt?** Less equity is needed, so IRR usually rises, but interest cost and risk rise too.
5. **Why does IRR fall as the premium rises?** The fund puts in more equity for the same exit value.
6. **What is the biggest risk?** Fashion risk in the core clog and further HEYDUDE decline, with interest taking close to half of EBITDA in year one.
7. **What did you simplify?** Fixed interest rates, basic share count, no fee amortization, LTM used as the starting year.

## Practice before you list this on your resume

1. Change the premium to 10% on the Assumptions tab and confirm the IRR moves to 17.4%.
2. Change the exit multiple to 12.0x and confirm 17.2% (at a 25% premium).
3. On a blank sheet, rebuild the Returns tab from these five numbers: year 5 EBITDA $1,168M, exit multiple 10.0x, net debt $3,087M, equity invested $4,952M, 5 years. You should get 1.74x and 11.7%.
4. Rebuild Sources & Uses from the Assumptions tab without looking.
