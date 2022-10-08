# azure-hub_spoke-terraform
Create a hub and spoke hybrid network topology in Azure using Terraform

In the hub and spoke topology, the hub is a VNet. The VNet acts as a central point of connectivity to your on-premises network. The spokes are VNets that peer with the hub, and can be used to isolate workloads. Traffic flows between the on-premises datacenter and the hub through an ExpressRoute or VPN gateway connection. The following image demonstrates the components in a hub and spoke topology:

![image](https://user-images.githubusercontent.com/115328290/194730470-bab60df2-4f71-4800-9873-9febcce3fd3c.png)

Preview the demo components
As you work through each article in this series, various components are defined in distinct Terraform scripts. The demo architecture created and deployed consists of the following components:

On-premises network. A private local-area network running with an organization. For hub and spoke reference architecture, a VNet in Azure is used to simulate an on-premises network.

VPN device. A VPN device or service provides external connectivity to the on-premises network. The VPN device may be a hardware appliance or a software solution.

Hub VNet. The hub is the central point of connectivity to your on-premises network and a place to host services. These services can be consumed by the different workloads hosted in the spoke VNets.

Gateway subnet. The VNet gateways are held in the same subnet.

Spoke VNets. Spokes can be used to isolate workloads in their own VNets, managed separately from other spokes. Each workload might include multiple tiers, with multiple subnets connected through Azure load balancers.

VNet peering. Two VNets can be connected using a peering connection. Peering connections are non-transitive, low latency connections between VNets. Once peered, the VNets exchange traffic by using the Azure backbone, without needing a router. In a hub and spoke network topology, VNet peering is used to connect the hub to each spoke. You can peer VNets in the same region, or different regions.


1.  Create a hub and spoke hybrid network topology in Azure using Terraform
2.  Create on-premises virtual network in Azure using Terraform
3.  Create a hub virtual network in Azure by using Terraform
4.  Create a hub virtual network appliance in Azure using Terraform
5.  Create a spoke network in Azure using Terraform
6. Validate a hub and spoke network in Azure using Terraform
