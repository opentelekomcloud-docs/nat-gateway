:original_name: nat_privatesnat_0001.html

.. _nat_privatesnat_0001:

Adding an SNAT Rule
===================

Scenarios
---------

After the private NAT gateway is created, add an SNAT rule so that some or all servers in a VPC subnet can share a transit IP address to access on-premises data centers or other VPCs.

Notes and Constraints
---------------------

Only one SNAT rule can be added for each VPC subnet.

Prerequisites
-------------

-  A private NAT gateway is available.
-  A transit IP address is available.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image2| to expand the service list and choose **Network** > **NAT Gateway**.

   The NAT Gateway console is displayed.

#. In the navigation pane on the left, choose **NAT Gateway** > **Private NAT Gateways**.

5. On the **Private NAT Gateways** page, click the name of the private NAT gateway on which you need to add an SNAT rule.

6. On the **SNAT Rules** tab, click **Add SNAT Rule**.

7. Configure required parameters. For details, see :ref:`Table 1 <nat_privatesnat_0001__table18428181261513>`.


   .. figure:: /_static/images/en-us_image_0000002117766493.png
      :alt: **Figure 1** Add SNAT Rule

      **Figure 1** Add SNAT Rule

   .. _nat_privatesnat_0001__table18428181261513:

   .. table:: **Table 1** Parameter descriptions of an SNAT rule

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                              |
      +===================================+==========================================================================================================================+
      | Subnet                            | The subnet type of the SNAT rule. Select **Existing** or **Custom**.                                                     |
      |                                   |                                                                                                                          |
      |                                   | Select a subnet where IP address translation is required in the service VPC.                                             |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Monitoring                        | You can create alarm rules using Cloud Eye after your SNAT connection has been created.                                  |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Transit IP Address                | Select the created transit IP address.                                                                                   |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Provides supplementary information about the SNAT rule. Enter up to 255 characters. Angle brackets (<>) are not allowed. |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+

8. Click **OK**.

   .. note::

      You can add multiple SNAT rules for a private NAT gateway to suite your service requirements.

Helpful Links
-------------

:ref:`Managing SNAT Rules <nat_privatesnat_0000>`

.. |image1| image:: /_static/images/en-us_image_0000002118113858.png
.. |image2| image:: /_static/images/en-us_image_0000002015300802.png
