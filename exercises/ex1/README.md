# Exercise 1 - Tabular AI Orchestration

In this exercise, you will learn how to set up the Tabular AI orchestration workflow to run predictions with the SAP-RPT-1.6 model at scale. 

Tabular AI Orchestration has three components:

```
Your App/Agent
   |
   v
Tabular AI Orchestration  <-- single endpoint
   |              |
   v              v
Context        SAP-RPT model
Selector       (model of your choice)
   |
Context Registry
(your registered dataset)
```

## Quick setup - Preparing the .env file

You should see a `.env.example` file. Rename the file to `.env` and open this file. You would see that we have already prepared some environment variables in the file:
```
AICORE_AUTH_URL=<url in XP269-SK.json file>/oauth/token
AICORE_CLIENT_ID=<clientid in XP269-SK.json file>
AICORE_CLIENT_SECRET=<clientsecret in XP269-SK.json file>
AICORE_RESOURCE_GROUP=default
AICORE_BASE_URL=<AI_API_URL in XP269-SK.json file>
RPT_DEPLOYMENT_ID=YOUR_SAP_RPT_1.6_DEPLOYMENT_ID
TABORC_HDLFS_HOST=<hdlfs-host in XP269-SK.json file>
TABORC_HDLFS_URL=<hdlfs-url in XP269-SK.json file>
```

Unzip `credentials.zip` file and open the `XP269-SK.json` file. Copy the required values from this JSON file into your `.env` file.

## Exercise 1.1 - Set up Tabular AI Orchestration (Design Time Steps)

After completing these steps, using the uploaded datasets, you have created:
1. A data destination
2. A tabular artifact
3. A scenario configuration

Now, you are ready to try running the workflow and obtain predictions from the SAP-RPT-1.6 model.

## Exercise 1.2 - Live Predictions with Tabular AI Orchestration (Run Time Steps)

>Note: Tabular AI orchestration has already been deployed for you. Simply use the provided deployment ID to start running predictions during the session. If you would like to repeat this on your own setup, we have provided a code block that you can use (currently greyed out).

After completing these steps, you will have successfully obtained model predictions from SAP-RPT-1.6 via the Tabular AI orchestration workflow.

## Summary

Now, that you have tried Tabular orchestration. Head to [Exercise 3 - Building an agent with Tabular AI Orchestration and SAP-RPT-1.6](/exercises/ex3/README.md).