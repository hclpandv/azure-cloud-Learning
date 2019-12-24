[<<back](index.md)
## Azure Availability Set

```bash
az vm availability-set list --output table
```

![image](https://user-images.githubusercontent.com/13016162/71400089-af14cc80-264b-11ea-8818-bac252050f4b.png)


```bash
az vm show -d \
--ids $(az vm availability-set show --resource-group viki-resource-group --name viki-webserver-avail-set --query "virtualMachines[].id" --output tsv) \
--query "[].{VMS:name, PublicIps:publicIps}" \
-o table
```
