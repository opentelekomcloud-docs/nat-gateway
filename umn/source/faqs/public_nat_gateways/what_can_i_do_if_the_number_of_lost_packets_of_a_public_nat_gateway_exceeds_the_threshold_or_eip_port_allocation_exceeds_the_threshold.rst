:original_name: nat_faq_0025.html

.. _nat_faq_0025:

What Can I Do If the Number of Lost Packets of a Public NAT Gateway Exceeds the Threshold (or EIP Port Allocation Exceeds the Threshold)?
=========================================================================================================================================

If the number of lost packets exceeds the upper limit (that is, the number of allocated EIP ports exceeds the upper limit) when the public NAT gateway is in use, the EIP ports bound to the SNAT rule have been used up. You are advised to increase the number of EIPs bound to the SNAT rule.
