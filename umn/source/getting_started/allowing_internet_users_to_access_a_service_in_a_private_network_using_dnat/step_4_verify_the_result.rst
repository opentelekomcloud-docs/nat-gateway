:original_name: nat_qs_0011.html

.. _nat_qs_0011:

Step 4: Verify the Result
=========================

Scenarios
---------

After adding a DNAT rule, you can perform the following steps to verify the connection:

#. Verify that the DNAT rule has been added for the public NAT gateway.
#. Check whether ECS 01 in the private network can be accessed by ECS 02 from the Internet through the NAT gateway (EIP 120.46.131.153 bound to the DNAT rule).

Prerequisites
-------------

A DNAT rule has been added.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the desired region and project.
#. Under **Network**, select **NAT Gateway**.
#. On the displayed page, click the name of the target NAT gateway.
#. In the DNAT rule list, you can view details about the DNAT rule. If **Status** is **Running**, the DNAT rule has been added successfully.

Verifying that Servers in a VPC Can Be Accessed from the Internet Through the NAT Gateway
-----------------------------------------------------------------------------------------

#. Log in to the management console.
#. Click |image2| in the upper left corner and select the desired region and project.
#. Hover on |image3| in the upper left corner to display **Service List** and choose **Computing** > **Elastic Cloud Server**.
#. Log in to ECS 02 with an EIP bound.
#. On ECS 02, ping the EIP (120.46.131.153) to check whether ECS 01 on the private network can be accessed by ECS 02 on the public network through the NAT gateway.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
.. |image2| image:: /_static/images/en-us_image_0141273034.png
.. |image3| image:: /_static/images/en-us_image_0000001223839393.png
