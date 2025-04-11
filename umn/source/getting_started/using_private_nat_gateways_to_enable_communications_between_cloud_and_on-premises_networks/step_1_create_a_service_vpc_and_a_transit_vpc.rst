:original_name: nat_qs_0021.html

.. _nat_qs_0021:

Step 1: Create a Service VPC and a Transit VPC
==============================================

Scenarios
---------

You need to create two VPCs, a service VPC with a service subnet and a transit VPC with a transit subnet.

Procedure
---------

For details, see `Creating a VPC <https://docs.otc.t-systems.com/virtual-private-cloud/umn/vpc_and_subnet/vpc/creating_a_vpc.html>`__.

.. table:: **Table 1** VPC and subnet settings

   =========================== ==============================
   VPC CIDR Block              Subnet CIDR Block
   =========================== ==============================
   Service VPC: 192.168.0.0/16 Service subnet: 192.168.0.0/24
   Transit VPC: 10.1.0.0/16    Transit subnet: 10.1.0.0/24
   =========================== ==============================
