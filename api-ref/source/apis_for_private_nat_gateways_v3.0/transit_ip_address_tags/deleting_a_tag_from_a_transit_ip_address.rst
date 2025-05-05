:original_name: DeleteTransitIpTag.html

.. _DeleteTransitIpTag:

Deleting a Tag from a Transit IP Address
========================================

Function
--------

-  This API is idempotent.

-  When a tag is deleted, the tag character set is not verified. Before calling this API, perform the encodeURI operation. The server must perform decodeURI on the API URI. If the key of the tag to be deleted does not exist, 404 will be displayed. The key cannot be left blank or be an empty string.

URI
---

DELETE /v3/{project_id}/transit-ips/{resource_id}/tags/{key}

.. table:: **Table 1** Path Parameters

   =========== ========= ====== ===========================================
   Parameter   Mandatory Type   Description
   =========== ========= ====== ===========================================
   key         Yes       String Specifies the tag key.
   project_id  Yes       String Specifies the project ID.
   resource_id Yes       String Specifies the ID of the transit IP address.
   =========== ========= ====== ===========================================

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

Deleting a tag from a transit IP address

.. code-block:: text

   DELETE  https://{Endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/transit-ips/56121618-fb0a-4a51-aff0-e2eb9cba4c73/tags/key1

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
