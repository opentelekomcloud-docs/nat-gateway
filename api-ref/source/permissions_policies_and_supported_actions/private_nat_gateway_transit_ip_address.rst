:original_name: nat_api_0071.html

.. _nat_api_0071:

Private NAT Gateway - Transit IP Address
========================================

+--------------------------------+-----------------------------------------------------------------+-------------+--------------------+
| Permission                     | API                                                             | IAM Project | Enterprise Project |
+================================+=================================================================+=============+====================+
| Assigning a Transit IP Address | POST /v3/{project_id}/private-nat/transit-ips                   | Y           | Y                  |
+--------------------------------+-----------------------------------------------------------------+-------------+--------------------+
| Querying a Transit IP Address  | GET /v3/{project_id}/private-nat/transit-ips/{transit_ip_id}    | Y           | Y                  |
+--------------------------------+-----------------------------------------------------------------+-------------+--------------------+
| Querying Transit IP Addresses  | GET /v3/{project_id}/private-nat/transit-ips                    | Y           | Y                  |
+--------------------------------+-----------------------------------------------------------------+-------------+--------------------+
| Releasing a Transit IP Address | DELETE /v3/{project_id}/private-nat/transit-ips/{transit_ip_id} | Y           | Y                  |
+--------------------------------+-----------------------------------------------------------------+-------------+--------------------+
