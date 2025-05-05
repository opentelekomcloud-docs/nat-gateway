:original_name: en-us_topic_0086739750.html

.. _en-us_topic_0086739750:

Notes and Constraints
=====================

Public NAT Gateway
------------------

When using a public NAT gateway, note the following:

-  Common restrictions

   -  Rules on one public NAT gateway can use the same EIP, but rules on different NAT gateways must use different EIPs.
   -  Each VPC can be associated with multiple public NAT gateways.
   -  SNAT and DNAT rules can use the same EIP to save resources. However, when **Port Type** of a DNAT rule is set to **All ports**, the resource in the DNAT rule will preferentially use all ports of the EIP. So an SNAT rule cannot share an EIP with such a DNAT rule.
   -  If both an EIP and a public NAT gateway are configured for a server, data will be forwarded through the EIP.
   -  NAT Gateway supports TCP, UDP, and ICMP, but does not support application layer gateway (ALG)-related technologies. In addition, NAT Gateway does not support Encapsulating Security Payload (ESP) and Authentication Header (AH) used by Generic Routing Encapsulation (GRE) tunnels and Internet Protocol Security (IPsec). This is determined by the features of NAT Gateway.

-  SNAT restrictions

   -  Only one SNAT rule can be added for each VPC subnet.
   -  If an SNAT rule is used in the Direct Connect scenario, the custom CIDR block must be a CIDR block of a Direct Connect connection and cannot overlap with the NAT gateway's VPC subnets.
   -  There is no limit on the number of SNAT rules that can be added on a public NAT gateway.

-  DNAT restrictions

   -  Only one DNAT rule can be configured for each port on a server. One port can be mapped to only one EIP.
   -  A maximum of 200 DNAT rules can be added on a public NAT gateway.

Private NAT Gateway
-------------------

When using a private NAT gateway, note the following:

-  Common restrictions

   -  Manually add routes in a VPC to connect it to a remote private network through a VPC peering connection, Direct Connect, or VPN connection.
   -  The transit IP address and destination IP address cannot be in the same VPC.
   -  SNAT and DNAT rules cannot share a transit IP address.
   -  The total number of DNAT and SNAT rules that can be added on a private NAT gateway varies with the private NAT gateway specifications.

      -  Small: 20 or less
      -  Medium: 50 or less
      -  Large: 200 or less
      -  Extra-large: 500 or less

-  SNAT restrictions

   -  Only one SNAT rule can be added for each VPC subnet.

-  DNAT restrictions

   -  A DNAT rule with **Port Type** set to **All ports** cannot share a transit IP address with a DNAT rule with **Port Type** set to **Specific port**.
