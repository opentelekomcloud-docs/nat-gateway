:original_name: en-us_topic_0086739750.html

.. _en-us_topic_0086739750:

Notes and Constraints
=====================

When using a NAT gateway:

-  Multiple rules for one NAT gateway can use the same EIP, but the rules for different NAT gateways must use different EIPs.
-  Each VPC can only have one NAT gateway.
-  Manually adding the default route for a VPC is not allowed.
-  Each VPC subnet can only be used in one SNAT rule.
-  SNAT and DNAT rules cannot share the same EIP.
-  DNAT rules do not support the mapping between an EIP and a virtual IP address.
-  If both an EIP and a NAT gateway are configured for a server, data will be forwarded through the EIP.
-  When you add an SNAT rule, if the rule is used in the VPC scenario, the custom CIDR block must be a subset of the NAT gateway's VPC subnets. If the rule is used in the Direct Connect scenario, the custom CIDR block must be a CIDR block of a Direct Connect connection and cannot overlap with the NAT gateway's VPC subnets.
-  You can configure only one DNAT rule for each port of a server. One port can be mapped to only one EIP.
-  The DNAT rules of a NAT gateway are irrelevant to the NAT gateway specifications. A maximum of 200 DNAT rules can be added to a NAT gateway. The number of SNAT rules that you can add for a NAT gateway has no relationship with the NAT gateway specifications.
