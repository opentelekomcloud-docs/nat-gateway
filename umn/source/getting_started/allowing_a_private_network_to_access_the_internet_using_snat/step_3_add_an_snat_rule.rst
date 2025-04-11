:original_name: nat_qs_0004.html

.. _nat_qs_0004:

Step 3: Add an SNAT Rule
========================

Scenarios
---------

After creating a public NAT gateway, add an SNAT rule to enable your servers in a specific subnet to access the Internet through the same EIP.

One SNAT rule can be configured for only one subnet or CIDR block. If there are multiple subnets or CIDR blocks in a VPC, you can add multiple SNAT rules to allow servers to share EIPs.

Prerequisites
-------------

A public NAT gateway is available.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image2| to expand the service list and choose **Network** > **NAT Gateway**.

   The **Public NAT Gateways** page is displayed.

#. On the displayed page, click the name of the public NAT gateway on which you need to add an SNAT rule.

#. On the **SNAT Rules** tab, click **Add SNAT Rule**.


   .. figure:: /_static/images/en-us_image_0000002116327929.png
      :alt: **Figure 1** Add SNAT Rule

      **Figure 1** Add SNAT Rule

#. Configure required parameters. :ref:`Table 1 <nat_qs_0004__table1966804261617>` describes the parameters.

   .. _nat_qs_0004__table1966804261617:

   .. table:: **Table 1** Descriptions of SNAT rule parameters

      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                             |
      +===================================+=========================================================================================================================================================================================================================================+
      | Scenario                          | Select **VPC** if your servers in a VPC will use the SNAT rule to access the Internet.                                                                                                                                                  |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | CIDR Block                        | The CIDR block is a subset of the NAT gateway's VPC subnets                                                                                                                                                                             |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | Servers whose IP addresses in the CIDR block can use the SNAT rule to access the Internet.                                                                                                                                              |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Public IP Address Type            | The EIP used for accessing the Internet                                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | You can select an EIP that either has not been bound, has been bound to a DNAT rule of the current public NAT gateway with **Port Type** set to **Specific port**, or has been bound to an SNAT rule of the current public NAT gateway. |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Provides supplementary information about the SNAT rule. Enter up to 255 characters. Angle brackets (<>) are not allowed.                                                                                                                |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   .. note::

      -  You can add multiple SNAT rules for a public NAT gateway to suite your service requirements.
      -  Only one SNAT rule can be added for each VPC subnet.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
.. |image2| image:: /_static/images/en-us_image_0000002021410433.png
