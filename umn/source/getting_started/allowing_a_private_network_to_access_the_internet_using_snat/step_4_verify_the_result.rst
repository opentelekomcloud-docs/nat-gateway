:original_name: nat_qs_0005.html

.. _nat_qs_0005:

Step 4: Verify the Result
=========================

Scenarios
---------

After adding an SNAT rule, you can perform the following steps to verify the connection:

#. Verify that the SNAT rule has been added for the public NAT gateway.
#. Verify that servers that have no EIPs bound can access the Internet through the NAT gateway.

Prerequisites
-------------

An SNAT rule has been added.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the desired region and project.
#. Under **Network**, select **NAT Gateway**.
#. On the displayed page, click the name of the target NAT gateway.
#. In the SNAT rule list, you can view details about the SNAT rule. If **Status** is **Running**, the SNAT rule has been added successfully.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
