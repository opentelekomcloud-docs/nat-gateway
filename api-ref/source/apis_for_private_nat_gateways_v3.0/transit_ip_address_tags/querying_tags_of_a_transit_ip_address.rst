:original_name: ShowTransitIpTags.html

.. _ShowTransitIpTags:

Querying Tags of a Transit IP Address
=====================================

Function
--------

-  This API is used to query tags of a specified transit IP address.

-  TMS uses this API to query all tags of a specified transit IP address.

URI
---

GET /v3/{project_id}/transit-ips/{resource_id}/tags

.. table:: **Table 1** Path Parameters

   =========== ========= ====== ===========================================
   Parameter   Mandatory Type   Description
   =========== ========= ====== ===========================================
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

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +------------+---------------------------------------------------------------+---------------------------+
   | Parameter  | Type                                                          | Description               |
   +============+===============================================================+===========================+
   | request_id | String                                                        | Specifies the request ID. |
   +------------+---------------------------------------------------------------+---------------------------+
   | tags       | Array of :ref:`Tag <showtransitiptags__response_tag>` objects | Specifies the tags.       |
   +------------+---------------------------------------------------------------+---------------------------+

.. _showtransitiptags__response_tag:

.. table:: **Table 4** Tag

   +-----------+--------+------------------------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                                          |
   +===========+========+======================================================================================================+
   | key       | String | Specifies the tag key. A key can contain up to 128 Unicode characters. **key** cannot be left blank. |
   +-----------+--------+------------------------------------------------------------------------------------------------------+
   | value     | String | Specifies the tag value. Each value can contain up to 255 Unicode characters.                        |
   +-----------+--------+------------------------------------------------------------------------------------------------------+

Example Requests
----------------

.. code-block:: text

   GET  https://{Endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/transit-ips/b0399473-c352-4d0c-8ff4-cfde719cfde9/tags

Example Responses
-----------------

**Status code: 200**

Query operation succeeded.

.. code-block::

   {
     "request_id" : "80ef5f21-b81a-4546-b23d-84272507d330",
     "tags" : [ {
       "key" : "key1",
       "value" : "value1"
     }, {
       "key" : "key2",
       "value" : "value2"
     }, {
       "key" : "key3",
       "value" : "value3"
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
