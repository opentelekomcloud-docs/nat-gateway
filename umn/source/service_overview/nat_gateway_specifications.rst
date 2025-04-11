:original_name: en-us_topic_0086739763.html

.. _en-us_topic_0086739763:

NAT Gateway Specifications
==========================

The NAT gateway performance is determined by the maximum number of SNAT connections supported.

Public NAT Gateway
------------------

An SNAT connection consists of a source IP address, source port, destination IP address, destination port, and a transport layer protocol. The source IP address is the EIP, and the source port is the EIP port. An SNAT connection uniquely identifies a session.

Throughput is the total bandwidth of all EIPs in DNAT rules. For example, a public NAT gateway has two DNAT rules. The EIP bandwidth in the first DNAT rule is 10 Mbit/s, and that in the second DNAT rule is 5 Mbit/s. The throughput of the public NAT gateway will be 15 Mbit/s.

The default timeout period of an SNAT connection over TCP is 900 seconds.

The default timeout period of an SNAT connection over UDP is 300 seconds.

Select a public NAT gateway based on your service requirements. :ref:`Table 1 <en-us_topic_0086739763__table39923257151849>` lists the public NAT gateway specifications.

.. _en-us_topic_0086739763__table39923257151849:

.. table:: **Table 1** Public NAT gateway specifications

   ============== ================ ========= ========================
   Specifications SNAT Connections Bandwidth Queries Per Second (QPS)
   ============== ================ ========= ========================
   Small          10,000           20 Gbit/s 10,000
   Medium         50,000           20 Gbit/s 10,000
   Large          200,000          20 Gbit/s 10,000
   Extra-large    1,000,000        20 Gbit/s 10,000
   ============== ================ ========= ========================

.. note::

   -  The PPS of different NAT gateway specifications is the total PPS in both inbound and outbound directions.
   -  If the number of requests exceeds the maximum allowed connections of a public NAT gateway, services will be adversely affected. To avoid this situation, create alarm rules on the Cloud Eye console to monitor the number of SNAT connections.

Private NAT Gateway
-------------------

An SNAT connection consists of a source IP address, source port, destination IP address, destination port, and a transport layer protocol. The source IP address is the transit IP address, and the source port is the port of the transit IP address.

Select a private NAT gateway based on your service requirements. :ref:`Table 2 <en-us_topic_0086739763__table209462910468>` lists the private NAT gateway specifications.

.. _en-us_topic_0086739763__table209462910468:

.. table:: **Table 2** Private NAT gateway specifications

   ============== ================ ========== ======
   Specifications SNAT Connections Bandwidth  QPS
   ============== ================ ========== ======
   Small          2,000            200 Mbit/s 6000
   Medium         5,000            500 Mbit/s 9000
   Large          20,000           2 Gbit/s   10,000
   Extra-large    50,000           5 Gbit/s   10,000
   ============== ================ ========== ======

.. note::

   If the number of requests exceeds the maximum allowed connections of a private NAT gateway, services will be adversely affected. To avoid this situation, create alarm rules on the Cloud Eye console to monitor the number of SNAT connections.
