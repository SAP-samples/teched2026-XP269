# Exercise 2 - Building an agent with Tabular AI Orchestration and SAP-RPT-1.6

In this exercise, you will use Joule Studio 2.0 to build an agent that can run predictions at scale using SAP-RPT-1.6 via the Tabular AI orchestration workflow. 

## Quick Setup
1. Open **Joule Studio**: [`here`](https://747401964.eu10.sapdas.cloud.sap/new/)
2. Sign in with the user account that comes with your provided laptop.
3. Confirm that the MCP and base skills are available

The team has already deployed the **MCP server** (in Cloud Foundry) and the **base skills**, and connected them to Joule. Do a quick check to ensure that you can see/use them. 

In Joule, start a new chat and a smoke-test prompt:
```
List the base skills you have available.
```
<TODO: add a screenshot>

[Optional] You can do a second smoke-test prompt to confirm that the MCP can reach the backend:

```
Check that the tabular prediction service is healthy.
```
<TODO: add a screenshot>

You **should NOT** need to:
- Upload the dataset — it is already in HDLFS/S3 (see [../data/README.md](../data/README.md)).
- Handle tokens, client secrets, or AI Core keys as the MCP takes care of that for you.
- Install Joule, Python, or any CLI.

## Getting Started with Exercise 2
There are 3 sub-exercises, as follow:
1. [Exercise 2.1 - Predict and Visualize](../ex2/ex2-1/README.md)
2. [Exercise 2.2 - Build a custom skill](../ex2/ex2-2/README.md)
3. [Exercise 2.3 - Take it further](../ex2/ex2-3/README.md)
