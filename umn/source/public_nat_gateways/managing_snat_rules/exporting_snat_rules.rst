:original_name: nat_snat_0004.html

.. _nat_snat_0004:

Exporting SNAT Rules
====================

Scenarios
---------

After a public NAT gateway is created, add an SNAT rule, so that servers in a VPC subnet or servers that are connected to a VPC through Direct Connect can access the Internet by sharing an EIP.

When adding SNAT rules in different environments or migrating SNAT rules between NAT gateways, you can export SNAT rules to simplify and accelerate the SNAT rule configuration.


Exporting SNAT Rules
--------------------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image2| to expand the service list and choose **Network** > **NAT Gateway**.

   The **Public NAT Gateways** page is displayed.

#. On the displayed page, click the name of the public NAT gateway from which you want to export SNAT rules.

#. On the public NAT gateway details page, click the **SNAT Rules** tab.

#. In the SNAT rule list, select the rules to be exported and click **Export**.

   The exported parameters contain the ID, status, application scenario, CIDR block, EIP, description, and time when a rule was added.

   a. **Export all data to an XLSX file**: The system automatically exports the basic information of all the SNAT rules in the current region as an Excel file to a local directory.
   b. **Export selected data to an XLSX file**: The system automatically exports the basic information of the selected SNAT rules in the current region as an Excel file to a local directory.

.. |image1| image:: /_static/images/en-us_image_0000002118113858.png
.. |image2| image:: /_static/images/en-us_image_0000002153354089.png
