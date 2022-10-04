:original_name: nat_faq_0013.html

.. _nat_faq_0013:

What Are the Differences Between Using a NAT Gateway and Using an EIP for an ECS?
=================================================================================

A NAT gateway provides SNAT and DNAT, so multiple ECSs can share an EIP.

An ECS can also have an EIP bound to it. The EIP does not have to be shared.

If both SNAT and EIP are configured for an ECS, data will be forwarded through the EIP.

If both DNAT and EIP are configured for an ECS, the ECS will have two EIPs, one that is directly bound to the ECS and one that is associated with the DNAT rule. Incoming data will be forwarded by one of the two EIPs, which is determined by the client user. Outgoing data will be forwarded by the EIP directly bound to the ECS in priority. If the two EIPs are different, data forwarding will fail.

Configuring both a NAT gateway and an EIP for an ECS is not recommended.
