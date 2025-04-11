:original_name: en-us_topic_0127489529.html

.. _en-us_topic_0127489529:

Adding an SNAT Rule
===================

Scenarios
---------

After a public NAT gateway is created, add an SNAT rule, so that servers in a VPC subnet or servers that are connected to a VPC through Direct Connect can access the Internet by sharing an EIP.

One SNAT rule takes effect for only one subnet. If there are multiple subnets in a VPC, create multiple SNAT rules to allow servers in them to share EIPs.

Notes and Constraints
---------------------

-  Only one SNAT rule can be added for each VPC subnet.
-  If an SNAT rule is used in the Direct Connect scenario, the custom CIDR block must be a CIDR block of a Direct Connect connection and cannot overlap with the NAT gateway's VPC subnets.
-  There is no limit on the number of SNAT rules that can be added on a public NAT gateway.


Adding an SNAT Rule
-------------------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image2| to expand the service list and choose **Network** > **NAT Gateway**.

   The **Public NAT Gateways** page is displayed.

#. On the displayed page, click the name of the public NAT gateway on which you need to add an SNAT rule.

#. On the **SNAT Rules** tab, click **Add SNAT Rule**.


   .. figure:: /_static/images/en-us_image_0000002116327929.png
      :alt: **Figure 1** Add SNAT Rule

      **Figure 1** Add SNAT Rule

#. Configure required parameters. For details, see :ref:`Table 1 <en-us_topic_0127489529__en-us_topic_0127293981_table4272024117597>`.

   .. _en-us_topic_0127489529__en-us_topic_0127293981_table4272024117597:

   .. table:: **Table 1** Descriptions of SNAT rule parameters

      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                             |
      +===================================+=========================================================================================================================================================================================================================================+
      | Scenario                          | The scenarios where the SNAT rule is used                                                                                                                                                                                               |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | Select **VPC** if your servers in a VPC need to access the Internet.                                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | Select **Direct Connect** if servers in your on-premises data center need to access the Internet.                                                                                                                                       |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | CIDR Block                        | In a VPC scenario, specify a VPC subnet to enable servers in that subnet to access the Internet using the SNAT rule.                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                         |
      |                                   | In a Direct Connect scenario, specify a CIDR block of your data center to enable your servers to access the Internet using the SNAT rule.                                                                                               |
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

.. |image1| image:: /_static/images/en-us_image_0000002118113858.png
.. |image2| image:: /_static/images/en-us_image_0000002153354089.png
