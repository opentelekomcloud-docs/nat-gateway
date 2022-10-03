:original_name: nat_pro_0004.html

.. _nat_pro_0004:

Basic Concepts
==============

EIP
---

An EIP can be directly accessed over the Internet. A private IP address is an IP address on a local area network (LAN) and cannot be routed through the Internet.

An EIP is a static, public IP address. You can bind an EIP to an ECS in your subnet to enable the ECS in your VPC to communicate with the Internet through a fixed public IP address.

Each EIP can be used by only one ECS at a time.

SNAT Connections
----------------

An SNAT connection consists of the source IP address, source port, destination IP address, destination port, and transmission-layer protocol. The source IP address refers to the EIP, and the source port refers to the EIP port. They will be used to access the destination IP address and port of the Internet. These five elements identify a connection as a unique session.

DNAT Connections
----------------

A DNAT connection enables servers in a VPC to share an EIP to provide services accessible from the Internet through IP address or port mapping.
