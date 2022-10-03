:original_name: nat_faq_001.html

.. _nat_faq_001:

Why Is SNAT Used?
=================

Besides requiring services provided by the system, some ECSs also need to access the Internet to obtain information or download software. However, assigning a public IP address to each ECS consumes already-limited IPv4 addresses, incurs additional costs, and may increase the attack surface in a virtual environment. Enabling multiple ECSs to share a single public IP address is preferable and more practical. This can be done using SNAT.
