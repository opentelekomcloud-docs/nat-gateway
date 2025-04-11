:original_name: nat_privatenatexsub_0001.html

.. _nat_privatenatexsub_0001:

Assigning a Transit IP Address
==============================

Scenarios
---------

Servers in a VPC can use the same transit IP address to access or provide services accessible from on-premises data centers or other VPCs.

A transit IP address can be mapped to multiple backend servers through different ports.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image2| to expand the service list and choose **Network** > **NAT Gateway**.

   The NAT Gateway console is displayed.

#. In the navigation pane on the left, choose **NAT Gateway** > **Private NAT Gateways**.

#. On the **Private NAT Gateways** page, click **Transit IP Addresses**.


   .. figure:: /_static/images/en-us_image_0000002120569941.png
      :alt: **Figure 1** Assign Transit IP Address

      **Figure 1** Assign Transit IP Address

#. Configure required parameters. For details, see :ref:`Table 1 <nat_privatenatexsub_0001__nat_qs_0023_table0141919163217>`.

   .. _nat_privatenatexsub_0001__nat_qs_0023_table0141919163217:

   .. table:: **Table 1** Parameter descriptions of a transit IP address

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                               |
      +===================================+===========================================================================================================================+
      | Transit VPC                       | VPC to which the transit IP address is located.                                                                           |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------+
      | Transit Subnets                   | A transit subnet is a transit network and is the subnet to which the transit IP address belongs.                          |
      |                                   |                                                                                                                           |
      |                                   | The subnet must have at least one available IP address.                                                                   |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------+
      | Transit IP Address                | The transit IP address can be assigned in either of the following ways:                                                   |
      |                                   |                                                                                                                           |
      |                                   | **Automatic**: The system automatically assigns a transit IP address.                                                     |
      |                                   |                                                                                                                           |
      |                                   | **Manual**: You need to manually assign a transit IP address.                                                             |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------+
      | IP Address                        | This parameter is only available when you set **Transit IP Address** to **Manual**.                                       |
      |                                   |                                                                                                                           |
      |                                   | Click **View In-Use IP Address** to view in-use IP addresses in the selected subnet.                                      |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------+
      | Enterprise Project                | The enterprise project to which the transit IP address belongs.                                                           |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | The transit IP address tag, which consists of a key and value pair. You can add up to 20 tags to each transit IP address. |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000002118113858.png
.. |image2| image:: /_static/images/en-us_image_0000002015300802.png
