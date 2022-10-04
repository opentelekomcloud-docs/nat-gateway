:original_name: nat_faq_0002.html

.. _nat_faq_0002:

What Are SNAT Connections?
==========================

An SNAT connection consists of the source IP address, source port, destination IP address, destination port, and transmission-layer protocol. These five elements identify a connection as a unique session. The source IP address refers to the EIP, and the source port refers to the EIP port. They will be used to access the destination IP address and port of the Internet.

SNAT supports three protocols: TCP, UDP, and ICMP. A NAT gateway supports up to 55,000 concurrent connections for each destination IP address and port. If any of the destination IP address, port number, and protocol (TCP/UDP/ICMP) changes, you can create another 55,000 connections. The number of connections you query on an ECS may be different from the actual number of SNAT connections. (You can run the **netstat** command to query the number of connections.) Assume that an ECS creates 100 connections to a fixed destination every second. 55,000 connections will be used up in about 10 minutes without considering the dropped idle connections. As a result, new connections cannot be established.

If there is no data packet passing through the SNAT connection for a long time, the connection will be timed out.
