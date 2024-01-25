:original_name: nat_faq_0013.html

.. _nat_faq_0013:

For an ECS, Is There Any Difference Between Using a NAT Gateway and Directly Having an EIP Bound?
=================================================================================================

The NAT gateway provides the SNAT and DNAT functions, allowing multiple ECSs to share one EIP.

The ECS that has an EIP bound is exclusively using the IP address.

If both SNAT and EIP are configured for an ECS, data will be preferentially forwarded through the EIP.

If both DNAT and EIP are configured for an ECS, the ECS will have two EIPs, one that is directly bound to the ECS and one that is associated with the DNAT rule. Incoming data will be forwarded by one of the two EIPs, which is determined by the client user. Outgoing data will be forwarded by the EIP directly bound to the ECS in priority. If the two EIPs are different, data forwarding will fail.

Therefore, you are not advised to use a NAT gateway and bind an EIP to the same ECS at the same time.
