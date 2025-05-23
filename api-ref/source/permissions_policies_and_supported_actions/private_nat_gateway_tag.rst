:original_name: nat_api_0074.html

.. _nat_api_0074:

Private NAT Gateway - Tag
=========================

+----------------------------------------------------------------+-----------------------------------------------------------------+-----------------+--------------------+
| Permission                                                     | API                                                             | IAM Project     | Enterprise Project |
+================================================================+=================================================================+=================+====================+
| Adding a Tag to a Private NAT Gateway                          | POST                                                            | Y               | Y                  |
|                                                                |                                                                 |                 |                    |
|                                                                | /v3/{project_id}/private-nat-gateways/{resource_id}/tags        |                 |                    |
+----------------------------------------------------------------+-----------------------------------------------------------------+-----------------+--------------------+
| Batch Adding or Deleting Tags to or from a Private NAT Gateway | POST                                                            | Y               | Y                  |
|                                                                |                                                                 |                 |                    |
|                                                                | /v3/{project_id}/private-nat-gateways/{resource_id}/tags/action |                 |                    |
+----------------------------------------------------------------+-----------------------------------------------------------------+-----------------+--------------------+
| Querying Private NAT Gateways by Tag                           | POST                                                            | Y               | x                  |
|                                                                |                                                                 |                 |                    |
|                                                                | /v3/{project_id}/private-nat-gateways/resource_instances/action |                 |                    |
+----------------------------------------------------------------+-----------------------------------------------------------------+-----------------+--------------------+
| Querying Tags of a Private NAT Gateway                         | GET /v3/{project_id}/private-nat-gateways/{resource_id}/tags    | Y               | Y                  |
+----------------------------------------------------------------+-----------------------------------------------------------------+-----------------+--------------------+
| Querying Tags of All Private NAT Gateways in a Project         | GET /v3/{project_id}/private-nat-gateways/tags                  | Y               | x                  |
+----------------------------------------------------------------+-----------------------------------------------------------------+-----------------+--------------------+
| Deleting a Tag from a Private NAT Gateway                      | DELETE                                                          | Y               | Y                  |
|                                                                |                                                                 |                 |                    |
|                                                                | /v3/{project_id}/private-nat-gateways/{resource_id}/tags/{key}  |                 |                    |
+----------------------------------------------------------------+-----------------------------------------------------------------+-----------------+--------------------+
