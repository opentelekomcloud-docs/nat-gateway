:original_name: nat_qs_0010.html

.. _nat_qs_0010:

Step 3: Add a DNAT Rule
=======================

Scenarios
---------

After a NAT gateway is created, you can add DNAT rules to allow servers in your VPC to provide services accessible from the Internet.

You can configure a DNAT rule for each port of a server. If multiple servers need to provide services accessible from the Internet, create multiple DNAT rules.

Prerequisites
-------------

A NAT gateway has been created.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Under **Network**, choose **NAT Gateway**.

#. On the displayed page, click the name of the NAT gateway for which you want to add the DNAT rule.

#. On the NAT gateway details page, click the **DNAT Rules** tab.

#. Click **Add DNAT Rule**.


   .. figure:: /_static/images/en-us_image_0201532842.png
      :alt: **Figure 1** Add DNAT Rule


      **Figure 1** Add DNAT Rule

#. Configure the parameters as prompted. For details, see :ref:`Table 1 <nat_qs_0010__table30787259144637>`.

   .. _nat_qs_0010__table30787259144637:

   .. table:: **Table 1** Parameter descriptions

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                         |
      +===================================+=====================================================================================================================================================================================================================================+
      | Scenario                          | Select **VPC** if your servers in a VPC will use the DNAT rule to provide services accessible from the Internet.                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                     |
      |                                   | Different servers in a VPC can share the same EIP to provide services accessible from the Internet.                                                                                                                                 |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Port Type                         | The port type. You can select **All ports** or **Specific port**.                                                                                                                                                                   |
      |                                   |                                                                                                                                                                                                                                     |
      |                                   | -  **All ports**: This is equivalent to assigning an EIP to a server. Any requests on the EIP will be forwarded by the NAT gateway to your server based on IP address mapping.                                                      |
      |                                   | -  **Specific port**: The NAT gateway only forwards requests with a specific protocol and port on the EIP to the corresponding port of the target server.                                                                           |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Protocol                          | The protocol can be TCP or UDP. This parameter is available if you select **Specific port** for **Port Type**. If you select **All ports**, the value of this parameter will be **All** by default.                                 |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | EIP                               | The EIP that will be used by the server to provide services accessible from the Internet.                                                                                                                                           |
      |                                   |                                                                                                                                                                                                                                     |
      |                                   | You can select an EIP that either is not bound to any resource, has been bound to a DNAT rule with **Port Type** set to **Specific port** of the current NAT gateway, or has been bound to an SNAT rule of the current NAT gateway. |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Outside Port                      | The port of the EIP. This parameter is available if you select **Specific port** for **Port Type**. The value ranges from 1 to 65535.                                                                                               |
      |                                   |                                                                                                                                                                                                                                     |
      |                                   | You can enter a single port number, for example, 80.                                                                                                                                                                                |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Private IP Address                | The private IP address of the server that provides services accessible from the Internet through the DNAT rule.                                                                                                                     |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Inside Port                       | The port of the server that provides services accessible from the Internet through the DNAT rule. This parameter is available if you select **Specific port** for **Port Type**. The value ranges from 1 to 65535.                  |
      |                                   |                                                                                                                                                                                                                                     |
      |                                   | You can enter a single port number, for example, 80.                                                                                                                                                                                |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
