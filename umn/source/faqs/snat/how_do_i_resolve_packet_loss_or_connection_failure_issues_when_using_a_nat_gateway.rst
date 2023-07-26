:original_name: nat_faq_0016.html

.. _nat_faq_0016:

How Do I Resolve Packet Loss or Connection Failure Issues When Using a NAT Gateway?
===================================================================================

If packet loss or connection failures occur on a server that uses the NAT gateway to access the Internet, you can check the SNAT connections on the Cloud Eye console. If the number of SNAT connections exceeds what the NAT gateway specifications support, there will be packet loss or connection failures. If the number of connections exceeds the upper limit, change the NAT gateway specifications.
