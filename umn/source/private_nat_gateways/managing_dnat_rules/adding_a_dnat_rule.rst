:original_name: nat_privatednat_0001.html

.. _nat_privatednat_0001:

Adding a DNAT Rule
==================

Scenarios
---------

After a private NAT gateway is created, you can add DNAT rules to allow servers in your VPC to provide services accessible from on-premises servers or other VPCs.

A DNAT rule needs to be configured for each port on a server that needs to be made accessible. If multiple ports on a server or multiple servers need to provide services accessible from on-premises servers or other VPCs, multiple DNAT rules need to be configured.

Notes and Constraints
---------------------

A DNAT rule with **Port Type** set to **All ports** cannot share a transit IP address with a DNAT rule with **Port Type** set to **Specific port**.

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

5. On the **Private NAT Gateways** page, click the name of the private NAT gateway on which you need to add a DNAT rule.

6. On the private NAT gateway details page, click the **DNAT Rules** tab.

7. Click **Add DNAT Rule**.

   .. important::

      After you add a DNAT rule, add rules to the security group associated with the servers to allow inbound or outbound traffic. Otherwise, the DNAT rule does not take effect.

8. Configure required parameters. For details, see :ref:`Table 1 <nat_privatednat_0001__table149569172358>`.


   .. figure:: /_static/images/en-us_image_0000001606771726.png
      :alt: **Figure 1** Add DNAT Rule

      **Figure 1** Add DNAT Rule

   .. _nat_privatednat_0001__table149569172358:

   .. table:: **Table 1** Descriptions of DNAT rule parameters

      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                     |
      +===================================+=================================================================================================================================================================================================================================================================+
      | **Local Network**                 |                                                                                                                                                                                                                                                                 |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Port Type                         | The port type                                                                                                                                                                                                                                                   |
      |                                   |                                                                                                                                                                                                                                                                 |
      |                                   | The type can be:                                                                                                                                                                                                                                                |
      |                                   |                                                                                                                                                                                                                                                                 |
      |                                   | -  **Specific port**: The private NAT gateway only forwards requests with a specific protocol and port on the transit IP address to the corresponding port of the target server.                                                                                |
      |                                   | -  **All ports**: All requests received by the gateway through all ports over any protocol will be forwarded to the private IP address of your server.                                                                                                          |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Protocol                          | The protocol can be TCP or UDP                                                                                                                                                                                                                                  |
      |                                   |                                                                                                                                                                                                                                                                 |
      |                                   | If you select **All ports**, the value of this parameter is **All** by default.                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                                                                 |
      |                                   | This parameter is only available if you select **Specific port** for **Port Type**.                                                                                                                                                                             |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Instance Type                     | The type of instance that will provide services accessible from on-premises data centers or other VPCs                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                                                 |
      |                                   | Possible types are:                                                                                                                                                                                                                                             |
      |                                   |                                                                                                                                                                                                                                                                 |
      |                                   | -  **Server**                                                                                                                                                                                                                                                   |
      |                                   | -  **Virtual IP address**                                                                                                                                                                                                                                       |
      |                                   | -  **Load balancer**                                                                                                                                                                                                                                            |
      |                                   | -  **Custom**                                                                                                                                                                                                                                                   |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | NIC                               | The NIC of the server                                                                                                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                                                                                 |
      |                                   | This parameter is only available if you set **Instance Type** to **Server**.                                                                                                                                                                                    |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | IP Address                        | The IP address of the server that will provide services accessible from on-premises data centers or other VPCs. This parameter is only available if you set **Instance Type** to **Custom**.                                                                    |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Internal Port                     | The port of the instance                                                                                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                                                 |
      |                                   | Range: 1 to 65535                                                                                                                                                                                                                                               |
      |                                   |                                                                                                                                                                                                                                                                 |
      |                                   | This parameter is only available if you select **Specific port** for **Port Type**.                                                                                                                                                                             |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | **Transit Network**               |                                                                                                                                                                                                                                                                 |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Transit IP Address                | The transit IP address used to access on-premises data centers or other VPCs                                                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                                                 |
      |                                   | You can select a transit IP address that is not bound to any resource, has been bound to a DNAT rule for the current private NAT gateway where **Port Type** is set to **Specific port**, or has been bound to an SNAT rule of the current private NAT gateway. |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Transit IP Address Port           | The port of the transit IP address Supported range: 1 to 65535                                                                                                                                                                                                  |
      |                                   |                                                                                                                                                                                                                                                                 |
      |                                   | This parameter is only available if you select **Specific port** for **Port Type**.                                                                                                                                                                             |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Supplementary information about the DNAT rule. Enter up to 255 characters. Angle brackets (<>) are not allowed.                                                                                                                                                 |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

9. Click **OK**.

   Once the rule is created, its status changes to **Running**.

Helpful Links
-------------

:ref:`Managing DNAT Rules <nat_privatednat_0000>`

.. |image1| image:: /_static/images/en-us_image_0000002118113858.png
.. |image2| image:: /_static/images/en-us_image_0000002015300802.png
