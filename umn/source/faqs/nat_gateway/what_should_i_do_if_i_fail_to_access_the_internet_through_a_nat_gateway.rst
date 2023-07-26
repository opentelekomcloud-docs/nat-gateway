:original_name: nat_faq_0011.html

.. _nat_faq_0011:

What Should I Do If I Fail to Access the Internet Through a NAT Gateway?
========================================================================

If your server cannot access the Internet through a NAT gateway, you may have configured the VPC route table incorrectly. Perform the following steps to reset the route table:

#. Locate the route table associated with the subnet in the VPC.
#. Check whether the route table contains the route to the NAT gateway. If not, add the route.
#. Ensure that the destination address of the route to be added contain the target address.
