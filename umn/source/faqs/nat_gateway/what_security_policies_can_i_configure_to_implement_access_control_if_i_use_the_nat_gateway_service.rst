:original_name: nat_faq_0020.html

.. _nat_faq_0020:

What Security Policies Can I Configure to Implement Access Control If I Use the NAT Gateway Service?
====================================================================================================

You can configure security groups and firewalls to implement access control.

-  A security group is a collection of access control rules for ECSs that have the same security protection requirements and are mutually trusted. After a security group is created, you can create various access rules for the security group, and these rules will apply to all ECSs added to this security group.
-  A firewall is an optional layer of security for your subnets. You can associate one or more subnets with a firewall to control traffic in and out of the subnets.

Security groups operate at the ECS level, whereas firewalls operate at the subnet level. You can use firewalls together with security groups to implement access control that is both comprehensive and fine-grained.

For details about security groups and firewalls, see `Security <https://docs.otc.t-systems.com/virtual-private-cloud/umn/operation_guide_new_console_edition/security/index.html>`__ in the *Virtual Private Cloud User Guide*.
