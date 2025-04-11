:original_name: nat_qs_0026.html

.. _nat_qs_0026:

Step 4: Add an SNAT Rule
========================

Scenarios
---------

After the private NAT gateway is created, add an SNAT rule with a transit IP address. It enables the access to on-premises data centers or other VPCs (by using their private addresses in the service VPC).

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click **Service List** in the upper left corner. Under **Network**, select **NAT Gateway**. In the navigation pane on the left, choose **Private NAT Gateways**.

   The **Private NAT Gateways** page is displayed.

#. In the private NAT gateway list, click the name of the private NAT gateway that you want to add an SNAT rule for.

#. On the **SNAT Rules** tab, click **Add SNAT Rule**.

#. Configure required parameters. For details, see :ref:`Table 1 <nat_qs_0026__table12205153618462>`.

   .. _nat_qs_0026__table12205153618462:

   .. table:: **Table 1** Description

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                              |
      +===================================+==========================================================================================================================+
      | Subnet                            | The subnet type of the SNAT rule. Select **Existing** or **Custom**.                                                     |
      |                                   |                                                                                                                          |
      |                                   | Select a subnet where IP address translation is required in the service VPC.                                             |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Monitoring                        | You can create alarm rules to watch the number of SNAT connections.                                                      |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Transit IP Address                | The transit IP address you assigned in :ref:`Step 3: Create a Private NAT Gateway <nat_qs_0023>`                         |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Provides supplementary information about the SNAT rule. Enter up to 255 characters. Angle brackets (<>) are not allowed. |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

#. View details in the SNAT rule list.

   If **Status** is **Running**, the rule has been added.

.. |image1| image:: /_static/images/en-us_image_0283962445.png
