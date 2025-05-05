:original_name: DeletePrivateDnat.html

.. _DeletePrivateDnat:

Deleting a DNAT Rule
====================

Function
--------

This API is used to delete a specified DNAT rule.

URI
---

DELETE /v3/{project_id}/private-nat/dnat-rules/{dnat_rule_id}

.. table:: **Table 1** Path Parameters

   ============ ========= ====== ===========================
   Parameter    Mandatory Type   Description
   ============ ========= ====== ===========================
   project_id   Yes       String Specifies the project ID.
   dnat_rule_id Yes       String Specifies the DNAT rule ID.
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

DNAT rule deleted.

None

Example Requests
----------------

.. code-block:: text

   DELETE  https://{Endpoint}/v3/da261828016849188f4dcc2ef94d9da9/private-nat/dnat-rules/24dd6bf5-48f2-4915-ad0b-5bb111d39c83

Example Responses
-----------------

None

Status Codes
------------

=========== ==================
Status Code Description
=========== ==================
204         DNAT rule deleted.
=========== ==================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
