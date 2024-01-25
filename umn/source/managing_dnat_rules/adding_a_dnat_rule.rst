:original_name: en-us_topic_0127489530.html

.. _en-us_topic_0127489530:

Adding a DNAT Rule
==================

Scenarios
---------

After a NAT gateway is created, you can add DNAT rules to allow servers in your VPC to provide services accessible from the Internet.

You can configure only one DNAT rule for each port of a server. One port can be mapped to only one EIP. If multiple servers need to provide services accessible from the Internet, create multiple DNAT rules.

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

   .. important::

      Add security group rules to allow inbound or outbound traffic after you add a DNAT rule. Otherwise, the DNAT rule does not take effect.


   .. figure:: /_static/images/en-us_image_0000001576425382.png
      :alt: **Figure 1** Add DNAT Rule

      **Figure 1** Add DNAT Rule

#. Configure the parameters as prompted. For details, see :ref:`Table 1 <en-us_topic_0127489530__en-us_topic_0127293986_table30787259144637>`.

   .. _en-us_topic_0127489530__en-us_topic_0127293986_table30787259144637:

   .. table:: **Table 1** Parameter descriptions

      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                                                                      |
      +===================================+==================================================================================================================================================================================================================================================================================================================+
      | Scenario                          | **VPC**: Servers in the VPC can share an EIP to provide services accessible from the Internet through the DNAT rule.                                                                                                                                                                                             |
      |                                   |                                                                                                                                                                                                                                                                                                                  |
      |                                   | **Direct Connect**: Servers via Direct Connect or VPN can provide services accessible from the Internet through the DNAT rule.                                                                                                                                                                                   |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Port Type                         | The port type. You can select **All ports** or **Specific port**.                                                                                                                                                                                                                                                |
      |                                   |                                                                                                                                                                                                                                                                                                                  |
      |                                   | -  **All ports**: This is equivalent to assigning an EIP to a server. Any requests on the EIP will be forwarded by the NAT gateway to your server based on IP address mapping.                                                                                                                                   |
      |                                   | -  **Specific port**: The NAT gateway only forwards requests with a specific protocol and port on the EIP to the corresponding port of the target server.                                                                                                                                                        |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Protocol                          | The protocol can be TCP or UDP. This parameter is available if you select **Specific port** for **Port Type**. If you select **All ports**, the value of this parameter will be **All** by default.                                                                                                              |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | EIP                               | The EIP that will be used by the server to provide services accessible from the Internet.                                                                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                                                                                                  |
      |                                   | You can select an EIP that either is not bound to any resource, has been bound to a DNAT rule with **Port Type** set to **Specific port** of the current NAT gateway, or has been bound to an SNAT rule of the current NAT gateway.                                                                              |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Outside Port                      | The port of the EIP. This parameter is available if you select **Specific port** for **Port Type**. The value ranges from 1 to 65535.                                                                                                                                                                            |
      |                                   |                                                                                                                                                                                                                                                                                                                  |
      |                                   | You can enter a single port number, for example, 80.                                                                                                                                                                                                                                                             |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Private IP Address                | -  In a VPC scenario, set this parameter to the IP address of the server in a VPC. This IP address is used by the server to provide services accessible from the Internet through DNAT.                                                                                                                          |
      |                                   | -  In a Direct Connect scenario, set this parameter to the IP address of the server in the local data center or the user's private IP address. This IP address is used by local servers that are connected to a VPC through Direct Connect or VPN to provide services accessible from the Internet through DNAT. |
      |                                   | -  Configure the port of **Private IP Address** if you select **Specific port** for **Port Type**.                                                                                                                                                                                                               |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Instance Type                     | The type of the instance that will be providing services accessible from on-premises data centers or remote VPCs. Possible values are:                                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                                                                                                                                  |
      |                                   | -  **Server**                                                                                                                                                                                                                                                                                                    |
      |                                   | -  **Virtual IP address**                                                                                                                                                                                                                                                                                        |
      |                                   | -  **Custom**                                                                                                                                                                                                                                                                                                    |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | NIC                               | The NIC of the server. This parameter is available when you set **Instance Type** to **Server**.                                                                                                                                                                                                                 |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Inside Port                       | The port of the server that provides services accessible from the Internet through the DNAT rule. This parameter is available if you select **Specific port** for **Port Type**. The value ranges from 1 to 65535.                                                                                               |
      |                                   |                                                                                                                                                                                                                                                                                                                  |
      |                                   | You can enter a single port number, for example, 80.                                                                                                                                                                                                                                                             |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Supplementary information about the DNAT rule. Enter up to 255 characters. Angle brackets (<>) are not allowed.                                                                                                                                                                                                  |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. After the configuration is complete, click **OK**. Once the rule is created, its status changes to **Running**.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
