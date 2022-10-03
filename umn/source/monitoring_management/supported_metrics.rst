:original_name: nat_ces_0002.html

.. _nat_ces_0002:

Supported Metrics
=================

Description
-----------

This section describes metrics reported by NAT Gateway to Cloud Eye as well as their namespaces, monitoring metrics, and dimensions. You can use the management console or the APIs provided by Cloud Eye to query the metrics generated for NAT Gateway.

Namespace
---------

SYS.NAT

Metrics
-------

+-----------------------+------------------------------+--------------------------------------------------------------------------+-------------+---------------------------------+--------------------------------+
| Metric                | Name                         | Description                                                              | Value Range | Measurement Object & Dimension  | Monitoring Interval (Raw Data) |
+=======================+==============================+==========================================================================+=============+=================================+================================+
| snat_connection       | SNAT Connections             | Number of SNAT connections of the NAT gateway                            | ≥ 0         | Measurement object: NAT gateway | 1 minute                       |
|                       |                              |                                                                          |             |                                 |                                |
|                       |                              | Unit: Count                                                              |             | Dimension:                      |                                |
|                       |                              |                                                                          |             |                                 |                                |
|                       |                              |                                                                          |             | nat_gateway_id                  |                                |
+-----------------------+------------------------------+--------------------------------------------------------------------------+-------------+---------------------------------+--------------------------------+
| Server IP address set | Monitoring Details of Top 10 | IP addresses of the top 10 servers that occupy the most SNAT connections | ≥ 0         | Measurement object: NAT gateway | 1 minute                       |
|                       |                              |                                                                          |             |                                 |                                |
|                       |                              | Unit: Count                                                              |             | Dimension:                      |                                |
|                       |                              |                                                                          |             |                                 |                                |
|                       |                              |                                                                          |             | nat_gateway_id                  |                                |
+-----------------------+------------------------------+--------------------------------------------------------------------------+-------------+---------------------------------+--------------------------------+

Dimensions
----------

============== ==============
Key            Value
============== ==============
nat_gateway_id NAT gateway ID
============== ==============
