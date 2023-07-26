:original_name: en-us_topic_0086739762.html

.. _en-us_topic_0086739762:

What Is NAT Gateway?
====================

NAT Gateway is a network address translation (NAT) service. It enables cloud and on-premises servers to share elastic IP addresses (EIPs) to access the Internet or to provide services accessible from the Internet. Cloud servers are Elastic Cloud Servers (ECSs) and Bare Metal Servers (BMSs) in a Virtual Private Cloud (VPC). On-premises servers are servers in on-premises data centers that connect to a VPC through Direct Connect or Virtual Private Network (VPN). NAT Gateway supports up to 20 Gbit/s of bandwidth.

NAT Gateway supports source NAT (SNAT) and destination NAT (DNAT).

-  SNAT translates private IP addresses into EIPs, allowing servers in a VPC to share an EIP to access the Internet in a secure and efficient way.


   .. figure:: /_static/images/en-us_image_0000001251223489.png
      :alt: **Figure 1** NAT gateway with an SNAT rule

      **Figure 1** NAT gateway with an SNAT rule

-  DNAT enables servers in a VPC to share an EIP to provide services accessible from the Internet through IP address mapping or port mapping.


   .. figure:: /_static/images/en-us_image_0000001206143558.png
      :alt: **Figure 2** NAT gateway with a DNAT rule

      **Figure 2** NAT gateway with a DNAT rule
