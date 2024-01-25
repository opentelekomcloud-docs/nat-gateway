:original_name: nat_pro_0003.html

.. _nat_pro_0003:

Using NAT Gateway with Other Services
=====================================

.. table:: **Table 1** Related services

   +-----------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+--------------------------------------------------------------------------------------------------+
   | Interaction                                                                                                                 | Cloud Service                                       | Reference                                                                                        |
   +=============================================================================================================================+=====================================================+==================================================================================================+
   | Local servers that need to communicate with the Internet using a NAT gateway can connect to a VPC using Direct Connect.     | Direct Connect                                      | :ref:`Allowing On-Premises Servers to Communicate with the Internet <nat_qs_0012>`               |
   +-----------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+--------------------------------------------------------------------------------------------------+
   | Local servers that need to communicate with the Internet using a NAT gateway can connect to a VPC through a VPN connection. | Virtual Private Network (VPN)                       | :ref:`Allowing On-Premises Servers to Communicate with the Internet <nat_qs_0012>`               |
   +-----------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+--------------------------------------------------------------------------------------------------+
   | Cloud servers can communicate with the Internet through NAT gateways.                                                       | Elastic Cloud Server (ECS), Bare Metal Server (BMS) | :ref:`Allowing a Private Network to Access the Internet Using SNAT <nat_qs_0001>`                |
   |                                                                                                                             |                                                     |                                                                                                  |
   |                                                                                                                             |                                                     | :ref:`Allowing Internet Users to Access a Service in a Private Network Using DNAT <nat_qs_0006>` |
   +-----------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+--------------------------------------------------------------------------------------------------+
