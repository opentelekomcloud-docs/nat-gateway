:original_name: nat_privatenat_0001.html

.. _nat_privatenat_0001:

Overview of Private NAT Gateways
================================

Private NAT Gateways
--------------------

Private NAT gateways provide private address translation services for ECSs and BMSs in a VPC. You can configure SNAT and DNAT rules to translate the source and destination IP addresses into transit IP addresses, so that servers in the VPC can communicate with other VPCs or on-premises data centers.

Specifically:

-  SNAT enables servers in a VPC, regardless of if they are in the same AZ, to share a transit IP address to access on-premises data centers or other VPCs.
-  DNAT enables servers in a VPC, regardless of if they are in the same AZ, to share a transit IP address to provide services accessible from on-premises data centers or other VPCs.

**Transit Subnet**

A transit subnet functions as a transit network. You can configure a transit IP address for the transit subnet so that servers in a local VPC can share the transit IP address to access on-premises data centers or other VPCs.

**Transit VPC**

The transit VPC is the VPC that the transit subnet is a part of.


.. figure:: /_static/images/en-us_image_0000002238621008.png
   :alt: **Figure 1** Private NAT gateway

   **Figure 1** Private NAT gateway

Application Scenarios
---------------------

-  Connecting VPCs with overlapping CIDR blocks

   You can configure two private NAT gateways for two VPCs with overlapping CIDR blocks. Then, add SNAT and DNAT rules on the two private NAT gateways to enable servers in the two VPCs to use the transit IP addresses to communicate with each other.

   In the following figure, there are two transit VPCs and two private NAT gateways. ECS-A's IP address 192.168.0.100 in VPC A is translated to 10.0.0.165, and ECS-B's IP address 192.168.0.101 in VPC B is translated to 10.0.1.166. A VPC peering connection can then be established between the two transit VPCs to enable communication between VPC A and VPC B.


   .. figure:: /_static/images/en-us_image_0000002273233725.png
      :alt: **Figure 2** Connecting VPCs with overlapping CIDR blocks

      **Figure 2** Connecting VPCs with overlapping CIDR blocks

-  Migrating workloads to the cloud without changing the network topology or accessing regulatory agencies from specific IP addresses

   Organizations may want to migrate their workloads to the cloud without making any changes to their existing network topology. They may also have to access regulatory agencies from specific IP addresses as required by these agencies. A private NAT gateway is a good choice.

   The following figure represents an enterprise network where the subnets of different departments overlap. A private NAT gateway allows the enterprise to keep the existing network topology unchanged while migrating their workloads to the cloud. In this example, the private NAT gateway maps the IP address of each department to 10.0.0.33 so that each department can use 10.0.0.33 to securely access the regulatory agency.


   .. figure:: /_static/images/en-us_image_0000001165391199.png
      :alt: **Figure 3** Migrating workloads to the cloud without changing the network topology or accessing regulatory agencies from specific IP addresses

      **Figure 3** Migrating workloads to the cloud without changing the network topology or accessing regulatory agencies from specific IP addresses

Differences Between Public and Private NAT Gateways
---------------------------------------------------

Public NAT gateways use SNAT rules to map private IP addresses to EIPs, so that servers in a VPC can share an EIP to access the Internet. DNAT rules enable the servers to share an EIP to provide services accessible from the Internet.

Private NAT gateways use SNAT rules to map private IP addresses to transit IP addresses, so that servers in a VPC can access on-premises data centers or other VPCs. DNAT rules enable the servers to share the transit IP address to provide services accessible from the private network.

:ref:`Table 1 <nat_privatenat_0001__table3924422163214>` describes the differences between public and private NAT gateways.

.. _nat_privatenat_0001__table3924422163214:

.. table:: **Table 1** Differences between public and private NAT gateways

   +---------------------------+-----------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------+
   | Item                      | Public NAT Gateway                                              | Private NAT Gateway                                                                                           |
   +===========================+=================================================================+===============================================================================================================+
   | Function                  | Connects a private network to the Internet                      | Connects private networks                                                                                     |
   +---------------------------+-----------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------+
   | SNAT                      | Enables access to the Internet                                  | Enables access to on-premises data centers or other VPCs                                                      |
   +---------------------------+-----------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------+
   | DNAT                      | Allows servers to provide services accessible from the Internet | Allows servers to provide services accessible from on-premises data centers or other VPCs in private networks |
   +---------------------------+-----------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------+
   | IP type for communication | EIP                                                             | Transit IP address                                                                                            |
   +---------------------------+-----------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------+

Process for Deploying a Private NAT Gateway
-------------------------------------------

The process for deploying a private NAT gateway is as follows:


.. figure:: /_static/images/en-us_image_0000002273332561.png
   :alt: **Figure 4** Process for deploying a private NAT gateway

   **Figure 4** Process for deploying a private NAT gateway

If you want to use a private NAT gateway to connect your VPC to on-premises data centers or other VPCs, refer to :ref:`Accessing On-premises Data Centers or Other VPCs <nat_privatenat_0007>`.
