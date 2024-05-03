
### Overview
---
In this exercise, you create a secure Container Apps environment and deploy a container app.
   
### Key Aspects
---
- Azure Container Apps 
- Azure Container Apps Environment

### Environment
---
Microsoft Azure Portal
- Valid Subscription

### Actions
---
Prepare your environment
  - Sign in to the Azure portal

  - Open the Cloud Shell using the Bash environment

  - Install the Azure Container Apps extension for CLI
```
az extension add --name containerapp --upgrade
```

  - Register the Microsoft.App namespace
```
az provider register --namespace Microsoft.App
```

  - Register the Microsoft.OperationalInsights provider for the Azure Monitor Log Analytics workspace
```
az provider register --namespace Microsoft.OperationalInsights
``` 

  - Set environment variables
```
DEFAULT_LOCATION="eastus2"
DEFAULT_CURRENTDATETIME="20240503174500"
DEFAULT_RESOURCEGROUP="myresourcegroup${DEFAULT_CURRENTDATETIME}"
ACANAME="aca${DEFAULT_CURRENTDATETIME}"
ACAENVIRONMENTNAME="acaenv${DEFAULT_CURRENTDATETIME}"
```

  - Create a resource group
```
az group create --name ${ACAENVIRONMENTNAME} --location ${DEFAULT_LOCATION}
``` 

Create a Container App

- Create an Azure Container Apps environment
```
az containerapp env create --name ${ACAENVIRONMENTNAME} --location ${DEFAULT_LOCATION} --resource-group ${DEFAULT_RESOURCEGROUP}
```

- Create a container app
```
az containerapp env create --name ${ACAENVIRONMENTNAME} --location ${DEFAULT_LOCATION} --resource-group ${DEFAULT_RESOURCEGROUP}
```

Clean up resources

- Delete the Resource Groups and its content
```
az group delete --name ${DEFAULT_RESOURCEGROUP} --no-wait
```

### Media
---
![image](https://github.com/ViCunha/Lab-Azure-AzureContainerApp-OnAzurePortal/assets/65992033/c9f3f5ca-dbd5-4f96-860a-8051861ad72b)

---
![image](https://github.com/ViCunha/Lab-Azure-AzureContainerApp-OnAzurePortal/assets/65992033/c5625a8c-d0cb-4be2-89ad-f71f2884d104)

---
![image](https://github.com/ViCunha/Lab-Azure-AzureContainerApp-OnAzurePortal/assets/65992033/40ff5195-9db3-466e-b1ec-33c95f3a47b6)


### References
---
- [Exercise - Deploy a container app](https://learn.microsoft.com/en-us/training/modules/implement-azure-container-apps/3-exercise-deploy-app)
