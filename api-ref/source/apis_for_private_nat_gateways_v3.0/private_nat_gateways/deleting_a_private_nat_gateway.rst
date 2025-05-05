:original_name: DeletePrivateNat.html

.. _DeletePrivateNat:

Deleting a Private NAT Gateway
==============================

Function
--------

This API is used to delete a private NAT gateway.

URI
---

DELETE /v3/{project_id}/private-nat/gateways/{gateway_id}

.. table:: **Table 1** Path Parameters

   ========== ========= ====== =====================================
   Parameter  Mandatory Type   Description
   ========== ========= ====== =====================================
   gateway_id Yes       String Specifies the private NAT gateway ID.
   project_id Yes       String Specifies the project ID.
   ========== ========= ====== =====================================

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

Private NAT gateway deleted.

None

Example Requests
----------------

.. code-block:: text

   DELETE https://{Endpoint}/v3/70505c941b9b4dfd82fd351932328a2f/private-nat/gateways/14338426-6afe-4019-996b-3a9525296e11

Example Responses
-----------------

None

Status Codes
------------

=========== ============================
Status Code Description
=========== ============================
204         Private NAT gateway deleted.
=========== ============================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
