[Azure Training Material](../index.md) >> [Azure load-balancing options](index.md) >> [Azure Traffic Manager](.)

## Azure Traffic Manager

>Azure Traffic Manager is a DNS-based traffic load balancer that enables you to distribute traffic optimally to services across global Azure regions, while providing high availability and responsiveness.

* Traffic manager profile  
* Traffic manager endpoints  

### Traffic Manager example (MS docs)
Contoso Corp have developed a new partner portal. The URL for this portal is https://partners.contoso.com/login.aspx. The application is hosted in three regions of Azure. To improve availability and maximize global performance, they use Traffic Manager to distribute client traffic to the closest available endpoint.  

To achieve this configuration, they complete the following steps:  

1. Deploy three instances of their service. The DNS names of these deployments are 'contoso-us.cloudapp.net', 'contoso-eu.cloudapp.net', and 'contoso-asia.cloudapp.net'.  
2. Create a Traffic Manager profile, named 'contoso.trafficmanager.net', and configure it to use the 'Performance' traffic-routing method across the three endpoints.
3. Configure their vanity domain name, 'partners.contoso.com', to point to 'contoso.trafficmanager.net', using a DNS CNAME record.




![image](https://user-images.githubusercontent.com/13016162/71672789-feba6d00-2d9c-11ea-8039-7aca0cd0794d.png)
