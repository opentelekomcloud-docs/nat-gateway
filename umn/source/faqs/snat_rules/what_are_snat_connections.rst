:original_name: nat_faq_0002.html

.. _nat_faq_0002:

What Are SNAT Connections?
==========================

The number of SNAT connections is the number of active connections created by a NAT gateway when it performs SNAT. An SNAT connection consists of a source IP address, source port, destination IP address, destination port, and a transport layer protocol. An SNAT connection uniquely identifies a session. The source IP address and port are the IP address and port translated by SNAT.

SNAT supports three protocols: TCP, UDP, and ICMP. A NAT gateway supports up to 55,000 concurrent connections to each destination IP address and port. If any of the destination IP address, port number, and protocol (TCP, UDP, or ICMP) changes, you can create another 55,000 connections. You can run the **netstat** command on an ECS to obtain the number of connections in the **ESTABLISHED** state, but this number reflects only the number of connections established to this ECS, and due to the impact of connection timeout, connection reuse, and other issues, this number may be different from the number of SNAT connections maintained by the NAT gateway. Assume that an ECS creates 100 connections to a fixed destination every second and there are no interrupted TCP connections, 55,000 connections will be used up in about 10 minutes. As a result, new connections cannot be established.

If there is no data packet passing through the SNAT connection for a long time, the connection will be timed out.
