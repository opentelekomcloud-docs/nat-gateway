:original_name: nat_pro_0002.html

.. _nat_pro_0002:

Application Scenarios
=====================

Using SNAT to Enable Servers to Access the Internet
---------------------------------------------------

If your servers in a VPC require Internet access, you can use SNAT to let the servers share one or more EIPs to access the Internet without exposing their IP addresses. In a VPC, each subnet corresponds to an SNAT rule, and each SNAT rule is configured with an EIP. NAT Gateway provides different specifications to support different numbers of connections. You can create multiple SNAT rules to meet your service requirements.

:ref:`Figure 1 <nat_pro_0002__fig1463533919456>` shows how servers in a VPC access the Internet using SNAT.

.. _nat_pro_0002__fig1463533919456:

.. figure:: /_static/images/en-us_image_0201532867.png
   :alt: **Figure 1** Using SNAT to enable servers to access the Internet

   **Figure 1** Using SNAT to enable servers to access the Internet

Using DNAT to Allow Servers to Provide Services Accessible from the Internet
----------------------------------------------------------------------------

To allow your servers in a VPC to provide services accessible from the Internet, you can use DNAT.

You can associate an EIP with a DNAT rule. As requests with a specific protocol and port access the EIP, NAT Gateway only forwards requests to the port of the target server through the mapping between the ports. NAT Gateway can also forward requests on the EIP to your servers based on IP address mapping. NAT Gateway allows multiple servers to share an EIP, saving costs on bandwidth.

A DNAT rule is configured for one server. If there are multiple servers, you can create several DNAT rules to make the servers share one or more EIPs.

:ref:`Figure 2 <nat_pro_0002__fig1553173645114>` shows how servers in a VPC use DNAT to provide services accessible from the Internet. Servers in the following figure can be an ECS or a BMS.

.. _nat_pro_0002__fig1553173645114:

.. figure:: /_static/images/en-us_image_0201532856.png
   :alt: **Figure 2** Using DNAT to allow servers to provide services accessible from the Internet

   **Figure 2** Using DNAT to allow servers to provide services accessible from the Internet

Using SNAT or DNAT to Communicate with the Internet at a High Speed
-------------------------------------------------------------------

If a large number of servers in a private cloud or those connect to a VPC through Direct Connect or VPN need secure, high-speed Internet access or need to provide services accessible from the Internet, SNAT and DNAT provide this access. Typical scenarios include Internet, games, e-commerce, and finance across clouds.

:ref:`Figure 3 <nat_pro_0002__fig19180043184010>` shows how to communicate with the Internet at a high speed.

.. _nat_pro_0002__fig19180043184010:

.. figure:: /_static/images/en-us_image_0201532887.png
   :alt: **Figure 3** Using SNAT or DNAT to communicate with the Internet at a high speed

   **Figure 3** Using SNAT or DNAT to communicate with the Internet at a high speed
