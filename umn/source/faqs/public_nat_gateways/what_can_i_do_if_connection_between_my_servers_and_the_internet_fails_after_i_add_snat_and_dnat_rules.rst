:original_name: nat_faq_0021.html

.. _nat_faq_0021:

What Can I Do If Connection Between My Servers and the Internet Fails After I Add SNAT and DNAT Rules?
======================================================================================================

Symptom
-------

You have created a NAT gateway and added SNAT and DNAT rules, but your servers cannot access the Internet or provide services accessible from the Internet. Whether the network configured with a public NAT Gateway can connect to the Internet depends on the configurations of route tables, security groups, and firewalls. If any configuration problem occurs, the network connection will fail. This section describes how to troubleshoot network disconnection after a public NAT gateway is created.

Fault Locating
--------------

The following fault causes are listed in descending order of occurrence probability.

If the fault persists after one possible cause is ruled out, move down the list to the other possible causes.

.. table:: **Table 1** Network disconnection troubleshooting

   +-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Possible Cause                                                          | Solution                                                                                                                                                                                                                                                |
   +=========================================================================+=========================================================================================================================================================================================================================================================+
   | The route table is incorrectly configured.                              | Add the default route or a route pointing to the public NAT gateway to the route table. For details, see :ref:`Checking Whether Default Route Pointing to the Public NAT Gateway Is Configured in the Route Table <nat_faq_0021__section129707218368>`. |
   +-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | The ECS has an EIP bound.                                               | Unbind the EIP from the ECS. For details, see :ref:`Checking Whether the ECS Has an EIP Bound <nat_faq_0021__section17316124619465>`.                                                                                                                   |
   +-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | The security group rules are incorrectly configured.                    | Configure ECS security group rules to allow traffic to and from the ECS. For details, see :ref:`Checking Whether Security Group Rules Allow Traffic to and from the ECS Port <nat_faq_0021__en-us_topic_0167240183_section613741411410>`.               |
   +-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | The Firewall is incorrectly configured.                                 | Add Firewall rules to allow traffic in and out of the subnet. For details, see :ref:`Checking Whether Firewall Rules Allow Traffic in and out of the Subnet <nat_faq_0021__section1424613193138>`.                                                      |
   +-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | The EIP bandwidth exceeds the threshold.                                | Increase the EIP bandwidth by referring to :ref:`Checking Whether the EIP Bandwidth Limit Has Been Exceeded <nat_faq_0021__section10581714191816>`.                                                                                                     |
   +-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | The SNAT connection limit for the public NAT gateway has been exceeded. | Increase the public NAT gateway specifications. For details, see :ref:`Checking Whether the SNAT Connection Limit for the Public NAT Gateway Has Been Exceeded <nat_faq_0021__section2030319152515>`.                                                   |
   +-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | The public NAT gateway status is abnormal.                              | Ensure that the public NAT gateway is running. For details, see :ref:`Check Whether the Public NAT Gateway Status is Normal <nat_faq_0021__section7191162535712>`.                                                                                      |
   +-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | The ECS port is not listened on.                                        | Enable the ECS port again. For details, see :ref:`Checking ECS Ports <nat_faq_0021__en-us_topic_0167240183_section26656224106>`.                                                                                                                        |
   +-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _nat_faq_0021__section129707218368:

Checking Whether Default Route Pointing to the Public NAT Gateway Is Configured in the Route Table
--------------------------------------------------------------------------------------------------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the desired region and project.
#. Click **Service List** in the upper left corner. Under **Network**, select **Virtual Private Cloud**.
#. In the navigation pane on the left, choose **Route Tables**.
#. In the route table list, click the name of the route table associated with the VPC to which the public NAT gateway belongs.
#. Check whether default route (0.0.0.0/0) pointing to the public NAT gateway is in the route list.

   -  If no, add the default route pointing to the public NAT gateway to the route table.

      a. Click **Add Route** and configure required parameters.

         .. table:: **Table 2** Descriptions of route parameters

            +-----------------------------------+------------------------------------------------------------------+
            | Parameter                         | Description                                                      |
            +===================================+==================================================================+
            | Destination                       | The destination CIDR block                                       |
            |                                   |                                                                  |
            |                                   | Set it to **0.0.0.0/0**.                                         |
            +-----------------------------------+------------------------------------------------------------------+
            | Next Hop Type                     | Set it to **NAT gateway**.                                       |
            +-----------------------------------+------------------------------------------------------------------+
            | Next Hop                          | Set it to the ID of the public NAT gateway you purchased.        |
            +-----------------------------------+------------------------------------------------------------------+
            | Description                       | (Optional) Supplementary information about the route             |
            |                                   |                                                                  |
            |                                   | Enter up to 255 characters. Angle brackets (<>) are not allowed. |
            +-----------------------------------+------------------------------------------------------------------+

      b. Click **OK**.

   -  If a default route is there but does not point to the public NAT gateway, add a route pointing to the public NAT gateway to the existing route table. Alternatively, create a route table and add a default route pointing to the public NAT gateway to the new route table.

      -  To add a route pointing to the public NAT gateway to the existing route table, perform the following steps:

         a. Click **Add Route** and configure required parameters.

            .. table:: **Table 3** Descriptions of route parameters

               +-----------------------------------+------------------------------------------------------------------+
               | Parameter                         | Description                                                      |
               +===================================+==================================================================+
               | Destination                       | The destination CIDR block                                       |
               +-----------------------------------+------------------------------------------------------------------+
               | Next Hop Type                     | Set it to **NAT gateway**.                                       |
               +-----------------------------------+------------------------------------------------------------------+
               | Next Hop                          | Set it to the ID of the public NAT gateway you purchased.        |
               +-----------------------------------+------------------------------------------------------------------+
               | Description                       | (Optional) Supplementary information about the route             |
               |                                   |                                                                  |
               |                                   | Enter up to 255 characters. Angle brackets (<>) are not allowed. |
               +-----------------------------------+------------------------------------------------------------------+

         b. Click **OK**.

      -  Create a route table and add a default route pointing to the public NAT gateway.

         a. In the upper right corner of the **Route Tables** page, click **Create Route Table** and configure required parameters.

            .. table:: **Table 4** Descriptions of route table parameters

               +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
               | Parameter             | Description                                                                                                                           | Example Value         |
               +=======================+=======================================================================================================================================+=======================+
               | Name                  | (Mandatory) The name of the route table                                                                                               | rtb-001               |
               |                       |                                                                                                                                       |                       |
               |                       | Enter up to 64 characters. Only letters, digits, underscores (_), hyphens (-), and periods (.) are allowed. Spaces are not allowed.   |                       |
               +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
               | VPC                   | (Mandatory) The VPC that the route table belongs to                                                                                   | vpc-001               |
               +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
               | Description           | (Optional) Supplementary information about the route table                                                                            | N/A                   |
               |                       |                                                                                                                                       |                       |
               |                       | Enter up to 255 characters. Angle brackets (<>) are not allowed.                                                                      |                       |
               +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
               | Route Settings        | Information about routes                                                                                                              | N/A                   |
               |                       |                                                                                                                                       |                       |
               |                       | You can click **Add Route** to add more routes.                                                                                       |                       |
               |                       |                                                                                                                                       |                       |
               |                       | Set **Destination** to **0.0.0.0/0**, **Next Hop Type** to **NAT gateway**, and **Next Hop** to the public NAT gateway you purchased. |                       |
               +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

         b. Click **OK**.

            An **Information** dialog box is displayed, indicating that you can associate the route table with a subnet now or later.

         c. Click **Associate Subnet**.

            The **Associated Subnets** tab is displayed.

         d. Click **Associate Subnet** and select the subnet to be associated.

         e. Click **OK**.

.. _nat_faq_0021__section17316124619465:

Checking Whether the ECS Has an EIP Bound
-----------------------------------------

If both SNAT and EIP are configured for an ECS, the EIP is preferentially used for data forwarding.

If both DNAT and EIP are configured for an ECS, the ECS will have two EIPs, one that is bound to the ECS and one that is associated with the DNAT rule. Incoming data will be forwarded by one of the two EIPs, which is determined by the user of the client. Outgoing data will be forwarded by the EIP bound to the ECS in priority. If the two EIPs are different, data forwarding will fail.

If the ECS has an EIP bound, perform the following steps to unbind the EIP.

#. Log in to the management console.
#. Click |image2| in the upper left corner and select the desired region and project.
#. Under **Computing**, click **Elastic Cloud Server**.
#. In the list, locate the ECS. In the **IP Address** column, check whether the ECS has an EIP bound.

   -  If no, check the next item.

   -  If yes, unbind it.

      For details about how to unbind an EIP from an ECS, see `Unbinding an EIP from an ECS and Releasing the EIP <https://docs.otc.t-systems.com/elastic-ip/umn/elastic_ip/unbinding_an_eip_from_an_ecs_and_releasing_the_eip.html>`__.

.. _nat_faq_0021__en-us_topic_0167240183_section613741411410:

Checking Whether Security Group Rules Allow Traffic to and from the ECS Port
----------------------------------------------------------------------------

If the traffic to and from the ECS port is denied in the security group, add rules to the security group to allow the port traffic.

#. Log in to the management console.
#. Click |image3| in the upper left corner and select the desired region and project.
#. Under **Computing**, click **Elastic Cloud Server**.
#. On the **Elastic Cloud Server** page, click the name of the ECS.
#. Click the **Security Groups** tab and view security group rules.
#. Check whether you have configured inbound and outbound rules to allow traffic to and from the ECS port.

   -  If yes, check the next item.

   -  If no, click **Manage Rule**.

      On the **Summary** tab of the security group, click **Inbound Rules** or **Outbound Rules** to add an inbound rule and outbound rule that allow traffic to and from the ECS port. For details about inbound and outbound rule parameters, see `Creating a Security Group <https://docs.otc.t-systems.com/virtual-private-cloud/umn/access_control/security_group/managing_a_security_group/creating_a_security_group.html#en-us-topic-0013748715>`__.

.. _nat_faq_0021__section1424613193138:

Checking Whether Firewall Rules Allow Traffic in and out of the Subnet
----------------------------------------------------------------------

Check whether the VPC subnet is associated with Firewall rules. If yes, check the Firewall rules.

#. Log in to the management console.

#. Click |image4| in the upper left corner and select the desired region and project.

#. Click **Service List** in the upper left corner. Under **Network**, select **Virtual Private Cloud**.

#. In the navigation pane on the left, click **Subnets**.

#. Check whether the NAT gateway subnet is associated with a Firewall.

   The specific Firewall name indicates that the association is successful.

#. Click the Firewall name to view the details.

#. Check whether the inbound and outbound rules that allow traffic in and out of the subnet have been added.

   If no, add such inbound and outbound rules, or disassociate the Firewall from the subnet.

   For details, see `Add a Firewall Rule <https://docs.otc.t-systems.com/virtual-private-cloud/umn/access_control/firewall/index.html#vpc-acl-0000>`__ and `Disassociating a Subnet from a Firewall <https://docs.otc.t-systems.com/virtual-private-cloud/umn/vpc_and_subnet/subnet/index.html#>`__.

   .. note::

      The default Firewall rules deny all incoming and outgoing packets. After the Firewall is disabled, the default rules still take effect.

.. _nat_faq_0021__section10581714191816:

Checking Whether the EIP Bandwidth Limit Has Been Exceeded
----------------------------------------------------------

If an EIP is bound to the public NAT gateway, the bandwidth is used to provide access traffic between the public network and the public NAT gateway.

If the network is disconnected, check whether the EIP bandwidth exceeds the limit.

For details about how to increase the bandwidth, see `Modifying an EIP Bandwidth <https://docs.otc.t-systems.com/elastic-ip/umn/elastic_ip/modifying_an_eip_bandwidth.html>`__.

.. _nat_faq_0021__section2030319152515:

Checking Whether the SNAT Connection Limit for the Public NAT Gateway Has Been Exceeded
---------------------------------------------------------------------------------------

#. Log in to the management console.
#. Click |image5| in the upper left corner and select the desired region and project.
#. Click **Service List** in the upper left corner. Under **Management & Governance**, choose **Cloud Eye**.
#. In the navigation pane on the left, choose **Cloud Service Monitoring** > **NAT Gateway**.
#. Locate the row that contains the public NAT gateway you purchased and click **View Metric** in the **Operation** column to check detailed monitoring.
#. Check whether the SNAT connection limit for the public NAT gateway has been exceeded.

   -  If no, check the next item.

   -  If the number of SNAT connections exceeds the upper limit of the public NAT gateway specifications, increase the specifications.

      For details about how to increase the public NAT gateway specifications, see `Modifying a Public NAT Gateway <https://docs.otc.t-systems.com/nat-gateway/umn/managing_nat_gateways/modifying_a_public_nat_gateway.html>`__.

.. _nat_faq_0021__section7191162535712:

Check Whether the Public NAT Gateway Status is Normal
-----------------------------------------------------

#. Log in to the management console.
#. Click |image6| in the upper left corner and select the desired region and project.
#. Click **Service List** in the upper left corner. Under **Network**, select **NAT Gateway**.
#. In the public NAT gateway list, locate the NAT gateway and check whether its status is **Running**.

   -  If yes, check the next item.
   -  If no, the possible causes are as follows:

      -  Your account or resources are frozen because you violated related security requirements or laws and regulations when using the cloud platform. If you complete the rectification within the required period and meet related security and legal requirements, your account and resources can be unfrozen. If you do not complete the rectification within the required period, your resources will be deleted.

.. _nat_faq_0021__en-us_topic_0167240183_section26656224106:

Checking ECS Ports
------------------

Ensure that ECS ports are in the **LISTEN** state. :ref:`Table 5 <nat_faq_0021__en-us_topic_0167240183_table23951535155514>` lists the common TCP statuses.

-  Linux

   Run the **netstat -antp** command to check whether the ECS port is in the **LISTEN** state.

   For example, run **netstat -ntulp \|grep 80**.


   .. figure:: /_static/images/en-us_image_0000001154974329.png
      :alt: **Figure 1** Checking port listening status (Linux)

      **Figure 1** Checking port listening status (Linux)

   If no, enable the ECS port.

-  Windows

   Perform the following operations to check port communication:

   #. Run **cmd.exe**.

   #. Run the **netstat** **-ano \| findstr "**\ *PID*\ **"** command to obtain the PID used by the process.

      For example, run **netstat -ano \| findstr "80"**.


      .. figure:: /_static/images/en-us_image_0000001108294612.png
         :alt: **Figure 2** Checking port listening status (Windows)

         **Figure 2** Checking port listening status (Windows)

      If no, enable the ECS port.

.. _nat_faq_0021__en-us_topic_0167240183_table23951535155514:

.. table:: **Table 5** Common TCP statuses

   +-------------+--------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | TCP Status  | Description                                                                                                  | Scenario                                                                                                                                                                                                                                                              |
   +=============+==============================================================================================================+=======================================================================================================================================================================================================================================================================+
   | LISTEN      | Listens for network connection requests from a remote TCP port.                                              | The TCP server is running properly.                                                                                                                                                                                                                                   |
   +-------------+--------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ESTABLISHED | Indicates that a connection has been set up.                                                                 | A TCP connection is properly set up.                                                                                                                                                                                                                                  |
   +-------------+--------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | TIME-WAIT   | Waits until the remote TCP server receives the acknowledgement of the connection termination request.        | The TCP connection is terminated, and the session is closed in 1 minute.                                                                                                                                                                                              |
   +-------------+--------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | CLOSE-WAIT  | Waits for a connection termination request sent by a local user.                                             | An application program fault leads to an open socket. This state is displayed after the network is disconnected, indicating that a process is in an infinite loop or waiting for certain requirements to be met. To resolve this issue, restart the affected process. |
   +-------------+--------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | FIN-WAIT-2  | Waits for the network termination request from a remote TCP server.                                          | The network has been disconnected and requires 12 minutes to automatically recover.                                                                                                                                                                                   |
   +-------------+--------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | SYN-SENT    | Waits for the matched network connection request after a network connection request is sent.                 | The TCP connection request failed, which is generally caused by the delayed handling of high CPU usage on the server or by a DDoS attack.                                                                                                                             |
   +-------------+--------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | FIN-WAIT-1  | Waits for the remote TCP disconnection request, or the acknowledgement for a previous disconnection request. | If the network has been disconnected, this state may not automatically recover after 15 minutes. If the port remains occupied for a long period of time, restart the OS to resolve the issue.                                                                         |
   +-------------+--------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001156876053.png
.. |image2| image:: /_static/images/en-us_image_0000001182300205.png
.. |image3| image:: /_static/images/en-us_image_0000001110876070.png
.. |image4| image:: /_static/images/en-us_image_0000001111039460.png
.. |image5| image:: /_static/images/en-us_image_0000001157479305.png
.. |image6| image:: /_static/images/en-us_image_0000001111199360.png
