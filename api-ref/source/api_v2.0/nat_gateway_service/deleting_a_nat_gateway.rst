:original_name: nat_api_0004.html

.. _nat_api_0004:

Deleting a NAT Gateway
======================

Function
--------

This API is used to delete a NAT gateway.

URI
---

DELETE /v2.0/nat_gateways/{nat_gateway_id}

.. table:: **Table 1** Parameter description

   ============== ========= ====== =============================
   Parameter      Mandatory Type   Description
   ============== ========= ====== =============================
   nat_gateway_id Yes       String Specifies the NAT gateway ID.
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

      DELETE https://{Endpoint}/v2.0/nat_gateways/a78fb3eb-1654-4710-8742-3fc49d5f04f8

-  Example response

   .. code-block::

      None (STATUS CODE 204)

Status Code
-----------

See :ref:`Status Codes <nat_api_0038>`.
