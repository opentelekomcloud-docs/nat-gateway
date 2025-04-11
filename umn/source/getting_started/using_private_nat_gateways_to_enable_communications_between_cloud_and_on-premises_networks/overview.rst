:original_name: nat_qs_0020.html

.. _nat_qs_0020:

Overview
========

You can use a private NAT gateway to enable communications between cloud and on-premises networks.

The following figure shows how a private NAT gateway enables ECSs in a VPC to communicate with your on-premises data center that has been connected to the cloud using Direct Connect.


.. figure:: /_static/images/en-us_image_0000002267418193.png
   :alt: **Figure 1** Networking diagram

   **Figure 1** Networking diagram

The following configuration is used as an example. If you want to access the cloud through a VPN connection, see `Hybrid Cloud Deployment <https://docs.otc.t-systems.com/virtual-private-network/umn/overview/application_scenarios.html>`__.

In this example, the CIDR block of your on-premises data center is 10.0.0.0/24. The subnet of the transit VPC in the region is 10.1.0.0/24.

How networks are connected to each other

#. Your on-premises data center is connected to the transit VPC using Direct Connect.
#. The VPC where your services are deployed is connected to the transit VPC using a private NAT gateway.

This following figure shows the procedure.


.. figure:: /_static/images/en-us_image_0283618865.png
   :alt: **Figure 2** Procedure

   **Figure 2** Procedure
