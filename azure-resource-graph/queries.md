### Query with machine type


* Get all Subscriptions

```
resourcecontainers
| where type == "microsoft.resources/subscriptions"
| project name, subscriptionId
```

* Get all VMs order by Name

```
Resources
| where type =~ 'Microsoft.Compute/virtualMachines'
| project name, resourceGroup, location, MachineType = properties.hardwareProfile.vmSize, subscriptionId, type
| order by name desc
```

* Get all VMs count by subscriptionId

```
Resources
| where type =~ 'Microsoft.Compute/virtualMachines'
| project name, resourceGroup, location, MachineType = properties.hardwareProfile.vmSize, subscriptionId, type
| summarize count () by subscriptionId
```

* VMs with Size, Pvt Ip

```
Resources
| where type == "microsoft.compute/virtualmachines"
| extend os = properties.storageProfile.imageReference.offer
| extend sku = properties.storageProfile.imageReference.sku
| extend hostName = properties.osProfile.computerName
| extend MachineType = properties.hardwareProfile.vmSize
| mvexpand nic = properties.networkProfile.networkInterfaces
| extend nicId = tostring(nic.id)
| project subscriptionId, vmName = name, resourceGroup, location, nicId, hostName, MachineType, os, sku
| join kind=leftouter (
	Resources
	| where type == "microsoft.network/networkinterfaces"
	| mvexpand ipconfig=properties.ipConfigurations
	| extend privateIp = ipconfig.properties.privateIPAddress
    | project nicId = id, privateIp
) on nicId
| project-away nicId1
| project subscriptionId, vmName, resourceGroup, location, privateIp, hostName, MachineType, os, sku
| order by subscriptionId desc
```

* VMs with Size, Pvt Ip, subscriptionName

```
Resources
| where type == "microsoft.compute/virtualmachines"
| extend os = properties.storageProfile.imageReference.offer
| extend sku = properties.storageProfile.imageReference.sku
| extend hostName = properties.osProfile.computerName
| extend MachineType = properties.hardwareProfile.vmSize
| mvexpand nic = properties.networkProfile.networkInterfaces
| extend nicId = tostring(nic.id)
| project subscriptionId, vmName = name, resourceGroup, location, nicId, hostName, MachineType, os, sku
| join kind=leftouter (
	Resources
	| where type == "microsoft.network/networkinterfaces"
	| mvexpand ipconfig=properties.ipConfigurations
	| extend privateIp = ipconfig.properties.privateIPAddress
    | project nicId = id, privateIp
) on nicId
| project-away nicId1
| project subscriptionId, vmName, resourceGroup, location, privateIp, hostName, MachineType, os, sku
| join kind=leftouter (
    resourcecontainers
    | where type == "microsoft.resources/subscriptions"
    | project subscriptionName = name, subscriptionId
) on subscriptionId
| project subscriptionId, subscriptionName, vmName, resourceGroup, location, privateIp, hostName, MachineType, os, sku
| order by subscriptionName
```




