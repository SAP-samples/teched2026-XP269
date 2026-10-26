# Exercise 2 - Agents with Tabular AI Orchestration and SAP-RPT-1.6

In this exercise, you will use Joule Studio 2.0 to see how you can build and further extend an agent that can run predictions at scale using SAP-RPT-1.6 via the Tabular AI orchestration workflow. 

## Signing In
1. Open **Joule Studio**: [`here`](https://747401964.eu10.sapdas.cloud.sap/new/build)
2. Sign in with the user account that comes with your provided laptop.
3. Make sure you are on the **Develop** tab.
4. You should see a panel of Solutions and the `TabAI TechEd Demo` agent is within that list. Click on the 3-dots icon and click **Download ZIP**. 
5. Click on down icon on the right of the **New** button.
6. Select **Upload Solution** and choose the downloaded zip file. 
7. You would see a warning message. Click **Copy** to proceed.
8. You should see that this opens up a new agent solution, from your uploaded zip file. 
9. Now confirm that the MCP and base skills are available.

The team has already deployed the **MCP server** (in Cloud Foundry) and the **base skills**, and connected them to Joule Studio. Do a quick check to ensure that you can see/use them. 

In Joule Studio, you should see the `TabAI TechEd Demo` agent in the list. Select it and click **Preview with Mock Data** and click **tabai-agent** to start a new chat. Type in a smoke-test prompt:
```
List the base skills you have available.
```
![alt text](/assets/ex2-JS.png)

[Optional] You can do a second smoke-test prompt to confirm that the MCP can reach the backend:

```
Check that the tabular prediction service is healthy.
```
![alt text](/assets/ex2-tabhealth.png)

## Getting Started with Exercise 2
There are 3 sub-exercises, as follow:
1. [Exercise 2.1 - Predict and Visualize](../ex2/ex2-1/README.md)
2. [Exercise 2.2 - Build a custom skill](../ex2/ex2-2/README.md)
3. [Exercise 2.3 - Take it further](../ex2/ex2-3/README.md)

