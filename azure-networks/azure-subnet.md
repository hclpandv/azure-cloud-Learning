[<<back](index.md)
## Azure Subnet

* Split you private network into multiple subnets (ip based)

```bash
az network vnet list --output table
```

![image](https://user-images.githubusercontent.com/13016162/71399232-fe0d3280-2648-11ea-9464-4700736bc411.png)

```bash
az network vnet subnet list --resource-group 'viki-resource-group' --vnet-name 'viki-enterprise' --output table
```

![image](https://user-images.githubusercontent.com/13016162/71399045-6a3b6680-2648-11ea-85a6-3675c6018ddb.png)
