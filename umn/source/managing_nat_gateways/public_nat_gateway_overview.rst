:original_name: en-us_topic_0000001557248825.html

.. _en-us_topic_0000001557248825:

Public NAT Gateway Overview
===========================

A public NAT gateway enables cloud and on-premises servers in a private subnet to access the Internet or provide services accessible from the Internet. Cloud servers are in a VPC. On-premises servers are servers in on-premises data centers that connect to a VPC through Direct Connect or VPN. A public NAT gateway supports up to 20 Gbit/s of bandwidth.

The process of using a public NAT gateway is as follows.


.. figure:: /_static/images/en-us_image_0260388437.png
   :alt: **Figure 1** Process of using a public NAT gateway

   **Figure 1** Process of using a public NAT gateway

.. note::

   An SNAT rule and a DNAT rule cannot share the same EIP. If you need to create an SNAT rule and a DNAT rule, assign two EIPs.
