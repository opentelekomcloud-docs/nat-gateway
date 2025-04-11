:original_name: nat_dnat_0005.html

.. _nat_dnat_0005:

Importing DNAT Rules by Using a Template and Exporting DNAT Rules
=================================================================

Scenarios
---------

When adding DNAT rules in different environments or migrating DNAT rules between NAT gateways, you can import and export DNAT rules to simplify and accelerate the DNAT rule configuration.

Importing DNAT Rules
--------------------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image2| to expand the service list and choose **Network** > **NAT Gateway**.

   The **Public NAT Gateways** page is displayed.

#. On the displayed page, click the name of the public NAT gateway to which you want to import DNAT rules.

#. On the public NAT gateway details page, click the **DNAT Rules** tab.

#. On the displayed page, click **Import**. In the displayed **Import Rule** dialog box, click **Download Template**.

#. Fill in DNAT rule parameters based on the table heading in the template. For details, see :ref:`Table 1 <nat_dnat_0005__en-us_topic_0127293986_table30787259144637>`.

   .. _nat_dnat_0005__en-us_topic_0127293986_table30787259144637:

   .. table:: **Table 1** Descriptions of DNAT rule parameters

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                                                                  |
      +===================================+==============================================================================================================================================================================================================================================================================================================+
      | Scenario                          | The following two scenarios are available:                                                                                                                                                                                                                                                                   |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | -  **VPC**: The servers in a VPC will share an EIP to provide services accessible from the Internet through the DNAT rule.                                                                                                                                                                                   |
      |                                   | -  **Direct Connect**: Select this scenario if your on-premises servers will use the DNAT rule to provide services accessible from the Internet.                                                                                                                                                             |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Protocol                          | The value can be **TCP**, **UDP**, or **All**.                                                                                                                                                                                                                                                               |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | EIP                               | The EIP that will be used by the server to provide publicly accessible services                                                                                                                                                                                                                              |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | Only EIPs that have not been bound or that have been bound to a DNAT rule in the current VPC are available for selection.                                                                                                                                                                                    |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Outside Port                      | The EIP port                                                                                                                                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | This parameter is only available if **Specific port** is selected for **Port Type**.                                                                                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | You can enter a specific port number or a port range, for example, 80 or 80-100.                                                                                                                                                                                                                             |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Private IP Address                | -  In a VPC scenario, set this parameter to the private IP address of a server in the NAT gateway's VPC. The server will provide services accessible from the Internet through DNAT.                                                                                                                         |
      |                                   | -  In a Direct Connect scenario, set this parameter to IP address of the server in your on-premises data center or your private IP address. This IP address is used by on-premises servers that are connected to a VPC through Direct Connect to provide services accessible from the Internet through DNAT. |
      |                                   | -  Configure the private IP address port if **Protocol** is set to **TCP** or **UDP**.                                                                                                                                                                                                                       |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Inside Port                       | -  In a VPC scenario, set this parameter to the port of the server in a VPC.                                                                                                                                                                                                                                 |
      |                                   | -  In a Direct Connect scenario, set this parameter to the port of the server in the on-premises data center or the user's private port.                                                                                                                                                                     |
      |                                   | -  This parameter is only available if **Specific port** is selected for **Port Type**.                                                                                                                                                                                                                      |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | The number of private and public ports must match.                                                                                                                                                                                                                                                           |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Supplementary information about the DNAT rule. Enter up to 255 characters. Angle brackets (<>) are not allowed.                                                                                                                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. After filling in the template, click **Select File**, select the local template, and click **Import**.

#. View the imported DNAT rules.

   If their **Status** is **Running**, the DNAT rules have been added.

Exporting DNAT Rules
--------------------

#. Log in to the management console.

#. Click |image3| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image4| to expand the service list and choose **Network** > **NAT Gateway**.

   The **Public NAT Gateways** page is displayed.

#. On the displayed page, click the name of the public NAT gateway from which you want to export DNAT rules.

#. On the public NAT gateway details page, click the **DNAT Rules** tab.

#. In the DNAT rule list, select the rules to be exported and click **Export**.

   The exported parameters include ID, status, application scenario (VPC/Direct Connect), EIP, outside port, private IP address, inside port, protocol (TCP, UDP, or all), description, and time when a rule was added.

   a. **Export all data to an XLSX file**: The system automatically exports the basic information of all the DNAT rules in the current region as an Excel file to a local directory.
   b. **Export selected data to an XLSX file**: The system automatically exports the basic information of the selected DNAT rules in the current region as an Excel file to a local directory.

.. |image1| image:: /_static/images/en-us_image_0000002118113858.png
.. |image2| image:: /_static/images/en-us_image_0000002153354089.png
.. |image3| image:: /_static/images/en-us_image_0000002118113858.png
.. |image4| image:: /_static/images/en-us_image_0000002153354089.png
