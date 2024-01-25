:original_name: nat_pro_0002.html

.. _nat_pro_0002:

Application Scenarios
=====================

Allowing a Private Network to Access the Internet Using SNAT
------------------------------------------------------------

If your servers in a VPC need to access the Internet, you can configure SNAT rules to let these servers use EIPs to access the Internet without exposing their private IP addresses. You can configure only one SNAT rule for each subnet in a VPC, and select one or more EIPs for each SNAT rule. NAT Gateway provides different numbers of connections, and you can create multiple SNAT rules to meet your service requirements.

:ref:`Figure 1 <nat_pro_0002__fig1463533919456>` shows how servers in a VPC access the Internet using SNAT.

.. _nat_pro_0002__fig1463533919456:

.. figure:: /_static/images/en-us_image_0201532867.png
   :alt: **Figure 1** Allowing a private network to access the Internet using SNAT

   **Figure 1** Allowing a private network to access the Internet using SNAT

Allowing Internet Users to Access a Service in a Private Network Using DNAT
---------------------------------------------------------------------------

DNAT rules enable servers in a VPC to provide services accessible from the Internet.

After receiving requests from a specific port over a specific protocol, the public NAT gateway can forward the requests to a specific port of a server through port mapping. The NAT gateway can also forward all requests destined for an EIP to a specific server through IP address mapping.

One DNAT rule can be configured for each server. If there are multiple servers, you can create multiple DNAT rules to map one or more EIPs to the private IP addresses of these servers.

:ref:`Figure 2 <nat_pro_0002__fig1553173645114>` shows how servers in a VPC provide services accessible from the Internet using DNAT. Servers in the following figure can be an ECS or a BMS.

.. _nat_pro_0002__fig1553173645114:

.. figure:: /_static/images/en-us_image_0201532856.png
   :alt: **Figure 2** Allowing Internet users to access a service in a private network using DNAT

   **Figure 2** Allowing Internet users to access a service in a private network using DNAT

Allowing On-premises Servers to Communicate with the Internet
-------------------------------------------------------------

In certain Internet, gaming, e-commerce, and financial scenarios, a large number of servers in a private cloud are connected to a VPC through Direct Connect or VPN. If such servers need secure, high-speed Internet access or need to provide services accessible from the Internet, you can deploy a NAT gateway and configure SNAT and DNAT rules to meet their requirements. Typical scenarios include Internet, games, e-commerce, and finance across clouds.

:ref:`Figure 3 <nat_pro_0002__fig19180043184010>` shows how to communicate with the Internet at a high speed.

.. _nat_pro_0002__fig19180043184010:

.. figure:: /_static/images/en-us_image_0201532887.png
   :alt: **Figure 3** Allowing on-premises servers to communicate with the Internet

   **Figure 3** Allowing on-premises servers to communicate with the Internet
