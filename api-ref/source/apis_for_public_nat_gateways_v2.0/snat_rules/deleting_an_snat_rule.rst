:original_name: nat_api_0009.html

.. _nat_api_0009:

Deleting an SNAT Rule
=====================

Function
--------

This API is used to delete an SNAT rule.

URI
---

DELETE /v2.0/snat_rules/{snat_rule_id}

.. table:: **Table 1** Parameter description

   ============ ========= ====== ===========================
   Parameter    Mandatory Type   Description
   ============ ========= ====== ===========================
   snat_rule_id Yes       String Specifies the SNAT rule ID.
   ============ ========= ====== ===========================

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

      DELETE https://{Endpoint}/v2.0/snat_rules/a78fb3eb-1654-4710-8742-3fc49d5f04f8

-  Example response

   .. code-block::

      None (STATUS CODE 204)

Status Code
-----------

See :ref:`Status Codes <nat_api_0038>`.
