
# XP269 - Bring the power of Tabular AI foundation models to your SAP Agents

## Description

This repository contains the material for the SAP TechEd 2026 session called XP269 - Bring the power of Tabular AI foundation models to your SAP Agents.

## Session Overview

Tabular AI Meets Intelligent Agents: Build Smarter with SAP RPT and TabPFN

Structured data is everywhere in the enterprise — and it's one of the most underutilised assets in AI-driven workflows. This session explores how tabular foundation models, specifically SAP RPT and TabPFN, are redefining what intelligent agents can do with structured information.

In this hands-on session, you will move beyond theory and directly experience how to integrate tabular AI models into the agent development lifecycle. From initial integration and iterative testing to rigorous benchmarking, you will gain practical skills to evaluate model performance and make informed design decisions for real-world use cases.

Whether you are building decision-support agents, automating data-driven processes, or optimising enterprise workflows, tabular foundation models offer a powerful new layer of intelligence. Join us to discover how turning structured data into smarter, faster, and more reliable agent decisions is not just possible — it is within reach today.

## Hands-On Architecture

![Hands-On Architecture](assets/XP267_architecture.svg)

## What You Will Learn

Tabular AI in Action: Building Smarter Agents with SAP RPT, TabPFN & Joule Studio

In this hands-on session, you will learn how to harness the power of tabular foundation models — SAP RPT and TabPFN — to build intelligent agents that make smarter decisions from structured enterprise data.

Working directly inside Joule Studio's ProCode flow, you will go through the full agent development lifecycle: integrating tabular AI models, writing and testing agent logic in code, and benchmarking model performance against real-world scenarios. This is not a demo you watch — it is a workflow you execute.

By the end of this session, you will know how to:

Set up and integrate SAP RPT and TabPFN within the Joule Studio ProCode flow
Design and implement agents that reason over structured, tabular data
Test agent behaviour and validate outputs across different data scenarios
Apply benchmarking techniques to compare model accuracy and guide design decisions
Turn structured enterprise data into actionable, AI-driven decisions inside your agent pipelines

## Prerequisites / Setup

Before starting the exercises, set up a Python virtual environment and install the required packages:

```bash
# from the repository root
python3 -m venv .venv
source .venv/bin/activate        # on Windows: .venv\Scripts\activate
pip install -r exercises/requirements.txt
```

## Exercises

- [Getting Started / System access](exercises/ex0/)
- [Exercise 1 - Tabular AI Orchestration](exercises/ex1/)
- [Exercise 2 - Build your Agent with Joule Studio & integrate SAP-RPT-1.6](exercises/ex2/)
- [Exercise 3 - Introduction to SAP-RPT-1.6](exercises/ex3/)

**IMPORTANT**

Your repo must contain the .reuse and LICENSES folder and the License section below. DO NOT REMOVE the section or folders/files. Also, remove all unused template assets(images, folders, etc) from the exercises folder. 

## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (20xx-)20xx SAP SE or an SAP affiliate company and <your-project> contributors. Please see our [LICENSE](LICENSE) for copyright and license information. Detailed information including third-party components and their licensing/copyright information is available [via the REUSE tool](https://api.reuse.software/info/github.com/SAP/<your-project>).
