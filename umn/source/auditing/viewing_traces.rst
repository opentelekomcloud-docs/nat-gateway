:original_name: nat_cts_0002.html

.. _nat_cts_0002:

Viewing Traces
==============

Scenarios
---------

CTS records the operations performed on NAT Gateway and allows you to view the operation records of the last seven days on the CTS console. This topic describes how to query these records.

Procedure
---------

#. Log in to the management console.

#. In the upper left corner of the page, click |image1| and select the desired region and project.

#. Under **Management & Deployment**, click **Cloud Trace Service**.

#. In the navigation pane on the left, choose **Trace List**.

#. Specify the filters used for querying traces. The following filters are available:


   .. figure:: /_static/images/en-us_image_0000001200039028.png
      :alt: **Figure 1** Filters

      **Figure 1** Filters

   -  **Trace Type**, **Trace Source**, **Resource Type**, and **Search By**

      Select a filter from the drop-down list.

      If you select **Trace name** for **Search By**, select a specific trace name.

      If you select **Resource ID** for **Search By**, select or enter a specific resource ID.

      If you select **Resource name** for **Search By**, select or enter a specific resource name.

   -  **Operator**: Select a specific operator (at the user level rather than the tenant level).

   -  **Trace Status**: Available options include **All trace statuses**, **normal**, **warning**, and **incident**. You can only select one of them.

   -  Time range: You can query traces generated at any time range of the last seven days.

#. Click |image2| on the left of the required trace to expand its details.


   .. figure:: /_static/images/en-us_image_0000001199879050.png
      :alt: **Figure 2** Expanding trace details

      **Figure 2** Expanding trace details

#. Click **View Trace** in the **Operation** column to view trace details.


   .. figure:: /_static/images/en-us_image_0000001244918899.png
      :alt: **Figure 3** View Trace

      **Figure 3** View Trace

   For details about key fields in the trace, see section "Trace Structure" in *Cloud Trace Service User Guide*.

.. |image1| image:: /_static/images/en-us_image_0000001211126503.png
.. |image2| image:: /_static/images/en-us_image_0000001244918877.jpg
