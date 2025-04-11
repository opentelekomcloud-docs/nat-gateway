:original_name: nat_privatenat_0002.html

.. _nat_privatenat_0002:

Creating a Private NAT Gateway
==============================

Scenarios
---------

You need a private NAT gateway to enable servers in your VPC to access or provide services accessible from on-premises data centers and other VPCs.

Notes and Constraints
---------------------

-  Manually add routes in a VPC to connect it to a remote private network through a VPC peering connection, Direct Connect, or VPN connection.
-  SNAT and DNAT rules cannot share a transit IP address.
-  The total number of DNAT and SNAT rules that can be added on a private NAT gateway varies with the private NAT gateway specifications.

   -  Small: 20 or less
   -  Medium: 50 or less
   -  Large: 200 or less
   -  Extra-large: 500 or less

.. caution::

   When you create a private NAT gateway, you must specify its VPC, subnet, and specifications.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image2| to expand the service list and choose **Network** > **NAT Gateway**.

   The NAT Gateway console is displayed.

#. In the navigation pane on the left, choose **NAT Gateway** > **Private NAT Gateways**.

#. On the **Private NAT Gateways** page, click **Create Private NAT Gateway**.

#. Configure required parameters. For details, see :ref:`Table 1 <nat_privatenat_0002__table68520404137>`.


   .. figure:: /_static/images/en-us_image_0000002082113222.png
      :alt: **Figure 1** Create Private NAT Gateway

      **Figure 1** Create Private NAT Gateway

   .. _nat_privatenat_0002__table68520404137:

   .. table:: **Table 1** Descriptions of private NAT gateway parameters

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                          |
      +===================================+======================================================================================================================================================================================+
      | Region                            | The region where the private NAT gateway is located.                                                                                                                                 |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name                              | The name of the private NAT gateway.                                                                                                                                                 |
      |                                   |                                                                                                                                                                                      |
      |                                   | Enter up to 64 characters. Only digits, letters, underscores (_), hyphens (-), and periods (.) are allowed.                                                                          |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | The VPC that the private NAT gateway belongs to.                                                                                                                                     |
      |                                   |                                                                                                                                                                                      |
      |                                   | The selected VPC cannot be changed after the private NAT gateway is created.                                                                                                         |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Subnet                            | The subnet that the private NAT gateway belongs to.                                                                                                                                  |
      |                                   |                                                                                                                                                                                      |
      |                                   | The subnet must have at least one available IP address.                                                                                                                              |
      |                                   |                                                                                                                                                                                      |
      |                                   | The selected subnet cannot be changed after the private NAT gateway is created.                                                                                                      |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Specifications                    | The specifications of the private NAT gateway.                                                                                                                                       |
      |                                   |                                                                                                                                                                                      |
      |                                   | The value can be **Extra-large**, **Large**, **Medium**, or **Small**. For details about specifications, see section "NAT Gateway Specifications" in *NAT Gateway Service Overview*. |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Enterprise Project                | The enterprise project that the private NAT gateway belongs to.                                                                                                                      |
      |                                   |                                                                                                                                                                                      |
      |                                   | If an enterprise project has been configured, select the enterprise project.                                                                                                         |
      |                                   |                                                                                                                                                                                      |
      |                                   | If you have not configured any enterprise project, select the **default** enterprise project.                                                                                        |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Supplementary information about the private NAT gateway.                                                                                                                             |
      |                                   |                                                                                                                                                                                      |
      |                                   | Enter up to 255 characters. Angle brackets (<>) are not allowed.                                                                                                                     |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **Create Now**.

Other Operations
----------------

-  :ref:`Assigning a Transit IP Address <nat_privatenatexsub_0001>`
-  :ref:`Adding an SNAT Rule <nat_privatesnat_0001>`
-  :ref:`Adding a DNAT Rule <nat_privatednat_0001>`
-  :ref:`Managing Private NAT Gateways <nat_privatenat_0003>`

.. |image1| image:: /_static/images/en-us_image_0000002118113858.png
.. |image2| image:: /_static/images/en-us_image_0000002015300802.png
