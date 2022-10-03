:original_name: en-us_topic_0127489529.html

.. _en-us_topic_0127489529:

Adding an SNAT Rule
===================

Scenarios
---------

After a NAT gateway is created, add SNAT rules. With the SNAT rule, servers in a VPC subnet or servers that are connected to a VPC through Direct Connect or VPN can access the Internet by sharing an EIP.

Each SNAT rule is configured for one subnet. If there are multiple subnets in a VPC, you can create several SNAT rules to share EIPs.

**Prerequisites**
-----------------

-  A NAT gateway has been created.

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

#. Configure the parameters as prompted. For details, see :ref:`Table 1 <en-us_topic_0127489529__en-us_topic_0127293981_table4272024117597>`.

   .. _en-us_topic_0127489529__en-us_topic_0127293981_table4272024117597:

   .. table:: **Table 1** Parameter descriptions

      +-----------------------+---------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Condition                                                                                               | Description                                                                                                                                                                                                                         |
      +=======================+=========================================================================================================+=====================================================================================================================================================================================================================================+
      | Scenario              | N/A                                                                                                     | The scenarios where the SNAT rule is used.                                                                                                                                                                                          |
      |                       |                                                                                                         |                                                                                                                                                                                                                                     |
      |                       |                                                                                                         | Select **VPC** if your servers in a VPC need to access the Internet.                                                                                                                                                                |
      |                       |                                                                                                         |                                                                                                                                                                                                                                     |
      |                       |                                                                                                         | Select **Direct Connect** if the servers that are connected to a VPC through Direct Connect in your data center need to access the Internet.                                                                                        |
      +-----------------------+---------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Type                  | This parameter is available only when you select **VPC** for **Scenario**.                              | You can set it to **Subnet** or **Custom** based on service requirements.                                                                                                                                                           |
      |                       |                                                                                                         |                                                                                                                                                                                                                                     |
      |                       |                                                                                                         | Select **Subnet** if all servers in a VPC subnet need to access the Internet through the SNAT rule.                                                                                                                                 |
      |                       |                                                                                                         |                                                                                                                                                                                                                                     |
      |                       |                                                                                                         | Select **Custom** if only specific servers in a VPC subnet need to access the Internet through the SNAT rule.                                                                                                                       |
      +-----------------------+---------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Subnet                | This parameter is available only when you select **VPC** for **Scenario**, and **Subnet** for **Type**. | The subnet in which servers can access the Internet through the SNAT rule.                                                                                                                                                          |
      +-----------------------+---------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | EIP                   | -  This parameter is available only when you select **VPC** for **Scenario**.                           | The EIP used for accessing the Internet.                                                                                                                                                                                            |
      |                       | -  This parameter is available only when you select **Direct Connect** for **Scenario**.                |                                                                                                                                                                                                                                     |
      |                       |                                                                                                         | You can select an EIP that either is not bound to any resource, has been bound to a DNAT rule with **Port Type** set to **Specific port** of the current NAT gateway, or has been bound to an SNAT rule of the current NAT gateway. |
      +-----------------------+---------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   .. note::

      You can add multiple SNAT rules for a NAT gateway to suite your service requirements.

.. |image1| image:: /_static/images/en-us_image_0201532864.png
