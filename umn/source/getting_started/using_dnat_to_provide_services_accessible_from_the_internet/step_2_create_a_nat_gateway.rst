:original_name: nat_qs_0009.html

.. _nat_qs_0009:

Step 2: Create a NAT Gateway
============================

Scenarios
---------

This section guides you on how to create a NAT gateway to enable your servers to access the Internet or to provide services available from the Internet.

Prerequisites
-------------

-  When creating a NAT gateway, you must specify its VPC, subnet, and type.
-  Ensure that the VPC does not have the default route.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Under **Network**, choose **NAT Gateway**.

#. On the displayed page, click **Create NAT Gateway**.

#. Configure the parameters as prompted. For details, see :ref:`Table 1 <nat_qs_0009__nat_qs_0003_table27487005195751>`.

   .. _nat_qs_0009__nat_qs_0003_table27487005195751:

   .. table:: **Table 1** Parameter descriptions

      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                           |
      +===================================+=======================================================================================================================================================================+
      | Region                            | The region where the NAT gateway is located.                                                                                                                          |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name                              | The name of the NAT gateway. The name can include up to 64 characters and can include digits, letters, underscores (_), and hyphens (-).                              |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | The VPC that the NAT gateway belongs to. Select a VPC which is not used by any other NAT gateways and has no default route.                                           |
      |                                   |                                                                                                                                                                       |
      |                                   | You can change the VPC only when you are creating the NAT gateway. After the NAT gateway is created, you cannot modify the VPC.                                       |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Subnet                            | The subnet of the VPC that the NAT gateway belongs to.                                                                                                                |
      |                                   |                                                                                                                                                                       |
      |                                   | The subnet must have at least one available IP address.                                                                                                               |
      |                                   |                                                                                                                                                                       |
      |                                   | You can change the subnet only when you are creating the NAT gateway. After the NAT gateway is created, you cannot change the subnet.                                 |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Type                              | The type of the NAT gateway.                                                                                                                                          |
      |                                   |                                                                                                                                                                       |
      |                                   | The value can be **Small**, **Medium**, **Large**, and **Extra-large**. You can click **Learn more** on the page to view details about each type.                     |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Supplementary information about the NAT gateway. The description can contain up to 255 characters.                                                                    |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | The NAT gateway tag, which consists of a key and value pair. You can add a maximum of 20 tags to each NAT gateway.                                                    |
      |                                   |                                                                                                                                                                       |
      |                                   | The tag key and value must meet the requirements listed in :ref:`Table 2 <nat_qs_0009__nat_qs_0003_en-us_topic_0030971658_en-us_topic_0013935842_table248245914136>`. |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _nat_qs_0009__nat_qs_0003_en-us_topic_0030971658_en-us_topic_0013935842_table248245914136:

   .. table:: **Table 2** Tag requirements

      +-----------------------------------+---------------------------------------------------------------------+
      | Parameter                         | Requirement                                                         |
      +===================================+=====================================================================+
      | Key                               | -  Cannot be left blank.                                            |
      |                                   | -  Must be unique for each NAT gateway.                             |
      |                                   | -  Contains a maximum of 36 characters.                             |
      |                                   | -  Can contain only the following character types:                  |
      |                                   |                                                                     |
      |                                   |    -  Letter                                                        |
      |                                   |    -  Digits                                                        |
      |                                   |    -  Special characters, including hyphens (-) and underscores (_) |
      +-----------------------------------+---------------------------------------------------------------------+
      | Value                             | -  Can contain a maximum of 43 characters.                          |
      |                                   | -  Can contain only the following character types:                  |
      |                                   |                                                                     |
      |                                   |    -  Letter                                                        |
      |                                   |    -  Digits                                                        |
      |                                   |    -  Special characters, including hyphens (-) and underscores (_) |
      +-----------------------------------+---------------------------------------------------------------------+

#. Click **Create Now**. Confirm the NAT gateway information on the displayed page.

#. If you do not need to modify the information, click **Submit**.

   It takes 1 to 5 minutes to create a NAT gateway.

#. In the NAT gateway list, view the NAT gateway status. For details about the NAT gateway status, see :ref:`Table 3 <nat_qs_0009__nat_qs_0003_table1213025114317>`.

   .. _nat_qs_0009__nat_qs_0003_table1213025114317:

   .. table:: **Table 3** NAT gateway status

      ======== =================================
      Status   Description
      ======== =================================
      Running  The NAT gateway is running.
      Creating The NAT gateway is being created.
      Updating The NAT gateway is being updated.
      Deleting The NAT gateway is being deleted.
      Frozen   The NAT gateway has been frozen.
      Abnormal The NAT gateway is abnormal.
      ======== =================================

.. |image1| image:: /_static/images/en-us_image_0141273034.png
