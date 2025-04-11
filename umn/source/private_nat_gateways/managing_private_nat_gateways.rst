:original_name: nat_privatenat_0003.html

.. _nat_privatenat_0003:

Managing Private NAT Gateways
=============================

After a private NAT gateway is created, you can manage it in a unified manner, including modifying and deleting the private NAT gateway.

Modifying a Private NAT Gateway
-------------------------------

Modify the name, specifications, or description of a private NAT gateway.

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image2| to expand the service list and choose **Network** > **NAT Gateway**.

   The NAT Gateway console is displayed.

#. In the navigation pane on the left, choose **NAT Gateway** > **Private NAT Gateways**.

5. On the displayed page, locate the row that contains the private NAT gateway you want to modify and click **Modify** in the **Operation** column.

6. Modify the name, specifications, or description of the private NAT gateway.


   .. figure:: /_static/images/en-us_image_0000002214223497.png
      :alt: **Figure 1** Modifying a private NAT gateway

      **Figure 1** Modifying a private NAT gateway

7. Click **Next**.

8. Confirm the modification and click **Submit**.

Viewing a Private NAT Gateway
-----------------------------

#. Log in to the management console.

#. Click |image3| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image4| to expand the service list and choose **Network** > **NAT Gateway**.

   The **Public NAT Gateways** page is displayed.

#. In the navigation pane on the left, choose **NAT Gateway** > **Private NAT Gateways**.

#. Click the name of the private NAT gateway.

#. On the displayed page, view details of the private NAT gateway.


   .. figure:: /_static/images/en-us_image_0000002186808916.png
      :alt: **Figure 2** Details about a private NAT gateway

      **Figure 2** Details about a private NAT gateway

Deleting a Private NAT Gateway
------------------------------

Delete private NAT gateways that are no longer required to release resources and reduce costs.

.. note::

   All SNAT and DNAT rules created on the private NAT gateway have been deleted. For details about how to delete SNAT and DNAT rules, see :ref:`Deleting an SNAT Rule <nat_privatesnat_0004>` and :ref:`Deleting a DNAT Rule <nat_privatednat_0004>`.

#. Log in to the management console.

#. Click |image5| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image6| to expand the service list and choose **Network** > **NAT Gateway**.

   The NAT Gateway console is displayed.

#. In the navigation pane on the left, choose **NAT Gateway** > **Private NAT Gateways**.

5. On the **Private NAT Gateways** page, locate the private NAT gateway that you want to delete and click **Delete** in the **Operation** column.
6. In the displayed dialog box, enter **DELETE**.
7. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000002118113858.png
.. |image2| image:: /_static/images/en-us_image_0000002015300802.png
.. |image3| image:: /_static/images/en-us_image_0000002118113858.png
.. |image4| image:: /_static/images/en-us_image_0000002153354089.png
.. |image5| image:: /_static/images/en-us_image_0000002118113858.png
.. |image6| image:: /_static/images/en-us_image_0000002015300802.png
