:original_name: nat_api_0016.html

.. _nat_api_0016:

Querying NAT Gateways by Tag
============================

Function
--------

This API is used to filter NAT gateways by tag.

TMS uses this API to filter and list NAT gateways by tag.

By default, NAT gateways and tags are sorted in descending order of creation time.

URI
---

-  URI format

POST /v2.0/{project_id}/nat_gateways/resource_instances/action

-  Parameter description

.. table:: **Table 1** Parameter description

   ========== ========= ====== =========================
   Parameter  Mandatory Type   Description
   ========== ========= ====== =========================
   project_id Yes       String Specifies the project ID.
   ========== ========= ====== =========================

Request
-------

:ref:`Table 2 <nat_api_0016__table1215426155818>` describes the request parameters.

.. _nat_api_0016__table1215426155818:

.. table:: **Table 2** Request parameters

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
   +=================+=================+=================+=============================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
   | tags            | No              | Array<Object>   | Specifies the included tags. Each tag contains a maximum of 20 keys, and each key contains a maximum of 10 values. The structure body cannot be missing, and the key cannot be left blank or set to an empty string. Each tag key must be unique, and each tag value in a tag must be unique. Resources identified by different keys are in AND relationship, and values in one tag are in OR relationship. If no tag filtering criteria is specified, full data is returned.                                                               |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags_any        | No              | Array<Object>   | Specifies any included tags. Each tag contains a maximum of 20 keys, and each key contains a maximum of 10 values. The structure body cannot be missing, and the key cannot be left blank or set to an empty string. Each tag key must be unique, and each tag value in a tag must be unique. Resources identified by different keys are in OR relationship, and values in one tag are in OR relationship. If no tag filtering criteria is specified, full data is returned.                                                                |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | not_tags        | No              | Array<Object>   | Specifies the excluded tags. Each tag contains a maximum of 20 keys, and each key contains a maximum of 10 values. The structure body cannot be missing, and the key cannot be left blank or set to an empty string. Each tag key must be unique, and each tag value in a tag must be unique. Resources not identified by different keys are in AND relationship, and values in one tag are in OR relationship. If no tag filtering criteria is specified, full data is returned.                                                           |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | not_tags_any    | No              | Array<Object>   | Specifies any excluded tags. Each tag contains a maximum of 20 keys, and each key contains a maximum of 10 values. The structure body cannot be missing, and the key cannot be left blank or set to an empty string. Each tag key must be unique, and each tag value in a tag must be unique. Resources not identified by different keys are in OR relationship, and values in one tag are in OR relationship. If no tag filtering criteria is specified, full data is returned.                                                            |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit           | No              | String          | Number of records. This parameter is not available when **action** is set to **count**. The default value is **1000** when **action** is set to **filter**. The maximum value is **1000**, and the minimum value is **1**. The value cannot be a negative number.                                                                                                                                                                                                                                                                           |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset          | No              | String          | Specifies the index position. The query starts from the next piece of data indexed by this parameter. This parameter is not required when you query data on the first page. The value in the response returned for querying data on the previous page will be included in this parameter for querying data on subsequent pages. This parameter is not available when **action** is set to **count**. If **action** is set to **filter**, the value must be a number, and the default value is **0**. The value cannot be a negative number. |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | action          | Yes             | String          | Specifies the operation to perform. The value can only be **filter** (filtering) or **count** (querying the total number).                                                                                                                                                                                                                                                                                                                                                                                                                  |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
   |                 |                 |                 | The value **filter** indicates pagination query. The value **count** indicates that the total number of query results meeting the search criteria will be returned. Returning other fields is not allowed.                                                                                                                                                                                                                                                                                                                                  |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | matches         | No              | Array<match>    | Specifies the search criteria. The tag key is the field to match, for example, **resource_name**. The tag value indicates the matched value. This field is a fixed dictionary value.                                                                                                                                                                                                                                                                                                                                                        |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
   |                 |                 |                 | Determine whether fuzzy match is required based on different fields. For example, if **key** is **resource_name**, fuzzy search (case insensitive) is used by default. If **value** is an empty string, exact match is used. If **key** is **resource_id**, exact match is used.                                                                                                                                                                                                                                                            |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 3** Description of field **tag**

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                                          |
   +=================+=================+=================+======================================================================================================================================================================================================================================================================================================+
   | key             | Yes             | String          | Specifies the tag key. A key contains a maximum of 127 Unicode characters and cannot be blank. (The system does not check the parameter when searching a tag.) The key cannot be empty or an empty string, and cannot contain spaces. Before verification, delete spaces before and after the value. |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | values          | Yes             | Array<String>   | Specifies the tag values. Each value contains a maximum of 255 Unicode characters and cannot contain spaces. Before verification, delete spaces before and after the value.                                                                                                                          |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                 | The asterisk (``*``) is a reserved character. The value can be empty but cannot be left blank.                                                                                                                                                                                                       |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                 | If the value starts with an asterisk (``*``), the string following the asterisk is fuzzy matched.                                                                                                                                                                                                    |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                 | If the values are null, it indicates **any_value** (querying any value). The values are in OR relationship.                                                                                                                                                                                          |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 4** Description of field **match**

   +-----------+-----------+--------+------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                  |
   +===========+===========+========+==============================================================================+
   | key       | Yes       | String | Specifies the tag key. The value is fixed at **resource_name**.              |
   +-----------+-----------+--------+------------------------------------------------------------------------------+
   | value     | Yes       | String | Specifies the key value. It can contain a maximum of 255 Unicode characters. |
   +-----------+-----------+--------+------------------------------------------------------------------------------+

Response
--------

:ref:`Table 5 <nat_api_0016__table9270786414>` lists response parameters.

.. _nat_api_0016__table9270786414:

.. table:: **Table 5** Response parameters

   +-------------+-----------------+------------------------------------------------------------------------------------------------------+
   | Parameter   | Type            | Description                                                                                          |
   +=============+=================+======================================================================================================+
   | resources   | Array<resource> | Specifies the resource object list. For details, see :ref:`Table 6 <nat_api_0016__table5281587411>`. |
   +-------------+-----------------+------------------------------------------------------------------------------------------------------+
   | total_count | Integer         | Specifies the total number of resources.                                                             |
   +-------------+-----------------+------------------------------------------------------------------------------------------------------+

.. _nat_api_0016__table5281587411:

.. table:: **Table 6** Data structure description of field **resource**

   +----------------+---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter      | Type                | Description                                                                                                                                             |
   +================+=====================+=========================================================================================================================================================+
   | resource_id    | String              | Specifies the resource ID.                                                                                                                              |
   +----------------+---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | resouce_detail | Object              | Provides details about the resource. The value is a resource object, used for extension. This parameter is left blank by default.                       |
   +----------------+---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags           | Array<resource_tag> | Specifies the list of queried tags. If no tag is matched, an empty array is returned. For details, see :ref:`Table 7 <nat_api_0016__table18303783416>`. |
   +----------------+---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | resource_name  | String              | Specifies the resource name. This parameter is an empty string by default if there is no resource name.                                                 |
   +----------------+---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _nat_api_0016__table18303783416:

.. table:: **Table 7** Parameter description of field **resource_tag**

   +-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                                                                                                                                   |
   +===========+========+===============================================================================================================================================================================================+
   | key       | String | Specifies the tag key. It contains a maximum of 36 Unicode characters. It cannot be left empty or contain ASCII characters (0-31) and the following special characters: \*<>\\=               |
   +-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | value     | String | Specifies the key value. The value can contain a maximum of 43 Unicode characters and can be an empty string. It cannot contain ASCII characters (0-31) and the following characters: \*<>\\= |
   +-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   #. Request body when **action** is set to **filter**

   .. code-block:: text

      POST  https://{VPC_endpoint}/v2.0/9ad601814ac94c80bf7bb9073ded66fc/nat_gateways/resource_instances/action
      {
          "offset": "100",
          "limit": "100",
          "action": "filter",
          "matches": [
              {
                  "key": "resource_name",
                  "value": "nat_gateways"
              }
          ],
          "not_tags": [
              {
                  "key": "key1",
                  "values": [
                      "*value1",
                      "value2"
                  ]
              }
          ],
          "tags": [
              {
                  "key": "key2",
                  "values": [
                      "*value3",
                      "value4"
                  ]
              }
          ],
          "tags_any": [
              {
                  "key": "key3",
                  "values": [
                      "*value5",
                      "value6"
                  ]
              }
          ],
          "not_tags_any": [
              {
                  "key": "key4",
                  "values": [
                      "*value7",
                      "value8"
                  ]
              }
          ]
      }

   2. Request body when **action** is set to **count**

   .. code-block:: text

      POST  https://{VPC_endpoint}/v2.0/9ad601814ac94c80bf7bb9073ded66fc/nat_gateways/resource_instances/action        {
          "action": "count",
          "matches": [
              {
                  "key": "resource_name",
                  "value": "nat_gateways"
              }
          ],
          "not_tags": [
              {
                  "key": "key1",
                  "values": [
                      "*value1",
                      "value2"
                  ]
              }
          ],
          "tags": [
              {
                  "key": "key2",
                  "values": [
                      "*value3",
                      "value4"
                  ]
              }
          ],
          "tags_any": [
              {
                  "key": "key3",
                  "values": [
                      "*value5",
                      "value6"
                  ]
              }
          ],
          "not_tags_any": [
              {
                  "key": "key4",
                  "values": [
                      "*value7",
                      "value8"
                  ]
              }
          ]
      }

-  Example response

   #. Response body when **action** is set to **filter**

   .. code-block::

      {
          "resources": [
              {
                  "resource_detail": null,
                  "resource_id": "e5ad289f-9c56-4daf-b08b-2e53a983473a",
                  "resource_name": "nat_gateways",
                  "tags": [
                      {
                         "key": "key2",
                         "value": "value4"
                      },
                      {
                         "key": "key2",
                         "value": "value3"
                      }
                  ]
              }
          ],
          "total_count": 1000
      }

   2. Response body when **action** is set to **count**

   .. code-block::

      {
          "total_count": 1000
      }

Status Code
-----------

See :ref:`Status Codes <nat_api_0038>`.
