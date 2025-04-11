:original_name: nat_privatednat_0003.html

.. _nat_privatednat_0003:

Modifying a DNAT Rule
=====================

Scenarios
---------

After a DNAT rule is added, you can modify parameters in the DNAT rule as required.

Note that modifying an SNAT rule may interrupt your services.

Prerequisites
-------------

A DNAT rule has been added.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image2| to expand the service list and choose **Network** > **NAT Gateway**.

   The NAT Gateway console is displayed.

#. In the navigation pane on the left, choose **NAT Gateway** > **Private NAT Gateways**.

5. On the **Private NAT Gateways** page, click the name of the private NAT gateway.

6. On the private NAT gateway details page, click the **DNAT Rules** tab.

7. In the DNAT rule list, locate the row that contains the DNAT rule you want to modify and click **Modify** in the **Operation** column.

8. In the displayed dialog box, modify parameters as needed.

   On the local network, the port type, protocol, instance type, and internal port can be modified.

   On the transit network, the transit IP address, transit IP address port, and description can be modified.


   .. figure:: /_static/images/en-us_image_0000002085106904.png
      :alt: **Figure 1** Modify DNAT Rule

      **Figure 1** Modify DNAT Rule

9. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000002118113858.png
.. |image2| image:: /_static/images/en-us_image_0000002015300802.png
