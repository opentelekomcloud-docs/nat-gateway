:original_name: en-us_topic_0086739763.html

.. _en-us_topic_0086739763:

NAT Gateway Types
=================

A NAT gateway type specifies the maximum number of SNAT connections supported by a NAT gateway.

An SNAT connection consists of the source IP address, source port, destination IP address, destination port, and transmission-layer protocol. The source IP address refers to the EIP, and the source port refers to the EIP port. They will be used to access the destination IP address and port of the Internet. These five elements identify a connection as a unique session.

The data throughput of a NAT gateway is determined by the sum of the EIP bandwidths used by its DNAT rules. For example, if a NAT gateway has two DNAT rules, and their EIP bandwidths are 10 Mbit/s and 5 Mbit/s, respectively, the throughput of the NAT gateway is 15 Mbit/s.

When creating a NAT gateway, select the type based on your service requirements. :ref:`Table 1 <en-us_topic_0086739763__table39923257151849>` lists the NAT gateway types.

.. _en-us_topic_0086739763__table39923257151849:

.. table:: **Table 1** NAT gateway types

   =========== ==================================
   Type        Maximum Number of SNAT Connections
   =========== ==================================
   Small       10,000
   Medium      50,000
   Large       200,000
   Extra-large 1,000,000
   =========== ==================================

.. note::

   -  If the requests exceed the maximum connections allowed by your NAT gateway, your services will be adversely affected. To avoid this situation, create alarm rules for the SNAT connection in Cloud Eye.
   -  A maximum of 200 DNAT rules can be added for each NAT gateway. The number of DNAT rules that you can add for a NAT gateway has no relationship with the NAT gateway type. The number of SNAT rules that you can add for a NAT gateway has no relationship with the NAT gateway type.
