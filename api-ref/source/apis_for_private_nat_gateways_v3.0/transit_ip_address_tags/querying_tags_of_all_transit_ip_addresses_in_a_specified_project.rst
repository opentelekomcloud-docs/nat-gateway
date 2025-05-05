:original_name: ListTransitIpTags.html

.. _ListTransitIpTags:

Querying Tags of All Transit IP Addresses in a Specified Project
================================================================

Function
--------

-  This API is used to query tags of all transit IP addresses owned by a tenant in a project.

-  TMS uses this API to list tags of all transit IP addresses owned by a tenant. TMS also provides tag association when users tag or filter transit IP addresses.

URI
---

GET /v3/{project_id}/transit-ips/tags

.. table:: **Table 1** Path Parameters

   ========== ========= ====== =========================
   Parameter  Mandatory Type   Description
   ========== ========= ====== =========================
   project_id Yes       String Specifies the project ID.
   ========== ========= ====== =========================

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

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +------------+-----------------------------------------------------------------+---------------------------+
   | Parameter  | Type                                                            | Description               |
   +============+=================================================================+===========================+
   | request_id | String                                                          | Specifies the request ID. |
   +------------+-----------------------------------------------------------------+---------------------------+
   | tags       | Array of :ref:`Tags <listtransitiptags__response_tags>` objects | Specifies the tags.       |
   +------------+-----------------------------------------------------------------+---------------------------+

.. _listtransitiptags__response_tags:

.. table:: **Table 4** Tags

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                                                                                                                                                               |
   +=======================+=======================+===========================================================================================================================================================================================================================================================================================================+
   | key                   | String                | Specifies the tag key. A key can contain up to 128 Unicode characters. (The system does not verify **key** when searching for resources.) **key** cannot be left blank or be an empty string. **key** cannot contain spaces. Before using the value of **key**, delete spaces before and after the value. |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | values                | Array of strings      | Specifies the tag value list. Each value can contain a maximum of 255 Unicode characters. Before verifying and using **values**, delete SBC spaces before and after the value.                                                                                                                            |
   |                       |                       |                                                                                                                                                                                                                                                                                                           |
   |                       |                       | The value can be an empty array but cannot be left blank. If **values** is not specified, any parameter value can be queried.                                                                                                                                                                             |
   |                       |                       |                                                                                                                                                                                                                                                                                                           |
   |                       |                       | The values are in the OR relationship. The system verifies the length, but not verifies the character set of **values** when searching for resources.                                                                                                                                                     |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

.. code-block:: text

   GET  https://{Endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/transit-ips/tags

Example Responses
-----------------

**Status code: 200**

Query operation succeeded.

.. code-block::

   {
     "request_id" : "36479272a29de0be0a8a8b294c02ab7a",
     "tags" : [ {
       "key" : "keys",
       "values" : [ "value" ]
     }, {
       "key" : "key3",
       "values" : [ "value3" ]
     }, {
       "key" : "key1",
       "values" : [ "value1" ]
     }, {
       "key" : "key2",
       "values" : [ "value2" ]
     } ]
   }

Status Codes
------------

=========== ==========================
Status Code Description
=========== ==========================
200         Query operation succeeded.
=========== ==========================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
