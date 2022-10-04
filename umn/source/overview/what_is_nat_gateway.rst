:original_name: en-us_topic_0086739762.html

.. _en-us_topic_0086739762:

What Is NAT Gateway?
====================

The NAT Gateway service provides network address translation (NAT) with 20 Gbit/s of bandwidth for Elastic Cloud Servers (ECSs) and Bare Metal Servers (BMSs) in a Virtual Private Cloud (VPC), or servers that connect to a VPC through Direct Connect or Virtual Private Network (VPN) in on-premises data centers, allowing these servers to share elastic IP addresses (EIPs) to access the Internet or to provide services accessible from the Internet.

NAT Gateway supports source NAT (SNAT) and destination NAT (DNAT).

-  SNAT translates private IP addresses into EIPs, allowing servers in a VPC to share an EIP to access the Internet in a secure and efficient way.

   :ref:`Figure 1 <en-us_topic_0086739762__fig439218341217>` shows the SNAT architecture.

   .. _en-us_topic_0086739762__fig439218341217:

   .. figure:: /_static/images/en-us_image_0201532914.png
      :alt: **Figure 1** SNAT architecture


      **Figure 1** SNAT architecture

-  DNAT enables servers in a VPC to share an EIP to provide services accessible from the Internet through IP address mapping or port mapping.

   :ref:`Figure 2 <en-us_topic_0086739762__fig13245644101814>` shows the DNAT architecture.

   .. _en-us_topic_0086739762__fig13245644101814:

   .. figure:: /_static/images/en-us_image_0201532822.png
      :alt: **Figure 2** DNAT architecture


      **Figure 2** DNAT architecture
