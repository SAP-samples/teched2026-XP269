# Exercise 2.1 — Predict & Visualize

In Exercise 1, you have created the scenario configuration (`used-cars-sc-<SUFFIX>`) and ran a prediction by calling the Tabular AI orchestration API directly in the Python notebook. Now, you will get to try running the same prediction workflow in **the no-code manner** just by chatting with Joule. You can build on top of this by creating your custom skill in Exercise 2.2.

## Run it
1. In the same chat as before, you can trigger the base prediction skill with a natural question, for example:
```
Predict the price of a 2015 Honda City, petrol, automatic, driven 60,000 km in Mumbai.
```
The base skill make a prediction request to SAP-RPT-1.6 via the Tabular AI orchestration using with the mocked scenario configuration `mock-scenario-config`, and replies with an estimated **Price**.

> This is the **same Tabular AI orchestration flow** you ran in the notebook — query rows in, context rows fetched automatically from your registered tabular artifact, `sap-rpt-1.6` predicts the missing value. The only difference is you are runnign this workflow conversationally instead of via APIs within a Python notebook. 

## Reading the result

- **Regression** (`Price`): a single numeric `prediction`, optionally with a `confidence_interval`.
- **Classification** (`Gear`, `Fuel`): a predicted label plus a `confidence` score (0–1). Ask for the gearbox instead and you'll get, e.g., `Automatic` with a confidence.

## A note on model selection

The flow uses `sap-rpt-1.6`, which fits this dataset comfortably. The `*-large` variants allow for a larger context window. For this exercise, the base model is faster and mostly sufficient. You can view the detailed model specifications on Help Portal [here](https://help.sap.com/docs/sap-ai-core/generative-ai/sap-rpt-1-6?locale=en-US).

## Try a classification

You can use the same skill but with a different intent:
```
For a 2018 Hyundai i20, diesel, 40,000 km, is it more likely manual or automatic?
```

The target column switches to `Gear` with `taskType: classification` and returns the most likely transmission with a confidence.

## Summary
You can now move on to [Exercise 2.2 - Build a Custom Skill](../ex2-2/README.md), where you can try building a custom skill by following the instructions to build the `used-car-deal-checker` skill.
