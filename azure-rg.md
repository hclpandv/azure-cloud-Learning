## Resource Group

* A top leval container which holds all you resources in azure.
* You cant not create any resource without creating a resource group.  
* Like a project in GCP etc.
* You must specify the Location where your resource group is created

## Location

* Regions where azure services are available globally i.e. westus, westindia, eastus etc
* There could be multiple Availability zones in a perticular region

![image](https://user-images.githubusercontent.com/13016162/71368614-6bc84880-25ce-11ea-806f-f391dca812b3.png)

![image](https://user-images.githubusercontent.com/13016162/71369015-7df6b680-25cf-11ea-843f-742119f20bd4.png)

![image](https://user-images.githubusercontent.com/13016162/71369629-5b659d00-25d1-11ea-9168-adf29a4be25a.png)

## List Resources in resource group

```bash
# Azure-cli
az resource list --resource-group 'viki-resource-group'
```

```powershell
# Powershell
Get-AzResource -ResourceGroupName viki-resource-group
```

![image](https://user-images.githubusercontent.com/13016162/71370454-fbbcc100-25d3-11ea-8265-1dac5f586df5.png)
