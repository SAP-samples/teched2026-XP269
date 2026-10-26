
# XP269 - Bring the power of Tabular AI foundation models to your SAP Agents

## Description

This repository contains the material for the SAP TechEd 2026 session called XP269 - Bring the power of Tabular AI foundation models to your SAP Agents.

## Session Overview

Tabular AI meets Intelligent Agents: Build Smarter with SAP-RPT

Structured data is everywhere in the enterprise — and it's one of the most underutilised assets in AI-driven workflows. This session explores how tabular foundation models, specifically SAP-RPT models, are redefining what intelligent agents can do with structured information.

In this hands-on session, you will move beyond theory and directly experience how to integrate tabular AI models into the agent development lifecycle. From initial integration and iterative testing to rigorous benchmarking, you will gain practical skills to evaluate model performance and make informed design decisions for real-world use cases.

Whether you are building decision-support agents, automating data-driven processes, or optimising enterprise workflows, tabular foundation models offer a powerful new layer of intelligence. Join us to discover how turning structured data into smarter, faster, and more reliable agent decisions is not just possible — it is within reach today.

## What You Will Learn

Tabular AI in Action: Building Smarter Agents with SAP-RPT & Joule Studio

In this hands-on session, you will learn how to harness the power of tabular foundation models, specifcally SAP-RPT, to build intelligent agents that make smarter decisions from structured enterprise data.

Working directly inside Joule Studio, you will go through the full agent development lifecycle: integrating tabular AI models, writing and testing agent logic in code, and benchmarking model performance against real-world scenarios. This is not a demo you watch — it is a workflow you execute.

By the end of this session, you will:

Learn how you can run predictions at scale using SAP-RPT models via Tabular Orchestration
Learn how you can integrate the SAP-RPT model within an agent in Joule Studio
Get to try extending the provided agent with custom skills
Get to test agent behaviour and validate outputs across different prediction scenarios
Turn structured enterprise data into actionable, AI-driven decisions inside your agent pipelines

## Prerequisites / Setup

To get started, first download the repository as a zip file. Once completed, unzip the file and you should get an extracted folder.

Open Visual Studio Code. Select **Open Folder** and choose the extracted folder. Once it has been loaded, you should see the file directory on the left. 

Click **Terminal** at the top toolbar and select **New Terminal**.

The terminal should open up on the bottom of the Visual Studio Code interface.

Set up a Python virtual environment and install the required packages using the following commands:

```bash
# from the repository root
python3 -m venv .venv
source .venv/bin/activate        # on Windows: .venv\Scripts\activate
pip install -r exercises/requirements.txt
```

Once done, you can head to Exercise 1.

## Exercises

- [Getting Started / System access](exercises/ex0/)
- [Exercise 1 - Tabular AI Orchestration](exercises/ex1/)
- [Exercise 2 - Build your Agent with Joule Studio & integrate SAP-RPT-1.6](exercises/ex2/)
- [Exercise 3 - Introduction to SAP-RPT-1.6](exercises/ex3/)

**IMPORTANT**

Your repo must contain the .reuse and LICENSES folder and the License section below. DO NOT REMOVE the section or folders/files. Also, remove all unused template assets(images, folders, etc) from the exercises folder. 

## Other Sessions

#### **AD262 | Agentic CAP: Build MCP servers and enterprise AI agents (Hands-on workshop)** ([Link](https://www.sap.com/events/teched/berlin/flow/sap/te26/catalog/page/catalog/session/1786525647304001OTzl))

> Learn how to turn apps based on SAP Cloud Application Programming Model (CAP) into enterprise AI agents using the model context protocol (MCP) and Agent2Agent protocol. With the integration of the SAP AI Core infrastructure, it’s straightforward to embed AI in apps based on CAP apps, such as including recommendations with the SAP-RPT-1 AI model.

**Slots:** 

- Tuesday, Oct 27 | 11:00 AM - 1:00 PM CET

- Wednesday, Oct 28 | 3:30 PM - 5:30 PM CET


#### **CT1093 | Beyond traditional machine learning: Putting SAP-RPT playground to the test (Community talk)** ([Link](https://www.sap.com/events/teched/berlin/flow/sap/te26/catalog/page/catalog/session/1784840363129001RY9e))

> Find out how the SAP-RPT playground environment challenges traditional machine learning for insurance fraud detection. Run the playground on a classification problem, test it under limited labeled data, and see how the results could evolve into a broader fraud intelligence workflow with Joule and graph-based context.

**Slots:** 

- Tuesday, Oct 27 | 1:30 PM - 1:50 PM CET


#### **DA205 | Agentic memory: Knowledge graph engine and recall in SAP HANA Cloud (Deep dive)** ([Link](https://www.sap.com/events/teched/berlin/flow/sap/te26/catalog/page/catalog/session/1785947648294001sOTX))

> Discover what SAP HANA Cloud contributes to agentic applications. Learn about the knowledge graph engine in SAP HANA Cloud and its role in agentic workflows, agentic memory and ways to let your agent learn, and SAP AI Core infrastructure integration, which lets your database talk to LLMs and tabular foundation models like the SAP-RPT-1 AI model.

**Slots:** 

- Tuesday, Oct 27 | 2:00 PM - 2:45 PM CET
- Thursday, Oct 29 | 11:00 AM - 11:45 AM CET


#### **DA262 | Get hands on with tabular AI and forecasting models in SAP HANA Cloud (Hands-on workshop)** ([Link](https://www.sap.com/events/teched/berlin/flow/sap/te26/catalog/page/catalog/session/1785950867623001MHDu))

> Learn how to leverage new SAP HANA Cloud database AI capabilities, such as generating on-the-fly predictions using tabular AI models like the SAP-RPT-1 AI model or generating ad hoc forecasts using time series foundation models. Get inspired by innovations, like automated machine learning (AutoML), from the predictive analysis library for SAP HANA.

**Slots:** 

- Wednesday, Oct 28 | 10:30 AM - 12:30 PM CET


#### **DA263 | Knowledge graph and agent memory: Build an agent that remembers (Hands-on workshop)** ([Link](https://www.sap.com/events/teched/berlin/flow/sap/te26/catalog/page/catalog/session/1785951246358001oDkD))

> Explore what SAP HANA Cloud contributes to agentic applications. Learn about the knowledge graph engine in SAP HANA Cloud and its role in agentic workflows, agentic memory and ways to let your agent learn, and SAP AI Core infrastructure integration, which lets your database talk to LLMs and tabular foundation models like the SAP-RPT-1 AI model.

**Slots:** 

- Wednesday, Oct 28 | 3:30 PM - 5:30 PM CET


#### **RA109 | SAP-RPT and TabPFN: Foundation models built for structured data (Deep dive)** ([Link](https://www.sap.com/events/teched/berlin/flow/sap/te26/catalog/page/catalog/session/1785751135193001Ly8X))

> Explore the future of tabular AI on SAP and predictive insights at scale with the latest generation of specialized tabular foundation models and features. Take a deep dive with SAP and Prior Labs to see how tabular foundation models revolutionize decision-making grounded in your relational enterprise data.

**Slots:**

- Thursday, Oct 29 | 10:00 AM - 10:45 AM CET


#### **RA162 | SAP-RPT and TabPFN: Get started with tabular foundation models (Hands-on workshop)** ([Link](https://www.sap.com/events/teched/berlin/flow/sap/te26/catalog/page/catalog/session/1785751580777001pW43))

> Get hands-on experience with tabular AI, guided by experts from SAP and Prior Labs. We'll explore the unique capabilities within each model family, then operationalize predictions with SAP AI Core. You'll learn how to build a workflow using tabular orchestration and connect your data to obtain real-time predictions.

**Slots:**
- Thursday, Oct 29 | 11:30 AM - 1:30 PM CET


## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright 2026 SAP SE or an SAP affiliate company and contributors. Please see our [LICENSE](LICENSE) for copyright and license information. Detailed information including third-party components and their licensing/copyright information is available [via the REUSE tool](https://api.reuse.software/info/github.com/SAP/teched2026-XP269).
