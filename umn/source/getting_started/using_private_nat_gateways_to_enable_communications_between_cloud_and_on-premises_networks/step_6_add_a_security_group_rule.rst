:original_name: nat_qs_0040.html

.. _nat_qs_0040:

Step 6: Add a Security Group Rule
=================================

Scenarios
---------

Add an inbound security group rule to allow traffic to servers in the destination VPC.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click **Service List** in the upper left corner. Under **Network**, select **Virtual Private Cloud**.

#. In the navigation pane on the left, choose **Access Control** > **Security Groups**.

   The security group list is displayed.

#. Locate the target security group and click **Manage Rules** in the **Operation** column.

   The page for configuring security group rules is displayed.

#. On the **Inbound Rules** tab, click **Add Rule**. In the displayed dialog box, configure required parameters.

   You can click **+** to add more inbound rules.

   .. table:: **Table 1** Inbound rule parameter descriptions

      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                | Example Value         |
      +=======================+============================================================================================================================================+=======================+
      | Protocol & Port       | **Protocol**: network protocol                                                                                                             | TCP                   |
      |                       |                                                                                                                                            |                       |
      |                       | The protocol can be **All**, **TCP**, **UDP**, **ICMP**, or **GRE**.                                                                       |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      |                       | **Port**: the port or port range over which the traffic can reach your ECS                                                                 | 22 or 22-30           |
      |                       |                                                                                                                                            |                       |
      |                       | Supported range: 1 to 65535                                                                                                                |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Type                  | The IP address type.                                                                                                                       | **IPv4**              |
      |                       |                                                                                                                                            |                       |
      |                       | -  **IPv4**                                                                                                                                |                       |
      |                       | -  **IPv6**                                                                                                                                |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Source                | The source of the security group rule                                                                                                      | 0.0.0.0/0             |
      |                       |                                                                                                                                            |                       |
      |                       | The source can be an IP address or a security group to allow access from IP addresses or instances in another security group. For example: |                       |
      |                       |                                                                                                                                            |                       |
      |                       | -  *xxx.xxx.xxx.xxx*\ **/32** (an IPv4 address)                                                                                            |                       |
      |                       | -  *xxx.xxx.xxx*\ **.0/24** (a subnet)                                                                                                     |                       |
      |                       | -  **0.0.0.0/0** (all IP addresses)                                                                                                        |                       |
      |                       | -  **sg-abc** (a security group)                                                                                                           |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | (Optional) Supplementary information about the security group rule                                                                         | N/A                   |
      |                       |                                                                                                                                            |                       |
      |                       | Enter up to 255 characters. Angle brackets (<>) are not allowed.                                                                           |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0283962445.png
