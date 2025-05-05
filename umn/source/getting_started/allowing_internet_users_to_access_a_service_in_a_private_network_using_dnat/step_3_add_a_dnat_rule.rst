:original_name: nat_qs_0010.html

.. _nat_qs_0010:

Step 3: Add a DNAT Rule
=======================

Scenarios
---------

After a public NAT gateway is created, add DNAT rules to allow servers in your VPC to provide services accessible from the Internet.

You can configure a DNAT rule for each port on a server. If multiple servers need to provide services accessible from the Internet, create multiple DNAT rules.

Prerequisites
-------------

A public NAT gateway is available.

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

#. Configure required parameters. For details, see :ref:`Table 1 <nat_qs_0010__table30787259144637>`.

   .. _nat_qs_0010__table30787259144637:

   .. table:: **Table 1** Descriptions of DNAT rule parameters

      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                             |
      +===================================+=========================================================================================================================================================================================================================================+
      | Scenario                          | Select **VPC** if your servers in a VPC need to share an EIP to provide services accessible from the Internet.                                                                                                                          |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Port Type                         | The port type                                                                                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | -  **All ports**: All requests received by the gateway through all ports over any protocol will be forwarded to the private IP address of your server.                                                                                  |
      |                                   | -  **Specific port**: Only requests received from a specified port over a specified protocol will be forwarded to the specified port on the server.                                                                                     |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Protocol                          | The protocol can be TCP or UDP.                                                                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | This parameter is available if you select **Specific port** for **Port Type**. If you select **All ports**, the value of this parameter is **All** by default.                                                                          |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Public IP Address Type            | The EIP of the public NAT gateway                                                                                                                                                                                                       |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | You can select an EIP that either has not been bound, has been bound to a DNAT rule of the current public NAT gateway with **Port Type** set to **Specific port**, or has been bound to an SNAT rule of the current public NAT gateway. |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Public Port                       | The port of the EIP used by the NAT gateway for external communications                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | This parameter is only available if you select **Specific port** for **Port Type**.                                                                                                                                                     |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | Range: 1 to 65535                                                                                                                                                                                                                       |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | You can only enter a specific port number, for example, 80.                                                                                                                                                                             |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Instance Type                     | The type of the instance that will be providing services accessible from the Internet. Possible values are:                                                                                                                             |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | -  **Server**                                                                                                                                                                                                                           |
      |                                   | -  **Virtual IP address**                                                                                                                                                                                                               |
      |                                   | -  **Custom**                                                                                                                                                                                                                           |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Private IP Address                | The IP address of the server in the NAT gateway's VPC and processes matching packets where requests will be forwarded to                                                                                                                |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | Configure the port of **Private IP Address** if you select **Specific port** for **Port Type**.                                                                                                                                         |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | NIC                               | The NIC of the server. This parameter is available if you set **Instance Type** to **Server**.                                                                                                                                          |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Private Port                      | The port of the server over which the originating requests will be forwarded                                                                                                                                                            |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | This parameter is only available if you select **Specific port** for **Port Type**.                                                                                                                                                     |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | Range: 1 to 65535                                                                                                                                                                                                                       |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | You can only enter a specific port number, for example, 80.                                                                                                                                                                             |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Provides supplementary information about the DNAT rule. Enter up to 255 characters. Angle brackets (<>) are not allowed.                                                                                                                |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

.. important::

   After you add a DNAT rule, add rules to the security group associated with the servers to allow inbound or outbound traffic. Otherwise, the DNAT rule does not take effect.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
.. |image2| image:: /_static/images/en-us_image_0000002021410433.png
