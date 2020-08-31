# azure-arm-templates
A collection of Azure ARM templates to quickly provision necessary resources for an event stream and processing scenario:
- A resource group
- A CosmosDB account with a free-tier database and a document container using the Core SQL api
- A Storage account with a blob container
- An Event Hub namespace with an event hub instance
- A Stream Analytics job configured to use the event hub instance as input and output to the CosmosDB container 

Each resource has a dedicated parameters.json file.

When executing via Azure CLI provide the Resource Group name, i.e.:
```
az deployment group create
--name streamAnalyticsJob --resource-group <MYRGNAME>
--template-file "C:\path\to\file\streamAnalyticsJob.json"
--parameters "C:\path\to\file\streamAnalyticsJob.parameters.json
```