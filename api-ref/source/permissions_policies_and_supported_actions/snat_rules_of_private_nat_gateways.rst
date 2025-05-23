:original_name: nat_api_0072.html

.. _nat_api_0072:

SNAT Rules of Private NAT Gateways
==================================

+-----------------------+---------------------------------------------------------------+-------------+--------------------+
| Permission            | API                                                           | IAM Project | Enterprise Project |
+=======================+===============================================================+=============+====================+
| Creating an SNAT Rule | POST /v3/{project_id}/private-nat/snat-rules                  | Y           | Y                  |
+-----------------------+---------------------------------------------------------------+-------------+--------------------+
| Querying an SNAT Rule | GET /v3/{project_id}/private-nat/snat-rules/{snat_rule_id}    | Y           | Y                  |
+-----------------------+---------------------------------------------------------------+-------------+--------------------+
| Querying SNAT Rules   | GET /v3/{project_id}/private-nat/snat-rules                   | Y           | Y                  |
+-----------------------+---------------------------------------------------------------+-------------+--------------------+
| Updating an SNAT Rule | PUT /v3/{project_id}/private-nat/snat-rules/{snat_rule_id}    | Y           | Y                  |
+-----------------------+---------------------------------------------------------------+-------------+--------------------+
| Deleting an SNAT Rule | DELETE /v3/{project_id}/private-nat/snat-rules/{snat_rule_id} | Y           | Y                  |
+-----------------------+---------------------------------------------------------------+-------------+--------------------+
