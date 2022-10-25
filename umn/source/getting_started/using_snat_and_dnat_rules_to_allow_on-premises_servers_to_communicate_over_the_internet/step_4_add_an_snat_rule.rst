:original_name: nat_qs_0017.html

.. _nat_qs_0017:

Step 4: Add an SNAT Rule
========================

Scenarios
---------

After a NAT gateway is created, you can add SNAT rules for it. With SNAT rules, servers that are connected to a VPC using Direct Connect can access the Internet by sharing an EIP.

An SNAT rule is configured for one CIDR block. If servers that are connected to a VPC using Direct Connect are in multiple CIDR blocks, you can create several SNAT rules to make the servers share one or more EIPs.

Prerequisites
-------------

A NAT gateway has been created.

Procedure
---------

#. Log in to the management console.

2. Click |image1| in the upper left corner and select the desired region and project.

3. Under **Network**, choose **NAT Gateway**.

4. On the displayed page, click the name of the NAT gateway for which you want to add the SNAT rule.

5. On the **SNAT Rules** tab, click **Add SNAT Rule**.


   .. figure:: /_static/images/en-us_image_0201532881.png
      :alt: **Figure 1** Add SNAT Rule

      **Figure 1** Add SNAT Rule

6. Configure the parameters as prompted. For details, see :ref:`Table 1 <nat_qs_0017__table4272024117597>`.

   .. _nat_qs_0017__table4272024117597:

   .. table:: **Table 1** Parameter descriptions

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                         |
      +===================================+=====================================================================================================================================================================================================================================+
      | Scenario                          | Select **Direct Connect** if servers in your data center need to access the Internet.                                                                                                                                               |
      |                                   |                                                                                                                                                                                                                                     |
      |                                   | The servers in your data center that are connected to a VPC through Direct Connect or VPN can access the Internet through the SNAT rule.                                                                                            |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | CIDR Block                        | On-premises servers whose IP address in this CIDR block can access the Internet through the SNAT rule.                                                                                                                              |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | EIP                               | The EIP used for accessing the Internet.                                                                                                                                                                                            |
      |                                   |                                                                                                                                                                                                                                     |
      |                                   | You can select an EIP that either is not bound to any resource, has been bound to a DNAT rule with **Port Type** set to **Specific port** of the current NAT gateway, or has been bound to an SNAT rule of the current NAT gateway. |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

7. Click **OK**.

8. View details in the SNAT rule list. If **Status** is **Running**, the rule has been added.

   .. note::

      You can add multiple SNAT rules for a NAT gateway to suite your service requirements.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
