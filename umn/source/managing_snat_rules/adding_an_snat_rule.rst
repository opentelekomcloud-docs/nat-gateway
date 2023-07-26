:original_name: en-us_topic_0127489529.html

.. _en-us_topic_0127489529:

Adding an SNAT Rule
===================

Scenarios
---------

After a NAT gateway is created, add SNAT rules. With the SNAT rule, servers in a VPC subnet or servers that are connected to a VPC through Direct Connect or VPN can access the Internet by sharing an EIP.

Each SNAT rule is configured for one subnet. If there are subnets in a VPC, you can create several SNAT rules to share EIPs.

Prerequisites
-------------

-  A NAT gateway has been created.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Under **Network**, select **NAT Gateway**.

#. On the displayed page, click the name of the NAT gateway for which you want to add the SNAT rule.

#. On the **SNAT Rules** tab, click **Add SNAT Rule**.


   .. figure:: /_static/images/en-us_image_0000001567533894.png
      :alt: **Figure 1** Add SNAT Rule

      **Figure 1** Add SNAT Rule

#. Configure the parameters as prompted. For details, see :ref:`Table 1 <en-us_topic_0127489529__en-us_topic_0127293981_table4272024117597>`.

   .. _en-us_topic_0127489529__en-us_topic_0127293981_table4272024117597:

   .. table:: **Table 1** Parameter descriptions

      +-----------------------+-----------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Condition                                                                                                       | Description                                                                                                                                                                                                                         |
      +=======================+=================================================================================================================+=====================================================================================================================================================================================================================================+
      | Scenario              | N/A                                                                                                             | The scenarios where the SNAT rule is used.                                                                                                                                                                                          |
      |                       |                                                                                                                 |                                                                                                                                                                                                                                     |
      |                       |                                                                                                                 | Select **VPC** if your servers in a VPC need to access the Internet.                                                                                                                                                                |
      |                       |                                                                                                                 |                                                                                                                                                                                                                                     |
      |                       |                                                                                                                 | Select **Direct Connect** if the servers that are connected to a VPC through Direct Connect in your data center need to access the Internet.                                                                                        |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | CIDR Block            | -  Configure this parameter when you select **VPC** for **Scenario** and **Custom** for **CIDR Block**.         | -  In a VPC scenario with **CIDR Block** as **Custom**, specify an IPv4 CIDR block, which must be a subset of the VPC subnets.                                                                                                      |
      |                       | -  This parameter is available only when you select **VPC** for **Scenario** and **Custom** for **CIDR Block**. | -  In a VPC scenario with **CIDR Block** as **Existing**, specify a VPC subnet in which servers can access the Internet through the SNAT rule.                                                                                      |
      |                       | -  Configure this parameter when you select **VPC** for **Scenario**.                                           | -  In a Direct Connect scenario, specify a CIDR block of your data center to enable your on-premises servers to access the Internet through the SNAT rule.                                                                          |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | EIP                   | N/A                                                                                                             | The EIP used for accessing the Internet.                                                                                                                                                                                            |
      |                       |                                                                                                                 |                                                                                                                                                                                                                                     |
      |                       |                                                                                                                 | You can select an EIP that either is not bound to any resource, has been bound to a DNAT rule with **Port Type** set to **Specific port** of the current NAT gateway, or has been bound to an SNAT rule of the current NAT gateway. |
      |                       |                                                                                                                 |                                                                                                                                                                                                                                     |
      |                       |                                                                                                                 | You can select multiple EIPs at once. Up to 20 EIPs can be selected for each SNAT rule. The EIP used for the SNAT rule is randomly chosen from the ones you select when you add the rule.                                           |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description           | N/A                                                                                                             | Supplementary information about the NAT gateway. The description can contain up to 255 characters.                                                                                                                                  |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   .. note::

      You can add multiple SNAT rules for a NAT gateway to suite your service requirements.

.. |image1| image:: /_static/images/en-us_image_0201532864.png
