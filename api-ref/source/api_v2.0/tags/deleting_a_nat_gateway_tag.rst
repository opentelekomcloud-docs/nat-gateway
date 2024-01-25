:original_name: nat_api_0019.html

.. _nat_api_0019:

Deleting a NAT Gateway Tag
==========================

Function
--------

This API is idempotent.

When a tag is deleted, it is not verified. The tag key cannot be left blank or be an empty string. If the key of the tag to be deleted does not exist, 404 will be returned.

URI
---

DELETE /v2.0/{project_id}/nat_gateways/{nat_gateway_id}/tags/{key}

.. table:: **Table 1** Parameter description

   ============== ========= ====== =============================
   Parameter      Mandatory Type   Description
   ============== ========= ====== =============================
   project_id     Yes       String Specifies the project ID.
   nat_gateway_id Yes       String Specifies the NAT gateway ID.
   key            Yes       String Specifies the tag key.
   ============== ========= ====== =============================

Request
-------

None

Response
--------

None

Examples
--------

-  Example request

   .. code-block:: text

      DELETE https://{VPC_endpoint}/v2.0/9ad601814ac94c80bf7bb9073ded66fc/nat_gateways/fe1a4cf0-27fe-4b97-a9b1-2c67c127f0e0/tags/key1

-  Example response

   .. code-block::

      None (STATUS CODE 204)

Status Code
-----------

See :ref:`Status Codes <nat_api_0038>`.
