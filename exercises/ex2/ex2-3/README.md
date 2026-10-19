# Exercise 2.3 — Take It Further

## Build your own skill from scratch

Use the bare template at [`../ex2-3/my-custom-skill/SKILL.md`](../ex2-3/my-custom-skill/SKILL.md). Copy it, fill in the placeholders, and publish it the same way you did in Exercise 2.3. Ask Joule to place the skill in assets/tabai-agent/app/skills/`skill-name`

The template has two moving parts:
1. **The prediction call** — choose a target column and task type (`regression` or `classification`).
2. **Your business logic** — what you do with the predicted value before returning it to the user. This is what makes your skill different from just asking for a raw prediction.

## Here are some ideas to get you started

**Feature value estimator** — *"What is an automatic gearbox worth on this car?"*
Run the same car twice — once with `Gear: Manual`, once with `Gear: Automatic` — and return the price delta. Tells a buyer whether a spec upgrade is worth the premium. Works for any column: `Fuel`, `Location`, `Ownership`.

**Location arbitrage** — *"Where should I sell this car to get the best price?"*
Batch-predict the same car across multiple cities in one call. Rank by predicted price and tell the seller which market to list in.

**Depreciation preview** — *"How much will this car be worth in two years?"*
Project future value at two or three mileage milestones (e.g. current km, +20k, +50k) by running predictions with incremented `Driven (Kms)`. Return a value-over-time table and a sell-or-hold recommendation.

**Negotiation advisor** — *"I'm looking at three cars — which one should I make an offer on?"*
User provides a list of cars with asking prices. Batch-predict market value for all of them, rank by gap between asking and predicted, and return a data-backed recommendation with a suggested counter-offer for the best candidate.

> **Tip:** every one of these follows the same pattern as the deal-checker. There will be one prediction call (or a small batch), followed by the business logic on the result. The template guides you through both parts.

## Further exploration
### Predict other columns

Your skill already handles `Price`. Change the target column and you have new capabilities with no new setup:

- **`Fuel`** — classification. "Petrol or diesel, most likely?"
- **`Car Brand`** — classification with many classes. Good for showing confidence spread.

### Narrow the context with filters

Ask the model to learn only from relevant history, e.g. cars in the same city or a model-year range. Under the hood this is a context-selection **filter** on the predict call; in chat you can phrase it as part of the request and let the skill pass it through:

```
Estimate the price, using only listings from Mumbai from 2012 onwards.
```

### Predict several columns at once

SAP-RPT-1.6 can fill more than one missing column in a single request (e.g. `Gear` **and** `Fuel`). Mark both as `[PREDICT]` in the query row and list both in the target columns.

### Return more than one candidate (top-K)

For a classification, ask for the top few labels with their confidences instead of just the best one — useful for "what are the likely options?" answers.

### Make the skill fully self-service

Right now the data stage is registered manually in Module 01. As a stretch, extend your skill so that, if the scenario config doesn't exist yet, it **registers it first** (destination → artifact → scenario config) and then predicts — the full "zero manual setup" agent. This is exactly the
pattern the base skills + MCP are designed to support.

### Bring your own table

The whole flow is dataset-agnostic. You can register a new data destination that points to a different table in HANA Data Lake Fies System (HDLFS) / S3 object storage, register it, and your skill pattern predicts any column of it. The used-cars dataset is just an example for this exercise that represents *your* data table in your use case.
