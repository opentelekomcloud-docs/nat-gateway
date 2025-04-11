:original_name: nat_faq_001.html

.. _nat_faq_001:

Why Do I Need SNAT?
===================

**Public NAT gateways:** Besides requiring services provided by the system, some ECSs also need to access the Internet to obtain information or download software. However, assigning a public IP address to each ECS consumes already-limited IPv4 addresses, incurs additional costs, and may increase the attack surface in a virtual environment. Enabling multiple ECSs to share a public IP address is preferable and more practical. This can be done using SNAT.

**Private NAT gateways**: Different departments of a large enterprise may have a large number of overlapping CIDR blocks. After the enterprise migrates its workloads to the cloud, those departments will not be able to communicate with each other. In this case, SNAT can be used to translate the IP addresses of multiple ECSs in a department into a transit IP address for accessing other departments. In other scenarios where high security is required, an industry regulation agency may require other organizations to use a specified IP address to access the regulation system. In this case, SNAT can translate the IP addresses of multiple servers in an organization to one transit IP address, that is, the specified IP address.
