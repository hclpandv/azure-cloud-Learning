[Azure Training Material](../index.md) >> [Azure Networks](index.md) >> [Azure Firewall](.)

## Azure Firewall

>Azure Firewall is a managed, cloud-based network security service that protects your Azure Virtual Network resources. It's a fully stateful firewall as a service with built-in high availability and unrestricted cloud scalability.

>Azure Firewall can be configured during deployment to span multiple Availability Zones for increased availability. With Availability Zones, your availability increases to 99.99% uptime. For more information, see the Azure Firewall Service Level Agreement (SLA). The 99.99% uptime SLA is offered when two or more Availability Zones are selected.
>You can also associate Azure Firewall to a specific zone just for proximity reasons, using the service standard 99.95% SLA.

#### Azure Firewall vs NSG

An NSG is a firewall, albeit a very basic one.  It’s a software defined solution that filters traffic at the Network layer.  However, Azure Firewall is more robust.  It’s a managed firewall service that can filter and analyze L3-L4 traffic, as well as L7 application traffic.  Azure Firewall provides the same capabilities as an NSG, plus more i.e. Source and Destination N/w address translation(SNAT/DNAT) and threat intelligence based filtering

* Source and Destination N/w address translation(SNAT/DNAT)  

>It’s possible to configure Azure Firewall with a Public IP address (PIP) that can be used to masked the IP address of Azure Resources that are sending out via the Firewall.
>
>Source Destination Address Translation is used to translate incoming traffic to the firewall’s Public IP to the Private IP addresses of the VNet.

* threat intelligence based filtering  


#### Typical Use Case

* Create a workload subnet, jumpbox subnet and AzureFirewallSubnet (Jumpbox VM will be able to connect workload VMs where traffic is routed via firewall) 


* Hub-Spoke vnet setup

![image](https://user-images.githubusercontent.com/13016162/71760701-ac399780-2ee7-11ea-8f74-6c4b440f0fd7.png)

