### Query with machine type

```
Resources
| where type =~ 'Microsoft.Compute/virtualMachines'
| project name, resourceGroup, location, MachineType = properties.hardwareProfile.vmSize, subscriptionId, type
| order by name desc
```
