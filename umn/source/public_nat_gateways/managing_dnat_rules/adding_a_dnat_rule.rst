:original_name: en-us_topic_0127489530.html

.. _en-us_topic_0127489530:

Adding a DNAT Rule
==================

Scenarios
---------

After a public NAT gateway is created, add DNAT rules to allow servers in your VPC to provide services accessible from the Internet.

Only one DNAT rule can be configured for each port on a server. One port can be mapped to only one EIP. If multiple servers need to provide services accessible from the Internet, create multiple DNAT rules.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image2| to expand the service list and choose **Network** > **NAT Gateway**.

   The **Public NAT Gateways** page is displayed.

#. On the displayed page, click the name of the public NAT gateway on which you need to add a DNAT rule.

#. On the public NAT gateway details page, click the **DNAT Rules** tab.

#. Click **Add DNAT Rule**.


   .. figure:: /_static/images/en-us_image_0259133802.png
      :alt: **Figure 1** Add DNAT Rule

      **Figure 1** Add DNAT Rule

#. Configure required parameters. For details, see :ref:`Table 1 <en-us_topic_0127489530__en-us_topic_0127293986_table30787259144637>`.

   .. _en-us_topic_0127489530__en-us_topic_0127293986_table30787259144637:

   .. table:: **Table 1** Descriptions of DNAT rule parameters

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                                                                  |
      +===================================+==============================================================================================================================================================================================================================================================================================================+
      | Scenario                          | Select **VPC** if your servers in a VPC will use the DNAT rule to share the same EIP to provide services accessible from the Internet.                                                                                                                                                                       |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | **Direct Connect**: Select this scenario if your on-premises servers will use the DNAT rule to provide services accessible from the Internet.                                                                                                                                                                |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Port Type                         | The port type                                                                                                                                                                                                                                                                                                |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | -  **All ports**: All requests received by the gateway through all ports over any protocol will be forwarded to the private IP address of your server.                                                                                                                                                       |
      |                                   | -  **Specific port**: Only requests received from a specified port over a specified protocol will be forwarded to the specified port on the server.                                                                                                                                                          |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Protocol                          | The protocol can be TCP or UDP.                                                                                                                                                                                                                                                                              |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | This parameter is available if you select **Specific port** for **Port Type**. If you select **All ports**, the value of this parameter is **All** by default.                                                                                                                                               |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Public IP Address Type            | The EIP that will be used by the server to provide services accessible from the Internet                                                                                                                                                                                                                     |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | You can select an EIP that either has not been bound, has been bound to a DNAT rule of the current public NAT gateway with **Port Type** set to **Specific port**, or has been bound to an SNAT rule of the current public NAT gateway.                                                                      |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Outside Port                      | The port of the EIP used by the NAT gateway for external communications                                                                                                                                                                                                                                      |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | This parameter is only available if you select **Specific port** for **Port Type**. Range: 1 to 65535                                                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | You can only enter a specific port number, for example, 80.                                                                                                                                                                                                                                                  |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Instance Type                     | The type of the instance that will be providing services accessible from the Internet. Possible values are:                                                                                                                                                                                                  |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | -  **Server**                                                                                                                                                                                                                                                                                                |
      |                                   | -  **Virtual IP address**                                                                                                                                                                                                                                                                                    |
      |                                   | -  **Custom**                                                                                                                                                                                                                                                                                                |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | NIC                               | The NIC of the server. This parameter is available if you set **Instance Type** to **Server**.                                                                                                                                                                                                               |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Private IP Address                | -  In a VPC scenario, this parameter can only be set to the private IP address of a server in the NAT gateway's VPC. The server will provide services accessible from the Internet through DNAT.                                                                                                             |
      |                                   | -  In a Direct Connect scenario, set this parameter to IP address of the server in your on-premises data center or your private IP address. This IP address is used by on-premises servers that are connected to a VPC through Direct Connect to provide services accessible from the Internet through DNAT. |
      |                                   | -  Configure the port of **Private IP Address** if you select **Specific port** for **Port Type**.                                                                                                                                                                                                           |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Inside Port                       | The port of the server over which the originating requests will be forwarded                                                                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | This parameter is only available if you select **Specific port** for **Port Type**.                                                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | Range: 1 to 65535                                                                                                                                                                                                                                                                                            |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | You can only enter a specific port number, for example, 80.                                                                                                                                                                                                                                                  |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Provides supplementary information about the DNAT rule. Enter up to 255 characters. Angle brackets (<>) are not allowed.                                                                                                                                                                                     |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   Once the rule is created, its status changes to **Running**.

.. important::

   After you add a DNAT rule, add rules to the security group associated with the servers to allow inbound or outbound traffic. Otherwise, the DNAT rule does not take effect.

.. |image1| image:: /_static/images/en-us_image_0000002118113858.png
.. |image2| image:: /_static/images/en-us_image_0000002153354089.png
