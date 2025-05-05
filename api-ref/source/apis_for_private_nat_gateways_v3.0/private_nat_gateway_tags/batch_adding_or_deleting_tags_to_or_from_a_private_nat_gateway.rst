:original_name: BatchCreateDeletePrivateNatTags.html

.. _BatchCreateDeletePrivateNatTags:

Batch Adding or Deleting Tags to or from a Private NAT Gateway
==============================================================

Function
--------

-  This API is used to batch add or delete tags to or from a private NAT gateway.

-  TMS uses this API to batch manage tags of a private NAT gateway.

-  A private NAT gateway can have up to 20 tags.

Constraints
-----------

This API is idempotent.

-  If the request body contains duplicate keys, an error is reported.

-  During tag creation, duplicate keys are not allowed. If a key already exists in the database, its value will be overwritten by the new duplicate key.

-  During tag deletion, if some tags to be deleted do not exist, the operation is considered to be successful by default. The character set of the tags will not be verified.

-  The tags structure cannot be missing during deletion. The key cannot be left blank or be an empty string.

URI
---

POST /v3/{project_id}/private-nat-gateways/{resource_id}/tags/action

.. table:: **Table 1** Path Parameters

   =========== ========= ====== =====================================
   Parameter   Mandatory Type   Description
   =========== ========= ====== =====================================
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

.. table:: **Table 3** Request body parameters

   +-----------------+-----------------+----------------------------------------------------------------------------+----------------------------------------+
   | Parameter       | Mandatory       | Type                                                                       | Description                            |
   +=================+=================+============================================================================+========================================+
   | action          | Yes             | String                                                                     | Specifies the operation.               |
   |                 |                 |                                                                            |                                        |
   |                 |                 |                                                                            | The value can be one of the following: |
   |                 |                 |                                                                            |                                        |
   |                 |                 |                                                                            | -  **create**                          |
   |                 |                 |                                                                            |                                        |
   |                 |                 |                                                                            | -  **delete**                          |
   |                 |                 |                                                                            |                                        |
   |                 |                 |                                                                            | Enumeration values:                    |
   |                 |                 |                                                                            |                                        |
   |                 |                 |                                                                            | -  **create**                          |
   |                 |                 |                                                                            |                                        |
   |                 |                 |                                                                            | -  **delete**                          |
   +-----------------+-----------------+----------------------------------------------------------------------------+----------------------------------------+
   | tags            | Yes             | Array of :ref:`Tag <batchcreatedeleteprivatenattags__request_tag>` objects | Specifies the tag list.                |
   +-----------------+-----------------+----------------------------------------------------------------------------+----------------------------------------+

.. _batchcreatedeleteprivatenattags__request_tag:

.. table:: **Table 4** Tag

   +-----------+-----------+--------+------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                          |
   +===========+===========+========+======================================================================================================+
   | key       | Yes       | String | Specifies the tag key. A key can contain up to 128 Unicode characters. **key** cannot be left blank. |
   +-----------+-----------+--------+------------------------------------------------------------------------------------------------------+
   | value     | Yes       | String | Specifies the tag value. Each value can contain up to 255 Unicode characters.                        |
   +-----------+-----------+--------+------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 204**

Tags added or deleted.

None

Example Requests
----------------

-  Adding tags to a private NAT gateway (Setting **action** to **create** and adding the following two tags: **key1**, **value1** and **key2**, **value2**)

   .. code-block:: text

      POST  https://{Endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/private-nat-gateways/3320166e-b937-40cc-a35c-02cd3f2b3ee2/tags/action

      {
        "action" : "create",
        "tags" : [ {
          "key" : "key1",
          "value" : "value1"
        }, {
          "key" : "key2",
          "value" : "value2"
        } ]
      }

-  Deleting tags from a private NAT gateway (Setting **action** to **delete** and deleting the following two tags: **key1**, **value1** and **key2**, **value2**)

   .. code-block:: text

      POST  https://{Endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/private-nat-gateways/3320166e-b937-40cc-a35c-02cd3f2b3ee2/tags/action

      {
        "action" : "delete",
        "tags" : [ {
          "key" : "key1",
          "value" : "value1"
        }, {
          "key" : "key2",
          "value" : "value2"
        } ]
      }

Example Responses
-----------------

None

Status Codes
------------

=========== ======================
Status Code Description
=========== ======================
204         Tags added or deleted.
=========== ======================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
