:original_name: en-us_topic_0086739762.html

.. _en-us_topic_0086739762:

What Is NAT Gateway?
====================

NAT Gateway is a network address translation (NAT) service. It can be a public NAT gateway or a private NAT gateway.

Public NAT Gateways
-------------------

A public NAT gateway enables cloud and on-premises servers in a private subnet to share an EIP to access the Internet or provide services accessible from the Internet. Cloud servers are ECSs in a VPC. On-premises servers are servers in on-premises data centers that connect to a VPC through Direct Connect or Virtual Private Network (VPN). A public NAT gateway supports up to 20 Gbit/s of bandwidth.

Public NAT gateways offer source NAT (SNAT) and destination NAT (DNAT).

-  SNAT translates private IP addresses into EIPs so that traffic from a private network can go out to the Internet.

   shows how an SNAT rule works.


   .. figure:: /_static/images/en-us_image_0000001412689457.png
      :alt: **Figure 1** NAT gateway with an SNAT rule

      **Figure 1** NAT gateway with an SNAT rule

-  DNAT enables servers in a VPC, regardless of if they are in the same AZ, to share an EIP to provide services accessible from the Internet. With an EIP, a public NAT gateway forwards the Internet requests from only a specific port and over a specific protocol to a specific port of a server, or it can forward all requests to the server regardless of which port they originated on.

   shows how a DNAT rule works.


   .. figure:: /_static/images/en-us_image_0000001362209618.png
      :alt: **Figure 2** NAT gateway with a DNAT rule

      **Figure 2** NAT gateway with a DNAT rule

Private NAT Gateways
--------------------

Private NAT gateways provide network address translation, allowing ECSs in a VPC to communicate with servers in other VPCs or on-premises data centers. You can configure SNAT and DNAT rules for a NAT gateway to translate the source and destination IP addresses of originating packets into a transit IP address.

Specifically,

-  SNAT enables servers in a VPC, regardless of if they are in the same AZ, to share a transit IP address to access on-premises data centers or other VPCs.
-  DNAT enables servers in a VPC, regardless of if they are in the same AZ, to share the same transit IP address to provide services accessible from on-premises data centers or other VPCs.

**Transit Subnet**

A transit subnet is a transit network and is the subnet to which the transit IP address belongs.

**Transit IP Address**

A transit IP address is a private IP address that can be assigned from a transit subnet. Cloud servers in your VPC can share a transit IP address to access on-premises networks or other VPCs.

**Transit VPC**

A transit VPC is where a transit subnet belongs to.


.. figure:: /_static/images/en-us_image_0000002238621008.png
   :alt: **Figure 3** Private NAT gateway

   **Figure 3** Private NAT gateway

How Do I Access the NAT Gateway Service?
----------------------------------------

You can access the NAT Gateway service through the management console or using HTTPS-based APIs.

-  Management console

   Log in to the management console and choose **NAT Gateway** from the service list.

-  APIs

   If you need to integrate NAT Gateway on the cloud platform into your own system, use APIs to access NAT Gateway.
