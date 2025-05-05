:original_name: nat_pro_0002.html

.. _nat_pro_0002:

Application Scenarios
=====================

Public NAT Gateway
------------------

-  **Allowing a private network to access the Internet using SNAT**

   If your servers in a VPC need to access the Internet, you can configure SNAT rules to let these servers use EIPs to access the Internet without exposing their private IP addresses. You can configure only one SNAT rule for each subnet in a VPC and select one or more EIPs for each SNAT rule. Public NAT Gateway provides different numbers of connections, and you can create multiple SNAT rules to meet your service requirements.

   shows how servers in a VPC access the Internet using SNAT.


   .. figure:: /_static/images/en-us_image_0000001435498145.png
      :alt: **Figure 1** Allowing a private network to access the Internet using SNAT

      **Figure 1** Allowing a private network to access the Internet using SNAT

-  **Allowing Internet users to access a service in a private network using DNAT**

   DNAT rules enable servers in a VPC to provide services accessible from the Internet.

   After receiving requests from a specific port over a specific protocol, the public NAT gateway can forward the requests to a specific port of a server through port mapping. The public NAT gateway can also forward all requests destined for an EIP to a specific server through IP address mapping.

   One DNAT rule can be configured for each server. If there are multiple servers, you can create multiple DNAT rules to map one or more EIPs to the private IP addresses of these servers.

   shows how servers (ECSs or BMSs) in a VPC provide services accessible from the Internet using DNAT.


   .. figure:: /_static/images/en-us_image_0000001385418792.png
      :alt: **Figure 2** Allowing Internet users to access a service in a private network using DNAT

      **Figure 2** Allowing Internet users to access a service in a private network using DNAT

-  **Allowing on-premises servers to communicate with the Internet**

   In certain Internet, gaming, e-commerce, and financial scenarios, a large number of servers in a private cloud are connected to a VPC through Direct Connect or VPN. If such servers need secure, high-speed Internet access or need to provide services accessible from the Internet, you can deploy a NAT gateway and configure SNAT and DNAT rules to meet their requirements.

   :ref:`Figure 3 <nat_pro_0002__fig1264218457350>` shows how to use SNAT and DNAT to provide high-speed Internet access or provide services accessible from the Internet.

   .. _nat_pro_0002__fig1264218457350:

   .. figure:: /_static/images/en-us_image_0000001385738376.png
      :alt: **Figure 3** Allowing on-premises servers to communicate with the Internet

      **Figure 3** Allowing on-premises servers to communicate with the Internet

Private NAT Gateway
-------------------

-  **Connecting VPCs with overlapping CIDR blocks**

   You can configure two private NAT gateways for two VPCs with overlapping CIDR blocks. Then, add SNAT and DNAT rules on the two private NAT gateways to enable servers in the two VPCs to use the transit IP addresses to communicate with each other.

   In the following figure, there are two transit VPCs and two private NAT gateways. ECS-A's IP address 192.168.0.100 in VPC A is translated to 10.0.0.165, and ECS-B's IP address 192.168.0.101 in VPC B is translated to 10.0.1.166. A VPC peering connection can then be established between the two transit VPCs to enable communication between VPC A and VPC B.


   .. figure:: /_static/images/en-us_image_0000002273233725.png
      :alt: **Figure 4** Connecting VPCs with overlapping CIDR blocks

      **Figure 4** Connecting VPCs with overlapping CIDR blocks

-  **Keeping the network topology while migrating workloads to the cloud, or accessing regulatory agencies from specific IP addresses**

   Organizations may want to migrate their workloads to the cloud without making any changes to their existing network topology. They may also have to access regulatory agencies from specific IP addresses as required by these agencies. A private NAT gateway is a good choice.

   Subnets of different departments in an enterprise network may overlap. A private NAT gateway allows the enterprise to keep the existing network topology unchanged while migrating their workloads to the cloud. In this example, the private NAT gateway maps the IP address of each department to 10.0.0.33 so that each department can use 10.0.0.33 to securely access the regulatory agency.


   .. figure:: /_static/images/en-us_image_0000001165391199.png
      :alt: **Figure 5** Migrating workloads to the cloud without changing the network topology or accessing regulatory agencies from specific IP addresses

      **Figure 5** Migrating workloads to the cloud without changing the network topology or accessing regulatory agencies from specific IP addresses
