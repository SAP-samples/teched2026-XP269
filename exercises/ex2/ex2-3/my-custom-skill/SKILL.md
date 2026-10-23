---
name: [your-skill-name]
description: "[One sentence: what does this skill do, and when should Joule use it? Include the trigger phrases a user would naturally say.]"
---

# [Your skill title]

[One paragraph: describe what this skill does and what business problem it solves.]

## Inputs

Collect the following from the user's message:

- **[Input 1]** — [what it is, e.g. "the car's attributes — Brand, Model, Year, etc."]
- **[Input 2]** — [what it is, e.g. "the seller's asking price"]
- [Add or remove inputs as needed. Do not invent values the user did not give.]

Used-car dataset columns you can use as features or targets:
`Car Brand`, `Model`, `Model Year`, `Location`, `Fuel`, `Driven (Kms)`, `Gear`, `Ownership`, `Price`

<!-- Note: `EMI (monthly)` is derived from `Price`. Do not use it as a feature when predicting
     Price (it leaks the target), and avoid it as a target too (it is just a proxy for Price). -->

## How it works

<!-- Step 1: call the MCP prediction tool. -->
<!-- TEAM: replace run_prediction with the real MCP tool name. -->

Call the `tabai-mcp` prediction tool with:

- `scenarioConfigName`: `used-cars-sc-<alias>`
- `modelName`: `sap-rpt-1.6`
- `predictionConfig.targetColumns`:
  ```json
  [{ "name": "[TARGET COLUMN]", "predictionPlaceholder": "[PREDICT]", "taskType": "[regression or classification]" }]
  ```
- `columns`: the query row(s) in columnar form, with the target column set to `[PREDICT]`.

<!-- Step 2: add your business logic here. -->
<!-- This is where your skill becomes more than just a prediction.         -->
<!-- Examples:                                                              -->
<!--   - Compare the predicted value against something the user provided   -->
<!--   - Run multiple predictions and find the best result                 -->
<!--   - Apply a formula to derive a new number from the prediction        -->
<!--   - Rank or filter results based on a business rule                   -->

[Describe your business logic step by step. Be explicit — the model follows these instructions literally.]

## Output

[Describe what to show the user. Lead with the most important number or verdict. Keep it short.]

Example output format:

```
[Your verdict or key result here]
[Supporting numbers — predicted value, inputs used, delta, etc.]
[One sentence of context or recommendation if relevant]
```

Always name the source: SAP RPT-1, from registered used-cars listings.
If the tool call fails, report the error plainly — do not fabricate a result.
