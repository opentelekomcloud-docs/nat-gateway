:original_name: nat_faq_0013.html

.. _nat_faq_0013:

What Are the Differences Between Using a Public NAT Gateway and Using an EIP for an ECS?
========================================================================================

Public NAT gateways support both SNAT and DNAT and allow multiple ECSs to share EIPs.

An EIP bound to an ECS cannot be used by any other ECSs.

If both SNAT and EIP are configured for an ECS, the EIP is preferentially used for data forwarding.

If both DNAT and EIP are configured for an ECS, inbound traffic will be forwarded by the EIP configured for the DNAT rule or the EIP directly bound to the ECS, which is determined by the client user. The outbound traffic will be forwarded by the EIP bound to the ECS preferentially. If the EIPs used for forwarding inbound and outbound traffic are different, the traffic will fail to be forwarded.

Associating an ECS with both an EIP and a public NAT gateway is not recommended.
