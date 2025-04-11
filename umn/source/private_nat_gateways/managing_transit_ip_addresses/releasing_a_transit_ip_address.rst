:original_name: nat_exip_0003.html

.. _nat_exip_0003:

Releasing a Transit IP Address
==============================

Scenarios
---------

You can release a transit IP address that is no longer needed.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image2| to expand the service list and choose **Network** > **NAT Gateway**.

   The NAT Gateway console is displayed.

#. In the navigation pane on the left, choose **NAT Gateway** > **Private NAT Gateways**.

#. In the **Transit IP Addresses** tab, locate the transit IP address you want to release and click **Release** in the **Operation** column.

#. Click **OK**.

   .. note::

      If a transit IP address has been associated with an SNAT or DNAT rule, it cannot be released. To release such a transit IP address, delete all rules associated with it first.

.. |image1| image:: /_static/images/en-us_image_0000002118113858.png
.. |image2| image:: /_static/images/en-us_image_0000002015300802.png
