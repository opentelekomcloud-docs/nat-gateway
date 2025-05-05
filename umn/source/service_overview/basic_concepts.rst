:original_name: nat_pro_0004.html

.. _nat_pro_0004:

Basic Concepts
==============

EIP
---

An EIP is a static, public IP address.

An EIP can be directly accessed over the Internet. A private IP address is an IP address on a local area network (LAN) and cannot be routed through the Internet.

You can bind an EIP to an ECS in your subnet to enable the ECS to communicate with the Internet.

Each EIP can be used by only one ECS at a time. To enable servers in a VPC, regardless of if they are in the same AZ, to share an EIP, use a public NAT gateway.

SNAT Connections
----------------

An SNAT connection consists of a source IP address, source port, destination IP address, destination port, and a transport layer protocol. The source IP address and port are the IP address and port translated by SNAT. An SNAT connection uniquely identifies a session.

DNAT Connections
----------------

DNAT connections enable servers in a private network, regardless of if they are in the same AZ, to share an EIP to provide services accessible from the Internet.
