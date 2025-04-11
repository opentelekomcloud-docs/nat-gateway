:original_name: nat_tag_0000.html

.. _nat_tag_0000:

Tag Management
==============

Scenarios
---------

A NAT gateway tag identifies the NAT gateway. Tags can be added to NAT gateways to ease NAT gateway identification and administration. You can add a tag to a NAT gateway when creating the NAT gateway. Alternatively, you can add a tag to a created NAT gateway on the NAT gateway details page. A maximum of 20 tags can be added to each NAT gateway.

A tag consists of a key and value pair. :ref:`Table 1 <nat_tag_0000__ted9687ca14074ef785241145365a6175>` lists the tag key and value requirements.

.. _nat_tag_0000__ted9687ca14074ef785241145365a6175:

.. table:: **Table 1** Tag requirements

   +-----------------------------------+-----------------------------------------------------------------------------------+
   | Parameter                         | Requirement                                                                       |
   +===================================+===================================================================================+
   | Key                               | -  Cannot be left blank.                                                          |
   |                                   | -  Must be unique for each NAT gateway.                                           |
   |                                   | -  Can contain a maximum of 36 characters.                                        |
   |                                   | -  Contains only letters, digits, hyphens (-), underscores (_), and at signs (@). |
   +-----------------------------------+-----------------------------------------------------------------------------------+
   | Value                             | -  Can contain a maximum of 43 characters.                                        |
   |                                   | -  Contains only letters, digits, hyphens (-), underscores (_), and at signs (@). |
   +-----------------------------------+-----------------------------------------------------------------------------------+

Managing NAT Gateway Tags
-------------------------

You can manage tags for NAT gateways in either of the following ways:

-  Add tags when you create a NAT gateway.

   For detailed operations, see :ref:`Creating a Public NAT Gateway <en-us_topic_0150270259>` and :ref:`Creating a Private NAT Gateway <nat_privatenat_0002>`.

-  Modify tags for an existing NAT gateway.

   #. Log in to the management console.
   #. In the upper left corner of the page, click |image1| and select the desired region and project.
   #. Click |image2| in the upper left corner of the page and choose **Network** > **NAT Gateway**.
   #. In the public or private NAT gateway list, click the target NAT gateway.
   #. Under **Tags**, click **Edit Tag**.
   #. The **Edit Tag** dialog box is displayed.

      a. Adding a tag: On the **Edit Tag** page, click **Add Tag** and enter a tag key and tag value.
      b. Modifying a tag: On the **Edit Tag** page, locate the target tag and enter a new value.

   #. Click **OK**.

      .. note::

         -  A maximum of 20 tags can be added to a NAT gateway.
         -  Each tag is a key-value pair, and the tag key is unique.

Managing Transit IP Address Tags
--------------------------------

You can manage tags for transit IP addresses in either of the following ways:

-  Add tags when you assign a transit IP address.

   For details, see :ref:`Assigning a Transit IP Address <nat_privatenatexsub_0001>`.

-  Modify tags for an existing transit IP address.

   #. Log in to the management console.
   #. In the upper left corner of the page, click |image3| and select the desired region and project.
   #. Click |image4| in the upper left corner of the page and choose **Network** > **NAT Gateway**.
   #. In the transit IP address list of the private NAT gateway, click the target transit IP address.
   #. Click **Edit Tag**.
   #. The **Edit Tag** dialog box is displayed.

      a. Adding a tag: On the **Edit Tag** page, click **Add Tag** and enter a tag key and tag value.
      b. Modifying a tag: On the **Edit Tag** page, locate the target tag and enter a new value.

   #. Click **OK**.

      .. note::

         -  A maximum of 20 tags can be added to a transit IP address.
         -  Each tag is a key-value pair, and the tag key is unique.

.. |image1| image:: /_static/images/en-us_image_0000002115024552.png
.. |image2| image:: /_static/images/en-us_image_0000002115184308.png
.. |image3| image:: /_static/images/en-us_image_0000002122932018.png
.. |image4| image:: /_static/images/en-us_image_0000002158213649.png
