:original_name: nat_qs_0011.html

.. _nat_qs_0011:

Step 4: Test the Connection
===========================

Scenarios
---------

After adding a DNAT rule, you can perform the following steps to verify the connection:

#. Verify that the DNAT rule has been added for the public NAT gateway.
#. Check whether ECS 01 in the private network can be accessed by ECS 02 from the Internet through the NAT gateway (EIP 120.46.131.153 bound to the DNAT rule).

Prerequisites
-------------

A DNAT rule has been added.

Verifying that the DNAT Rule Has Been Added
-------------------------------------------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image2| to expand the service list and choose **Network** > **NAT Gateway**.

   The **Public NAT Gateways** page is displayed.

#. On the **Public NAT Gateways** page, click the name of the public NAT gateway.

#. In the **DNAT Rules** tab, view details of the DNAT rule and check whether the DNAT rule has been created.

   If **Status** of the DNAT rule is **Running**, the DNAT rule has been created.

   |image3|

Verifying that Servers in a VPC Can Be Accessed from the Internet Through the NAT Gateway
-----------------------------------------------------------------------------------------

#. Log in to the management console.
#. Click |image4| in the upper left corner and select the desired region and project.
#. Hover on |image5| in the upper left corner to display **Service List** and choose **Computing** > **Elastic Cloud Server**.
#. Log in to ECS 02 with an EIP bound.
#. On ECS 02, ping the EIP (120.46.131.153) to check whether ECS 01 on the private network can be accessed by ECS 02 on the public network through the NAT gateway.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
.. |image2| image:: /_static/images/en-us_image_0000002021410433.png
.. |image3| image:: /_static/images/en-us_image_0000002116860101.png
.. |image4| image:: /_static/images/en-us_image_0141273034.png
.. |image5| image:: /_static/images/en-us_image_0000001223839393.png
