:original_name: CreateTransitIpTag.html

.. _CreateTransitIpTag:

Adding a Tag to a Transit IP Address
====================================

Function
--------

-  This API is used to add a tag to a transit IP address.

-  A transit IP address can have up to 20 tags.

-  This API is idempotent.

-  If a tag to be added has the same key as an existing tag, the tag will be added and overwrite the existing one.

URI
---

POST /v3/{project_id}/transit-ips/{resource_id}/tags

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

.. table:: **Table 3** Request body parameters

   +-----------+-----------+-----------------------------------------------------+--------------------+
   | Parameter | Mandatory | Type                                                | Description        |
   +===========+===========+=====================================================+====================+
   | tag       | Yes       | :ref:`Tag <createtransitiptag__request_tag>` object | Specifies the tag. |
   +-----------+-----------+-----------------------------------------------------+--------------------+

.. _createtransitiptag__request_tag:

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

Tag added.

None

Example Requests
----------------

Adding a tag to a transit IP address (Setting **key** to **key1** and **value** to **value1**)

.. code-block:: text

   POST  https://{Endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/transit-ips/56121618-fb0a-4a51-aff0-e2eb9cba4c73/tags

   {
     "tag" : {
       "key" : "key1",
       "value" : "value1"
     }
   }

Example Responses
-----------------

None

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
204         Tag added.
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
