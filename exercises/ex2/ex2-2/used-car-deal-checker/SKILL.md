---
name: used-car-deal-checker
description: "Check whether a used-car listing is a good deal, overpriced, or fairly priced by comparing the asking price against an SAP RPT-1 market-value prediction. Use when the user asks if a price is fair, whether they should buy a car at a given price, or if a listing is worth it."
---

# Used-car deal checker

Predicts the fair market value of a used car using the historical used-cars listings, then compares it against the seller's asking price to give a verdict.

## Inputs

Collect two things from the user's message:

1. **The car's attributes** — any of the columns below. The more given, the better the prediction. Do not invent values the user did not give; leave unknown columns out.
- `Car Brand`, `Model`, `Model Year`, `Location`, `Fuel`, `Driven (Kms)`, `Gear`, `Ownership`

> Do not use `EMI (monthly)` as a feature — it is derived from `Price` and would leak the target.

2. **The asking price** — the price the seller is listing the car at. Required; if missing, ask for it before calling the MCP.

## How it works

Call the `tabai-mcp` prediction tool once to predict `Price`.

Pass these arguments:

- `scenarioConfigName`: `used-cars-sc-<alias>`  <!-- TEAM/alias: your scenario config from Exercise 1 -->
- `modelName`: `sap-rpt-1.6`
- `predictionConfig.targetColumns`: a single entry predicting `Price` as a regression:
```json
{ "name": "Price", "predictionPlaceholder": "[PREDICT]", "taskType": "regression" }
```
- `columns`: the car's attributes in columnar form, with `Price` set to `[PREDICT]`. Example for
  "a 2018 Maruti Swift, petrol, manual, 45,000 km, Delhi, asking price 420,000":
```json
{
  "Car Brand": ["Maruti"],
  "Model": ["Swift"],
  "Model Year": [2018],
  "Location": ["Delhi"],
  "Fuel": ["Petrol"],
  "Driven (Kms)": [45000],
  "Gear": ["Manual"],
  "Price": ["[PREDICT]"]
}
```

Once you have the predicted price, compute the deal verdict:

```
gap_amount  = asking_price - predicted_price
gap_pct     = (gap_amount / predicted_price) * 100

if gap_pct < -5%  → GOOD DEAL   (asking price is more than 5% below market value)
if gap_pct > +5%  → OVERPRICED  (asking price is more than 5% above market value)
otherwise         → FAIR PRICE  (within ±5% of market value)
```

Do not fabricate a predicted price. If the tool call fails, report the error plainly.

## Output guidance

Lead with the verdict, then one line showing the numbers, then a confidence note if available.

**Good deal example:**
> **Good deal** — asking price is 12% below estimated market value.
> Asking: 420,000 · Predicted market value: 477,000 · You save ~57,000.

**Overpriced example:**
> **Overpriced** — asking price is 8% above estimated market value.
> Asking: 515,000 · Predicted market value: 477,000 · Premium: ~38,000.

**Fair price example:**
> **Fair price** — asking price is within 5% of estimated market value.
> Asking: 490,000 · Predicted market value: 477,000 · Difference: ~13,000 (3%).

If a `confidence_interval` is returned, add one short clause:
> *(Prediction range: 450,000 – 504,000 based on SAP RPT-1, from registered used-cars listings.)*

Follow the base **response-style** rules: lead with the answer, no preamble, no emojis, plain
formatting, and name the source.
