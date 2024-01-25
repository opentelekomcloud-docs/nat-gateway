:original_name: nat_faq_0015.html

.. _nat_faq_0015:

What Are the Relationships and Differences Between the CIDR Blocks in a NAT Gateway and in an SNAT Rule?
========================================================================================================

When creating a NAT gateway, you must specify the VPC and subnet CIDR block for the NAT gateway. This CIDR block can only be used by the system.

When you are creating an SNAT rule with **Scenario** set to **VPC**, configure a subnet CIDR block for the VPC so that servers in the subnet can access the Internet through the SNAT rule.

When you are creating an SNAT rule with **Scenario** set to **Direct Connect**, configure the CIDR block of a local data center or another VPC so that ECSs in the CIDR block can access the Internet through the SNAT rule.
