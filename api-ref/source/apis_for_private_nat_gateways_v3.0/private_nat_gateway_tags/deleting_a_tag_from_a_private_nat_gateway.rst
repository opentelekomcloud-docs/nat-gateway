:original_name: DeletePrivateNatTag.html

.. _DeletePrivateNatTag:

Deleting a Tag from a Private NAT Gateway
=========================================

Function
--------

-  This API is idempotent.

-  When a tag is deleted, the tag character set is not verified. Before calling this API, perform the encodeURI operation. The server must perform decodeURI on the API URI. If the key of the tag to be deleted does not exist, 404 will be displayed. The key cannot be left blank or be an empty string.

URI
---

DELETE /v3/{project_id}/private-nat-gateways/{resource_id}/tags/{key}

.. table:: **Table 1** Path Parameters

   =========== ========= ====== =====================================
   Parameter   Mandatory Type   Description
   =========== ========= ====== =====================================
   key         Yes       String Specifies the tag key.
   project_id  Yes       String Specifies the project ID.
   resource_id Yes       String Specifies the private NAT gateway ID.
   =========== ========= ====== =====================================

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                            |
   +=================+=================+=================+========================================================================================================================+
   | X-Auth-Token    | Yes             | String          | Specifies the user token.                                                                                              |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | It is a response to the API for obtaining a user token. This API is the only one that does not require authentication. |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | The value of **X-Subject-Token** in the response header is the token value.                                            |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 204**

Tag deleted.

None

Example Requests
----------------

This API is used to delete a tag from a private NAT gateway.

.. code-block:: text

   DELETE  https://{Endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/private-nat-gateways/3320166e-b937-40cc-a35c-02cd3f2b3ee2/tags/key1

Example Responses
-----------------

None

Status Codes
------------

=========== ============
Status Code Description
=========== ============
204         Tag deleted.
=========== ============

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
