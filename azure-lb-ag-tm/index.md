[Azure Training Material](../index.md) >> [Azure load-balancing options](.)


>The term load balancing refers to the distribution of workloads across multiple computing resources. Load balancing aims to optimize resource use, maximize throughput, minimize response time, and avoid overloading any single resource. It can also improve availability by sharing a workload across redundant computing resources.

[Azure Load Balancer](azure-lb.md)  
[Azure Application Gateway](azure-ag.md)    
[Azure Traffic Manager](azure-tm.md)  
[Azure Front Door](azure-fd.md)

Table to show recommended use cases: 

| Service | Global/regional | Recommended traffic |
| ------- | --------------- | ------- |
| Azure Front Door | Global | HTTP(S) |
| Traffic Manager | Global | non-HTTP(S) |
| Application Gateway | Regional | HTTP(S) |
| Azure Load Balancer | Regional | non-HTTP(S) |
