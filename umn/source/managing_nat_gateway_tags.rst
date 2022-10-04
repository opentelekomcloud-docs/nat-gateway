:original_name: nat_tag_0000.html

.. _nat_tag_0000:

Managing NAT Gateway Tags
=========================

Application Scenarios
---------------------

A NAT gateway tag identifies the NAT gateway. Tags can be added to NAT gateways to facilitate NAT gateway identification and administration. You can add a tag to a NAT gateway when creating the NAT gateway. Alternatively, you can add a tag to a created NAT gateway on the NAT gateway details page. A maximum of 20 tags can be added to each NAT gateway.

A tag consists of a key and value pair. :ref:`Table 1 <nat_tag_0000__ted9687ca14074ef785241145365a6175>` lists the tag key and value requirements.

.. _nat_tag_0000__ted9687ca14074ef785241145365a6175:

.. table:: **Table 1** Tag requirements

   +-----------------------------------+---------------------------------------------------------------------+
   | Parameter                         | Requirement                                                         |
   +===================================+=====================================================================+
   | Key                               | -  Cannot be left blank.                                            |
   |                                   | -  Must be unique for each NAT gateway.                             |
   |                                   | -  Contains a maximum of 36 characters.                             |
   |                                   | -  Can contain only the following character types:                  |
   |                                   |                                                                     |
   |                                   |    -  Letter                                                        |
   |                                   |    -  Digits                                                        |
   |                                   |    -  Special characters, including hyphens (-) and underscores (_) |
   +-----------------------------------+---------------------------------------------------------------------+
   | Value                             | -  Can contain a maximum of 43 characters.                          |
   |                                   | -  Can contain only the following character types:                  |
   |                                   |                                                                     |
   |                                   |    -  Letter                                                        |
   |                                   |    -  Digits                                                        |
   |                                   |    -  Special characters, including hyphens (-) and underscores (_) |
   +-----------------------------------+---------------------------------------------------------------------+

Procedure
---------

**Search for NAT gateways by tag key and value on the page showing the NAT gateway List.**

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Under **Network**, click **NAT Gateway**.

#. In the upper right corner of the NAT gateway list, click **Search by Tag**.

#. In the displayed area, enter the tag key and value of the NAT gateway you are looking for. Both the tag key and value must be specified.

#. Click **+** to specify additional tag keys and values.

   You can add a maximum of ten tags to refine your search results. If you add more than one tag to search for NAT gateways, the tags are automatically joined with AND.

#. Click **Search**.

   The system displays the NAT gateways you are looking for based on the entered tag keys and values.

**Add, delete, edit, and view tags on the Tags tab of a NAT gateway.**

#. Log in to the management console.
#. Click |image2| in the upper left corner and select the desired region and project.
#. Under **Network**, click **NAT Gateway**.
#. On the displayed page, locate the NAT gateway whose tags are to be managed and click the NAT gateway name. The page showing details about the NAT gateway is displayed.

5. Click the **Tags** tab and perform desired operations on tags.

   -  View a tag.

      On the **Tags** tab, you can view details about tags added to the current VPC, including the number of tags and the key and value of each tag.

   -  Add a tag.

      Click **Add Tag** in the upper left corner. In the displayed dialog box, enter the key and value of the tag to be added, and click **OK**.

      .. note::

         You can use the predefined tags as prompted to simplify tag adding operations. For details, see the *Tag Management Service User Guide*.

   -  Modify a tag.

      Locate the row that contains the tag to be edited and click **Edit** in the **Operation** column. In the **Edit Tag** dialog box, change the tag value and click **OK**.

   -  Delete a tag.

      Locate the row that contains the tag to be deleted and click **Delete** in the **Operation** column. In the displayed **Delete Tag** dialog box, click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
.. |image2| image:: /_static/images/en-us_image_0141273034.png
