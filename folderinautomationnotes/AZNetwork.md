| Category                            | Key services                                                                                        | Primary use case                                | Learn more                                                                                                                                                                       |
| ----------------------------------- | --------------------------------------------------------------------------------------------------- | ----------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Networking foundation               | Virtual Network, Private Link, Azure DNS, Azure Bastion, Route Server, NAT Gateway, Traffic Manager | Core connectivity for resources in Azure        | [Azure networking foundation services](https://learn.microsoft.com/en-us/azure/networking/foundations/network-foundations-overview)                                              |
| Load balancing and content delivery | Load Balancer, Application Gateway, Azure Front Door                                                | Distribute and optimize application traffic     | [Azure load balancing and content delivery services](https://learn.microsoft.com/en-us/azure/networking/load-balancer-content-delivery/load-balancing-content-delivery-overview) |
| Hybrid connectivity                 | VPN Gateway, ExpressRoute, Virtual WAN, Peering Service                                             | Connect on-premises networks to Azure           | [Azure hybrid connectivity services](https://learn.microsoft.com/en-us/azure/networking/hybrid-connectivity/hybrid-connectivity)                                                 |
| Network security                    | Firewall Manager, Firewall, Web Application Firewall, DDoS Protection                               | Protect applications and resources from threats | [Azure network security services](https://learn.microsoft.com/en-us/azure/networking/security/network-security)                                                                  |
| Network management and monitoring   | Network Watcher, Azure Monitor, Azure Virtual Network Manager                                       | Manage and monitor network resources            | [Azure network management and monitoring services](https://learn.microsoft.com/en-us/azure/networking/monitoring-management/)                                                    |
| Container networking                | Container network security, Container network observability                                         | Secure and observe AKS container traffic        | [Advanced Container Networking Services](https://learn.microsoft.com/en-us/azure/aks/advanced-container-networking-services-overview)                                            |
## Azure networking foundation services
### Virtual network

# Azure Network Watcher
Network Watcher consists of three major sets of tools and capabilities:

- Monitoring
    - Topology
    - Connection monitor
- Network diagnostic
    - IP flow verify
    - NSG diagnostics
    - Next hop
    - Effective security rules
    - Connection troubleshoot
    - Packet capture
    - VPN troubleshoot
- Traffic
    - Flow logs
    - Traffic analytics
![[Pasted image 20260909172724.png]]

Network Watcher offers two monitoring tools that help you view and monitor resources:

- Topology
- Connection monitor
Network Watcher offers two monitoring tools that help you view and monitor resources:

- Topology
- Connection monitor
## Network Watcher Topology tool
- - Subnets
- Network interfaces
- Network security groups
- Load balancer
- Load balancer health probes
- Public IP addresses
- Virtual network peering
- Virtual network gateways
- VPN gateway connections
- Virtual machines
- Virtual Machine Scale Sets
# When to use Azure Network Watcher
 For example, you can use the tools included in Azure Network Watcher in the following scenarios:

- Resolve connectivity issues related to IaaS VMs.
- Troubleshoot VPN connections.
- Determine cross region network latencies.

# Azure Application Gateway
zure Application Gateway is an Azure service that processes traffic to web apps that are hosted on a pool of web servers. The processing performed by Azure Application Gateway includes load balancing HTTP traffic and inspecting traffic using web application firewall. It also includes encrypting traffic between users and an application gateway, and encrypting traffic between application servers and an application gateway.
![[Pasted image 20260909174645.png
Application Gateway uses a round-robin process to load balance requests to the servers in each back-end pool. Session stickiness ensures client requests in the same session are routed to the same back-end server. Session stickiness is especially important with e-commerce applications where you don’t want a transaction to be disrupted because the load balancer bounces it around between back-end servers.

Azure Application Gateway includes the following features:

- Support for the HTTP, HTTPS, HTTP/2, and WebSocket protocols.
- A web application firewall to protect against web application vulnerabilities.
- End-to-end request encryption.
- Autoscaling to dynamically adjust capacity as your web traffic load change.
- Connection draining allowing graceful removal of back-end pool members during planned service updates.
# How Azure Application Gateway works
![[Pasted image 20260909175303.png]]
## Load balancing in Application Gateway
Application Gateway uses a round-robin mechanism to automatically load balance the requests sent to the servers in each back-end pool. Load-balancing works with the Open Systems Interconnection (OSI) Layer 7 routing implemented by Application Gateway routing, which means that it load balances requests based on the routing parameters (host names and paths) used by the Application Gateway rules. In comparison, other load balancers, such as Azure Load Balancer, function at the OSI Layer 4 level and distribute traffic based on the IP address of the target of a request.

You can configure session stickiness if you need to ensure that all requests for a client in the same session are routed to the same server in a back-end pool.
## Web application firewall

The web application firewall (WAF) is an optional component that handles incoming requests before they reach a listener. The web application firewall checks each request for many common threats based on the Open Web Application Security Project (OWASP). Common threats include: SQL-injection, Cross-site scripting, Command injection, HTTP request smuggling, HTTP response splitting, Remote file inclusion, Bots, crawlers, and scanners, and HTTP protocol violations and anomalies.
## Application Gateway routing

When the gateway routes a client request to a web server in the back-end pool, it uses a set of rules configured for the gateway to determine where the request should go. There are two primary methods of routing this client request traffic: path-based routing and multiple-site routing.

Azure Application Gateway can meet your organization’s needs for the following reasons:

- Azure Application Gateway routing allows traffic to be directed from an endpoint in Azure to a back-end pool made up of servers running in Adatum’s on-premises datacenter. The health-probe functionality of Azure Application Gateway ensures that traffic isn't being directed to any server that becomes unavailable.
- Azure Application Gateway TLS termination functionality reduces the amount of CPU capacity that servers in the back-end pool allocate to encryption and decryption operations.
- Azure Application Gateway allows Adatum to use a web application firewall to block cross-site scripting and SQL injection traffic before it reaches servers in the back-end pool.
- Azure Application Gateway supports session affinity. This support is required because the several web applications deployed by Adatum use user session state information stored locally on individual servers in the back-end pool.
## When not to use Azure Application Gateway

Azure Application Gateway isn’t appropriate if you have a web application that doesn’t require load balancing. For example, if you have a web application that only receives a small amount of traffic and the existing infrastructure already competently deals with the existing load, there's no need to deploy a back-end pool of web apps or virtual machines and no need for Application Gateway.

Azure provides other load balancing solutions, including Azure Front Door, Azure Traffic Manager, and Azure Load Balancer. The following list describes the differences between these services:

- **Front Door** is an application delivery network that provides global load balancing and site acceleration service for web applications. It offers Layer 7 capabilities for your application like TLS/SSL offload, path-based routing, fast failover, web application firewall, and caching to improve performance and high-availability of your applications. Choose this option in scenarios such as load balancing a web app deployed across multiple Azure regions.
- **Traffic Manager** is a DNS-based traffic load balancer that enables you to distribute traffic optimally to services across global Azure regions while providing high availability and responsiveness. Because Traffic Manager is a DNS-based load-balancing service, it load-balances only at the domain level. For that reason, it can't fail over as quickly as Front Door because of common challenges around DNS caching and systems not honoring DNS TTLs.
- **Azure Load Balancer** is a high-performance, ultra low-latency Layer 4 load-balancing service (inbound and outbound) for all UDP and TCP protocols. Azure Load Balancer is built to handle millions of requests per second while ensuring that your solution is highly available. Azure Load Balancer is zone-redundant, ensuring high availability across availability zones. Azure Load Balancer works within a region rather than globally.