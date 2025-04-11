:original_name: nat_qs_0023.html

.. _nat_qs_0023:

Step 3: Create a Private NAT Gateway
====================================

Scenarios
---------

To enable communications between your service VPC and a remote private network or VPC, create a private NAT gateway.

Prerequisites
-------------

You have determined the transit IP addresses to be used for NAT in the transit VPC.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click **Service List** in the upper left corner. Under **Network**, select **NAT Gateway**. In the navigation pane on the left, choose **Private NAT Gateways**.

   The **Private NAT Gateways** page is displayed.

#. Click **Create** **Private NAT Gateway** in the upper right corner.

#. Configure required parameters. For details, see :ref:`Table 1 <nat_qs_0023__nat_qs_0003_table27487005195751>`.

   .. _nat_qs_0023__nat_qs_0003_table27487005195751:

   .. table:: **Table 1** Descriptions of private NAT gateway parameters

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                              |
      +===================================+==========================================================================================================================+
      | Region                            | The region where the private NAT gateway is located                                                                      |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Name                              | The name of the private NAT gateway                                                                                      |
      |                                   |                                                                                                                          |
      |                                   | Enter up to 64 characters. Only digits, letters, underscores (_), and hyphens (-) are allowed.                           |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | The service VPC that the private NAT gateway belongs to                                                                  |
      |                                   |                                                                                                                          |
      |                                   | The selected VPC cannot be changed after the private NAT gateway is created.                                             |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Subnet                            | The subnet of the service VPC                                                                                            |
      |                                   |                                                                                                                          |
      |                                   | The subnet must have at least one available IP address.                                                                  |
      |                                   |                                                                                                                          |
      |                                   | The selected subnet cannot be changed after the private NAT gateway is created.                                          |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Specifications                    | The specifications of the private NAT gateway                                                                            |
      |                                   |                                                                                                                          |
      |                                   | The value can be **Small**, **Medium**, **Large**, or **Extra-large**.                                                   |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | The private NAT gateway tag. A tag is a key-value pair. You can add up to 20 tags to each NAT gateway.                   |
      |                                   |                                                                                                                          |
      |                                   | For details, see :ref:`Tag requirements <nat_qs_0023__en-us_topic_0030971658_en-us_topic_0013935842_table248245914136>`. |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Supplementary information about the private NAT gateway                                                                  |
      |                                   |                                                                                                                          |
      |                                   | Enter up to 255 characters. Angle brackets (<>) are not allowed.                                                         |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+

   .. _nat_qs_0023__en-us_topic_0030971658_en-us_topic_0013935842_table248245914136:

   .. table:: **Table 2** Tag requirements

      +-----------------------------------+---------------------------------------------------------------------+
      | Parameter                         | Requirement                                                         |
      +===================================+=====================================================================+
      | Key                               | -  Cannot be left blank.                                            |
      |                                   | -  Must be unique for each NAT gateway.                             |
      |                                   | -  Can contain a maximum of 36 characters.                          |
      |                                   | -  Can contain only the following character types:                  |
      |                                   |                                                                     |
      |                                   |    -  Letters                                                       |
      |                                   |    -  Digits                                                        |
      |                                   |    -  Special characters, including hyphens (-) and underscores (_) |
      +-----------------------------------+---------------------------------------------------------------------+
      | Value                             | -  Can contain a maximum of 43 characters.                          |
      |                                   | -  Can contain only the following character types:                  |
      |                                   |                                                                     |
      |                                   |    -  Letters                                                       |
      |                                   |    -  Digits                                                        |
      |                                   |    -  Special characters, including hyphens (-) and underscores (_) |
      +-----------------------------------+---------------------------------------------------------------------+

#. Click **Create Now**.

#. In the private NAT gateway list, check the gateway status.

#. On the **Private NAT Gateways** page, click **Transit IP Addresses**.


   .. figure:: /_static/images/en-us_image_0000002120569941.png
      :alt: **Figure 1** Assign Transit IP Address

      **Figure 1** Assign Transit IP Address

#. Configure required parameters. For details, see :ref:`Table 3 <nat_qs_0023__table0141919163217>`.

   .. _nat_qs_0023__table0141919163217:

   .. table:: **Table 3** Parameter descriptions of a transit IP address

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                              |
      +===================================+==========================================================================================================================+
      | Transit VPC                       | Specifies the VPC to which the transit IP address belongs.                                                               |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Transit Subnets                   | A transit subnet is a transit network and is the subnet to which the transit IP address belongs.                         |
      |                                   |                                                                                                                          |
      |                                   | The subnet must have at least one available IP address.                                                                  |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Transit IP Address                | The transit IP address can be assigned in either of the following ways:                                                  |
      |                                   |                                                                                                                          |
      |                                   | **Automatic**: The system automatically assigns a transit IP address.                                                    |
      |                                   |                                                                                                                          |
      |                                   | **Manual**: You need to manually assign a transit IP address.                                                            |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | IP Address                        | This parameter is only available when you set **Transit IP Address** to **Manual**.                                      |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Enterprise Project                | Specifies the enterprise project to which the transit IP address belongs.                                                |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | The private NAT gateway tag. A tag is a key-value pair. You can add up to 20 tags to each NAT gateway.                   |
      |                                   |                                                                                                                          |
      |                                   | For details, see :ref:`Tag requirements <nat_qs_0023__en-us_topic_0030971658_en-us_topic_0013935842_table248245914136>`. |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+

#. Set **Transit IP Address** to **Automatic** and click **OK**.

.. |image1| image:: /_static/images/en-us_image_0283962445.png
