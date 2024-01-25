:original_name: nat_api_0035.html

.. _nat_api_0035:

NAT Gateway Tag v2.0
====================

+-----------------------------------------------------------+-------------------------------------------------------------------+---------------------------+
| Permission                                                | API                                                               | Action                    |
+===========================================================+===================================================================+===========================+
| Adding NAT Gateway Resource Tags                          | POST /v2.0/{project_id}/nat_gateways/{nat_gateway_id}/tags        | nat:natGatewayTags:create |
+-----------------------------------------------------------+-------------------------------------------------------------------+---------------------------+
| Querying NAT Gateway Resource Tags                        | GET /v2.0/{project_id}/nat_gateways/{nat_gateway_id}/tags         | nat:natGatewayTags:get    |
+-----------------------------------------------------------+-------------------------------------------------------------------+---------------------------+
| Deleting NAT Gateway Resource Tags                        | DELETE /v2.0/{project_id}/nat_gateways/{nat_gateway_id}/{key}     | nat:natGatewayTags:delete |
+-----------------------------------------------------------+-------------------------------------------------------------------+---------------------------+
| Creating or Deleting NAT Gateway Resource Tags in Batches | POST /v2.0/{project_id}/nat_gateways/{nat_gateway_id}/tags/action | nat:natGatewayTags:create |
|                                                           |                                                                   |                           |
|                                                           |                                                                   | nat:natGatewayTags:delete |
+-----------------------------------------------------------+-------------------------------------------------------------------+---------------------------+
| Querying NAT Gateway Resources by Tag                     | POST /v2.0/{project_id}/nat_gateways/resource_instances/action    | nat:natGatewayTags:get    |
+-----------------------------------------------------------+-------------------------------------------------------------------+---------------------------+
| Querying NAT Gateway Tags in a Project                    | GET /v2.0/{project_id}/nat_gateways/tags                          | nat:natGatewayTags:get    |
+-----------------------------------------------------------+-------------------------------------------------------------------+---------------------------+
