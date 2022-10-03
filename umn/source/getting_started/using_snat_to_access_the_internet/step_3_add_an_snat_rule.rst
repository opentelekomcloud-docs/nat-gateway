:original_name: nat_qs_0004.html

.. _nat_qs_0004:

Step 3: Add an SNAT Rule
========================

Scenarios
---------

After a NAT gateway is created, add SNAT rules. With an SNAT rule, your servers in a specified subnet can access the Internet by sharing the same EIP.

Each SNAT rule is configured for one subnet or CIDR block. If there are multiple subnets or CIDR blocks in a VPC, you can create several SNAT rules to allow multiple servers to share EIPs.

**Prerequisites**
-----------------

A NAT gateway has been created.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Under **Network**, choose **NAT Gateway**.

#. On the displayed page, click the name of the NAT gateway for which you want to add the SNAT rule.

#. On the **SNAT Rules** tab, click **Add SNAT Rule**.


   .. figure:: /_static/images/en-us_image_0201532851.png
      :alt: **Figure 1** Add SNAT Rule


      **Figure 1** Add SNAT Rule

#. Configure the parameters as prompted. :ref:`Table 1 <nat_qs_0004__table1966804261617>` describes the parameters.

   .. _nat_qs_0004__table1966804261617:

   .. table:: **Table 1** Parameter descriptions

      +-----------------------+---------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Condition                                                                                               | Description                                                                                                                                                                                                                         |
      +=======================+=========================================================================================================+=====================================================================================================================================================================================================================================+
      | Scenario              | N/A                                                                                                     | Select **VPC** if your servers in a VPC will use the SNAT rule to access the Internet.                                                                                                                                              |
      |                       |                                                                                                         |                                                                                                                                                                                                                                     |
      |                       |                                                                                                         | Different servers in a VPC can share the same EIP to access the Internet.                                                                                                                                                           |
      +-----------------------+---------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Type                  | This parameter is available only when you select **VPC** for **Scenario**.                              | You can set it to **Subnet** or **Custom** based on service requirements.                                                                                                                                                           |
      |                       |                                                                                                         |                                                                                                                                                                                                                                     |
      |                       |                                                                                                         | Select **Subnet** if all servers in a VPC subnet need to access the Internet through the SNAT rule.                                                                                                                                 |
      |                       |                                                                                                         |                                                                                                                                                                                                                                     |
      |                       |                                                                                                         | Select **Custom** if only specific servers in a VPC subnet need to access the Internet through the SNAT rule.                                                                                                                       |
      +-----------------------+---------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Subnet                | This parameter is available only when you select **VPC** for **Scenario**, and **Subnet** for **Type**. | The subnet in which servers can access the Internet through the SNAT rule.                                                                                                                                                          |
      +-----------------------+---------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | EIP                   | N/A                                                                                                     | The EIP used for accessing the Internet.                                                                                                                                                                                            |
      |                       |                                                                                                         |                                                                                                                                                                                                                                     |
      |                       |                                                                                                         | You can select an EIP that either is not bound to any resource, has been bound to a DNAT rule with **Port Type** set to **Specific port** of the current NAT gateway, or has been bound to an SNAT rule of the current NAT gateway. |
      +-----------------------+---------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   .. note::

      You can add multiple SNAT rules for a NAT gateway to suite your service requirements.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
