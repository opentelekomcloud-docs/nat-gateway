:original_name: nat_qs_0017.html

.. _nat_qs_0017:

Step 4: Add an SNAT Rule
========================

Scenarios
---------

After a public NAT gateway is created, add SNAT rules for it. With SNAT rules, servers that are connected to a VPC using Direct Connect can access the Internet by sharing an EIP.

Each SNAT rule is configured for only one CIDR block. If servers that are connected to a VPC using Direct Connect are in multiple CIDR blocks, you can create multiple SNAT rules to allow the servers to share EIPs.

Prerequisites
-------------

A public NAT gateway is available.

Procedure
---------

#. Log in to the management console.

2. Click |image1| in the upper left corner and select the desired region and project.

3. In the upper left corner of the page, click |image2| to expand the service list and choose **Network** > **NAT Gateway**.

   The **Public NAT Gateways** page is displayed.

4. On the displayed page, click the name of the public NAT gateway on which you need to add an SNAT rule.

5. On the **SNAT Rules** tab, click **Add SNAT Rule**.


   .. figure:: /_static/images/en-us_image_0259133792.png
      :alt: **Figure 1** Add SNAT Rule

      **Figure 1** Add SNAT Rule

6. Configure required parameters. For details, see :ref:`Table 1 <nat_qs_0017__table4272024117597>`.

   .. _nat_qs_0017__table4272024117597:

   .. table:: **Table 1** Descriptions of SNAT rule parameters

      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                             |
      +===================================+=========================================================================================================================================================================================================================================+
      | Scenario                          | Select **Direct Connect** if your on-premises servers need to access the Internet.                                                                                                                                                      |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | CIDR Block                        | The CIDR block of the servers in the on-premises data center                                                                                                                                                                            |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Public IP Address Type            | The EIP used for accessing the Internet                                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | You can select an EIP that either has not been bound, has been bound to a DNAT rule of the current public NAT gateway with **Port Type** set to **Specific port**, or has been bound to an SNAT rule of the current public NAT gateway. |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Provides supplementary information about the SNAT rule. Enter up to 255 characters. Angle brackets (<>) are not allowed.                                                                                                                |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

7. Click **OK**.

8. View details in the SNAT rule list.

   If **Status** of the SNAT rule is **Running**, the SNAT rule has been created.

   .. note::

      -  You can add multiple SNAT rules for a public NAT gateway to suite your service requirements.
      -  Only one SNAT rule can be added for each VPC subnet.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
.. |image2| image:: /_static/images/en-us_image_0000002021410433.png
