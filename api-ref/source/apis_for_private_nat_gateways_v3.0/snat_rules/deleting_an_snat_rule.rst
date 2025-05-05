:original_name: DeletePrivateSnat.html

.. _DeletePrivateSnat:

Deleting an SNAT Rule
=====================

Function
--------

This API is used to delete a specified SNAT rule.

URI
---

DELETE /v3/{project_id}/private-nat/snat-rules/{snat_rule_id}

.. table:: **Table 1** Path Parameters

   ============ ========= ====== ===========================
   Parameter    Mandatory Type   Description
   ============ ========= ====== ===========================
   project_id   Yes       String Specifies the project ID.
   snat_rule_id Yes       String Specifies the SNAT rule ID.
   ============ ========= ====== ===========================

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                             |
   +=================+=================+=================+=========================================================================================================================+
   | X-Auth-Token    | Yes             | String          | Specifies the user token.                                                                                               |
   |                 |                 |                 |                                                                                                                         |
   |                 |                 |                 | It is a response to the API used to obtain a user token. This API is the only one that does not require authentication. |
   |                 |                 |                 |                                                                                                                         |
   |                 |                 |                 | The value of **X-Subject-Token** in the response header is the token value.                                             |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 204**

SNAT rule deleted.

None

Example Requests
----------------

.. code-block:: text

   DELETE https://{Endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/private-nat/snat-rules/8a522ff9-8158-494b-83cd-533b045700e6

Example Responses
-----------------

None

Status Codes
------------

=========== ==================
Status Code Description
=========== ==================
204         SNAT rule deleted.
=========== ==================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
