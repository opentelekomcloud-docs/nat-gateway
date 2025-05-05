:original_name: ListTransitIpsByTags.html

.. _ListTransitIpsByTags:

Querying Transit IP Addresses by Tag
====================================

Function
--------

-  This API is used to query transit IP addresses by tag.

-  TMS uses this API to filter and list transit IP addresses by tag.

URI
---

POST /v3/{project_id}/transit-ips/resource_instances/action

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

.. table:: **Table 3** Request body parameters

   +-----------------+-----------------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type                                                                | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   +=================+=================+=====================================================================+======================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
   | offset          | No              | String                                                              | Specifies the index position. The query starts from the next data record indexed by this parameter. When querying resources on the first page, you do not need to specify this parameter. When querying resources on subsequent pages, set this parameter to the value returned in the response body for querying resources on the previous page. This parameter is not available when **action** is set to **count**. If **action** is set to **filter**, the value must be a positive number, and the default value is **0**.                                                                      |
   +-----------------+-----------------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit           | No              | String                                                              | Specifies the number of records to be queried. This parameter is not available when **action** is set to **count**. If **action** is set to **filter**, the default value is **1000**, which is also the maximum value. The minimum value is **1**. The value cannot be a negative number.                                                                                                                                                                                                                                                                                                           |
   +-----------------+-----------------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | action          | Yes             | String                                                              | Specifies the operation to be performed. The value can be **filter** or **count**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                 |                 |                                                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                     | The value **filter** indicates pagination query. The value **count** indicates that the total number of query results meeting the search criteria will be returned.                                                                                                                                                                                                                                                                                                                                                                                                                                  |
   |                 |                 |                                                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                     | Enumeration values:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
   |                 |                 |                                                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                     | -  **filter**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
   |                 |                 |                                                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                     | -  **count**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
   +-----------------+-----------------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | matches         | No              | Array of :ref:`Match <listtransitipsbytags__request_match>` objects | Specifies the search field. The tag key is the field to be matched, for example, **resource_name**. The tag value indicates the value to be matched. This field is a fixed dictionary value. You can determine whether fuzzy match is required based on different fields. For example, if **key** is set to **resource_name**, fuzzy search (case insensitive) is used by default. If **value** is an empty string, exact match is used. If **key** is set to **resource_id**, exact match is used. Currently, only **resource_name** is supported.                                                  |
   +-----------------+-----------------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | not_tags        | No              | Array of :ref:`Tags <listtransitipsbytags__request_tags>` objects   | The resources to be queried do not contain tags listed in **not_tags**. Each resource to be queried contains a maximum of 20 keys. Each tag key can have a maximum of 20 tag values. The structure body cannot be missing, and the key cannot be left blank or set to an empty string. Each tag key must be unique, and each tag value in a tag must be unique.Resources that do not contain the tags listed in **not_tags** will be returned.Keys are in AND relationship, and values in a tag are in OR relationship.If this parameter is not specified, all resources will be returned.           |
   +-----------------+-----------------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags            | No              | Array of :ref:`Tags <listtransitipsbytags__request_tags>` objects   | The resources to be queried contain tags listed in **tags**. Each resource to be queried contains a maximum of 20 keys. Each tag key can have a maximum of 20 tag values. The structure body cannot be missing, and the key cannot be left blank or set to an empty string. Each tag key must be unique, and each tag value in a tag must be unique.Resources that contain the tags listed in \*\ *tags* will be returned.Keys are in AND relationship, and values in a tag are in OR relationship.If this parameter is not specified, all resources will be returned.                               |
   +-----------------+-----------------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags_any        | No              | Array of :ref:`Tags <listtransitipsbytags__request_tags>` objects   | The resources to be queried contain any tag listed in **tags_any**. Each resource to be queried contains a maximum of 20 keys. Each tag key can have a maximum of 20 tag values. The structure body cannot be missing, and the key cannot be left blank or set to an empty string. Each tag key must be unique, and each tag value in a tag must be unique.Resources that contain any tag listed in \*\ *tags_any* will be returned.Keys are in AND relationship, and values in a tag are in OR relationship.If this parameter is not specified, all resources will be returned.                     |
   +-----------------+-----------------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | not_tags_any    | No              | Array of :ref:`Tags <listtransitipsbytags__request_tags>` objects   | The resources to be queried do not contain any tag listed in **not_tags_any**. Each resource to be queried contains a maximum of 20 keys. Each tag key can have a maximum of 20 tag values. The structure body cannot be missing, and the key cannot be left blank or set to an empty string. Each tag key must be unique, and each tag value in a tag must be unique.Resources that do not contain any tag listed in **not_tags_any** will be returned.Keys are in AND relationship, and values in a tag are in OR relationship.If this parameter is not specified, all resources will be returned. |
   +-----------------+-----------------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _listtransitipsbytags__request_match:

.. table:: **Table 4** Match

   +-----------+-----------+--------+-------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                           |
   +===========+===========+========+=======================================================+
   | key       | Yes       | String | Specifies the tag key used to search for resources.   |
   +-----------+-----------+--------+-------------------------------------------------------+
   | value     | Yes       | String | Specifies the tag value used to search for resources. |
   +-----------+-----------+--------+-------------------------------------------------------+

.. _listtransitipsbytags__request_tags:

.. table:: **Table 5** Tags

   +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type             | Description                                                                                                                                                                                                                                                                                               |
   +=================+=================+==================+===========================================================================================================================================================================================================================================================================================================+
   | key             | Yes             | String           | Specifies the tag key. A key can contain up to 128 Unicode characters. (The system does not verify **key** when searching for resources.) **key** cannot be left blank or be an empty string. **key** cannot contain spaces. Before using the value of **key**, delete spaces before and after the value. |
   +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | values          | Yes             | Array of strings | Specifies the tag value list. Each value can contain a maximum of 255 Unicode characters. Before verifying and using **values**, delete SBC spaces before and after the value.                                                                                                                            |
   |                 |                 |                  |                                                                                                                                                                                                                                                                                                           |
   |                 |                 |                  | The value can be an empty array but cannot be left blank. If **values** is not specified, any parameter value can be queried.                                                                                                                                                                             |
   |                 |                 |                  |                                                                                                                                                                                                                                                                                                           |
   |                 |                 |                  | The values are in the OR relationship. The system verifies the length, but not verifies the character set of **values** when searching for resources.                                                                                                                                                     |
   +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 6** Response body parameters

   +-----------------------+----------------------------------------------------------------------------+----------------------------------------+
   | Parameter             | Type                                                                       | Description                            |
   +=======================+============================================================================+========================================+
   | resources             | Array of :ref:`Resource <listtransitipsbytags__response_resource>` objects | Specifies the resource list.           |
   +-----------------------+----------------------------------------------------------------------------+----------------------------------------+
   | request_id            | String                                                                     | Specifies the request ID.              |
   +-----------------------+----------------------------------------------------------------------------+----------------------------------------+
   | total_count           | Integer                                                                    | Specifies the total number of records. |
   |                       |                                                                            |                                        |
   |                       |                                                                            | **Value range:**                       |
   |                       |                                                                            |                                        |
   |                       |                                                                            | 0-1000000                              |
   +-----------------------+----------------------------------------------------------------------------+----------------------------------------+

.. _listtransitipsbytags__response_resource:

.. table:: **Table 7** Resource

   +-----------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
   | Parameter       | Type                                                                             | Description                                                                                             |
   +=================+==================================================================================+=========================================================================================================+
   | resource_detail | Object                                                                           | Specifies the resource details. This parameter is used for extension and is left blank by default.      |
   +-----------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
   | resource_id     | String                                                                           | Specifies the resource ID.                                                                              |
   +-----------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
   | resource_name   | String                                                                           | Specifies the resource name. This parameter is an empty string by default if there is no resource name. |
   +-----------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
   | resource_tag    | Array of :ref:`ResourceTag <listtransitipsbytags__response_resourcetag>` objects | Specifies the list of queried tags. If no tag is matched, an empty array is returned.                   |
   +-----------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+

.. _listtransitipsbytags__response_resourcetag:

.. table:: **Table 8** ResourceTag

   ========= ====== ========================
   Parameter Type   Description
   ========= ====== ========================
   key       String Specifies the tag key.
   value     String Specifies the tag value.
   ========= ====== ========================

Example Requests
----------------

-  Querying transit IP addresses by tag (Setting **action** to **filter** and **limit** to **1000**)

   .. code-block:: text

      POST  https://{Endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/transit-ips/resource_instances/action

      {
        "offset" : "0",
        "limit" : "1000",
        "action" : "filter",
        "not_tags_any" : [ {
          "key" : "owner",
          "value" : "tag_1_value"
        } ]
      }

-  Querying transit IP addresses by tag (Setting **action** to **count** and adding tags)

   .. code-block:: text

      POST  https://{Endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/transit-ips/resource_instances/action

      {
        "action" : "count",
        "tags" : [ {
          "key" : "key1",
          "values" : [ "value1", "value2" ]
        } ],
        "matches" : [ {
          "key" : "resource_name",
          "value" : "resource1"
        } ]
      }

Example Responses
-----------------

**Status code: 200**

Query operation succeeded.

-  Example 1: the response body when **action** is set to **filter**

-  Example 2: the response body when **action** is set to **count**

-  Example 1

   .. code-block::

      {
        "resources" : [ {
          "resource_detail" : null,
          "resource_id" : "ae33be9b-d2c0-441b-a8d0-f6dafedf1778",
          "resource_name" : "transit_ips",
          "tags" : [ {
            "key" : "key1",
            "value" : "value1"
          }, {
            "key" : "key2",
            "value" : "value1"
          } ]
        } ],
        "request_id" : "9e47d9476cfd346f864cb77acb274185",
        "total_count" : 1
      }

-  Example 2

   .. code-block::

      {
        "request_id" : "d70aabc854d3d301f9bb106e6b70ac99",
        "total_count" : 100
      }

Status Codes
------------

+-----------------------------------+----------------------------------------------------------------------+
| Status Code                       | Description                                                          |
+===================================+======================================================================+
| 200                               | Query operation succeeded.                                           |
|                                   |                                                                      |
|                                   | -  Example 1: the response body when **action** is set to **filter** |
|                                   |                                                                      |
|                                   | -  Example 2: the response body when **action** is set to **count**  |
+-----------------------------------+----------------------------------------------------------------------+

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
