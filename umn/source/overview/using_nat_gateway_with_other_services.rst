:original_name: nat_pro_0003.html

.. _nat_pro_0003:

Using NAT Gateway with Other Services
=====================================

.. table:: **Table 1** Related services

   +-----------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+--------------------------------------------------------------------------------------------------------------+
   | Interaction                                                                                                                 | Cloud Service                                       | Reference                                                                                                    |
   +=============================================================================================================================+=====================================================+==============================================================================================================+
   | Local servers that need to communicate with the Internet using a NAT gateway can connect to a VPC using Direct Connect.     | Direct Connect                                      | :ref:`Using SNAT and DNAT Rules to Allow On-premises Servers to Communicate Over the Internet <nat_qs_0012>` |
   +-----------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+--------------------------------------------------------------------------------------------------------------+
   | Local servers that need to communicate with the Internet using a NAT gateway can connect to a VPC through a VPN connection. | Virtual Private Network (VPN)                       | :ref:`Using SNAT and DNAT Rules to Allow On-premises Servers to Communicate Over the Internet <nat_qs_0012>` |
   +-----------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+--------------------------------------------------------------------------------------------------------------+
   | Cloud servers can communicate with the Internet through NAT gateways.                                                       | Elastic Cloud Server (ECS), Bare Metal Server (BMS) | :ref:`Using SNAT to Access the Internet <nat_qs_0001>`                                                       |
   |                                                                                                                             |                                                     |                                                                                                              |
   |                                                                                                                             |                                                     | :ref:`Using DNAT to Provide Services Accessible from the Internet <nat_qs_0006>`                             |
   +-----------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+--------------------------------------------------------------------------------------------------------------+
