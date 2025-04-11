:original_name: nat_qs_0027.html

.. _nat_qs_0027:

Step 5: Add a Route
===================

Scenarios
---------

After the private NAT gateway is configured, add a route in the route table of the service VPC to point to the private NAT gateway.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the desired region and project.
#. Click **Service List** in the upper left corner. Under **Network**, select **Virtual Private Cloud**.
#. In the navigation pane on the left, choose **Route Tables**.
#. In the route table list, click the name of the route table associated the service VPC.
#. Click **Add Route** and configure required parameters.

   .. table:: **Table 1** Parameter descriptions

      +-----------------------------------+------------------------------------------------------------------+
      | Parameter                         | Description                                                      |
      +===================================+==================================================================+
      | Destination                       | The destination CIDR block                                       |
      |                                   |                                                                  |
      |                                   | Set it to the CIDR block used by your on-premises data center.   |
      +-----------------------------------+------------------------------------------------------------------+
      | Next Hop Type                     | Set it to **NAT gateway**.                                       |
      +-----------------------------------+------------------------------------------------------------------+
      | Next Hop                          | Set **Next Hop** to the private NAT gateway.                     |
      +-----------------------------------+------------------------------------------------------------------+
      | Description                       | (Optional) Supplementary information about the route             |
      |                                   |                                                                  |
      |                                   | Enter up to 255 characters. Angle brackets (<>) are not allowed. |
      +-----------------------------------+------------------------------------------------------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0283962445.png
