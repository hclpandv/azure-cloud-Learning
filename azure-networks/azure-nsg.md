[Azure Training Material](../index.md) >> [Azure Networks](index.md) >> [nsg](.)
## Azure Network Security Group

* nsg can be applied to a network or on a NIC (n/w interface card, on vm or load balancer)

```bash
az network nsg list --output table
```
![image](https://user-images.githubusercontent.com/13016162/71404971-06ba3480-265a-11ea-88b6-f183025dc0e0.png)

```bash
az network nsg rule list --resource-group viki-resource-group --nsg-name viki-sbnt-frontend-nsg --output table
```
![image](https://user-images.githubusercontent.com/13016162/71405376-403f6f80-265b-11ea-8beb-48ed653eaf91.png)
