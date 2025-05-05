:original_name: ListPrivateDnats.html

.. _ListPrivateDnats:

Querying DNAT Rules
===================

Function
--------

This API is used to query DNAT rules.

Constraints
-----------

You can type the question mark (?) and ampersand (&) at the end of the URI to define multiple search criteria.

All optional parameters can be filtered. For details, see the example request.

URI
---

GET /v3/{project_id}/private-nat/dnat-rules

.. table:: **Table 1** Path Parameters

   ========== ========= ====== =========================
   Parameter  Mandatory Type   Description
   ========== ========= ====== =========================
   project_id Yes       String Specifies the project ID.
   ========== ========= ====== =========================

.. table:: **Table 2** Query Parameters

   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory       | Type             | Description                                                                                                                                                      |
   +=======================+=================+==================+==================================================================================================================================================================+
   | limit                 | No              | Integer          | Specifies the number of records displayed on each page.                                                                                                          |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | The value ranges from 1 to 2000.                                                                                                                                 |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | Default value: **2000**                                                                                                                                          |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | **Value range:**                                                                                                                                                 |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | 1-2000                                                                                                                                                           |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | **Default value:**                                                                                                                                               |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | 2000                                                                                                                                                             |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | marker                | No              | String           | Specifies the start resource ID of pagination query. If the parameter is left blank, only resources on the first page are queried.                               |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | The value is obtained from **next_marker** or **previous_marker** in **PageInfo** queried last time.                                                             |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | page_reverse          | No              | Boolean          | Specifies whether to query resources on the previous page.                                                                                                       |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | id                    | No              | Array of strings | Specifies the DNAT rule ID.                                                                                                                                      |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | project_id            | No              | Array of strings | Specifies the project ID.                                                                                                                                        |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id | No              | Array of strings | Specifies the ID of the enterprise project that is associated with the DNAT rule when the DNAT rule is created.                                                  |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description           | No              | Array of strings | Provides supplementary information about the DNAT rule. The description can contain up to 255 characters and cannot contain angle brackets (<>).                 |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | gateway_id            | No              | Array of strings | Specifies the private NAT gateway ID.                                                                                                                            |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | transit_ip_id         | No              | Array of strings | Specifies the ID of the transit IP address.                                                                                                                      |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | external_ip_address   | No              | Array of strings | Specifies the transit IP address.                                                                                                                                |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | network_interface_id  | No              | Array of strings | Specifies the port ID of the resource that the NAT gateway is bound to. The resource can be a compute instance, load balancer (v2 or v3), or virtual IP address. |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | type                  | No              | Array of strings | Specifies the backend resource type of the DNAT rule.                                                                                                            |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | The type can be:                                                                                                                                                 |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | -  **COMPUTE**: The backend resource is a compute instance.                                                                                                      |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | -  **VIP**: The backend resource is a virtual IP address.                                                                                                        |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | -  **ELB**: The backend resource is a v2 load balancer.                                                                                                          |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | -  **ELBv3**: The backend resource is a v3 load balancer.                                                                                                        |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | -  **CUSTOMIZE**: The backend resource is a user-defined IP address.                                                                                             |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | private_ip_address    | No              | Array of strings | Specifies the port IP address that the NAT gateway uses. The resource can be a compute instance, load balancer (v2 or v3), or virtual IP address.                |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | protocol              | No              | Array of strings | Specifies the DNAT rule protocol type.                                                                                                                           |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | TCP, UDP, and ANY are supported.                                                                                                                                 |
   |                       |                 |                  |                                                                                                                                                                  |
   |                       |                 |                  | The protocol number of TCP, UDP, and ANY are 6, 17, and 0, respectively.                                                                                         |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | internal_service_port | No              | Array of strings | Specifies the port number of the resource, which can be a compute instance, load balancer (v2 or v3), or virtual IP address.                                     |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | transit_service_port  | No              | Array of strings | Specifies the port number of the transit IP address.                                                                                                             |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at            | No              | String           | Specifies the time when the DNAT rule was created. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                                                            |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | updated_at            | No              | String           | Specifies the time when the DNAT rule was updated. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                                                            |
   +-----------------------+-----------------+------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 3** Request header parameters

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

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +------------+------------------------------------------------------------------------------+------------------------------------------------------+
   | Parameter  | Type                                                                         | Description                                          |
   +============+==============================================================================+======================================================+
   | dnat_rules | Array of :ref:`PrivateDnat <listprivatednats__response_privatednat>` objects | Specifies the response body for querying DNAT rules. |
   +------------+------------------------------------------------------------------------------+------------------------------------------------------+
   | request_id | String                                                                       | Specifies the request ID.                            |
   +------------+------------------------------------------------------------------------------+------------------------------------------------------+
   | page_info  | :ref:`PageInfo <listprivatednats__response_pageinfo>` object                 | Specifies the pagination information.                |
   +------------+------------------------------------------------------------------------------+------------------------------------------------------+

.. _listprivatednats__response_privatednat:

.. table:: **Table 5** PrivateDnat

   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                       |
   +=======================+=======================+===================================================================================================================================================+
   | id                    | String                | Specifies the DNAT rule ID.                                                                                                                       |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | project_id            | String                | Specifies the project ID.                                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | description           | String                | Provides supplementary information about the DNAT rule. The description can contain up to 255 characters and cannot contain angle brackets (<>).  |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | transit_ip_id         | String                | Specifies the ID of the transit IP address.                                                                                                       |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | gateway_id            | String                | Specifies the private NAT gateway ID.                                                                                                             |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | network_interface_id  | String                | Specifies the network interface ID. Network interfaces of a compute instance, load balancer (v2 or v3), or virtual IP address are supported.      |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | type                  | String                | Specifies the backend resource type of the DNAT rule.                                                                                             |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | The type can be:                                                                                                                                  |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | -  **COMPUTE**: The backend resource is a compute instance.                                                                                       |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | -  **VIP**: The backend resource is a virtual IP address.                                                                                         |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | -  **ELB**: The backend resource is a v2 load balancer.                                                                                           |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | -  **ELBv3**: The backend resource is a v3 load balancer.                                                                                         |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | -  **CUSTOMIZE**: The backend resource is a user-defined IP address.                                                                              |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | protocol              | String                | Specifies the protocol type.                                                                                                                      |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | TCP, UDP, and ANY are supported.                                                                                                                  |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | The protocol number of TCP, UDP, and ANY are 6, 17, and 0, respectively.                                                                          |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | Enumeration values:                                                                                                                               |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | -  **tcp**                                                                                                                                        |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | -  **udp**                                                                                                                                        |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | -  **any**                                                                                                                                        |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | private_ip_address    | String                | Specifies the port IP address that the NAT gateway uses. The resource can be a compute instance, load balancer (v2 or v3), or virtual IP address. |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | internal_service_port | String                | Specifies the port number of the resource, which can be a compute instance, load balancer (v2 or v3), or virtual IP address.                      |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | **Value range:**                                                                                                                                  |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | 0-65535                                                                                                                                           |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | **Default value:**                                                                                                                                |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | 0                                                                                                                                                 |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | transit_service_port  | String                | Specifies the port number of the transit IP address.                                                                                              |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | **Value range:**                                                                                                                                  |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | 0-65535                                                                                                                                           |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | **Default value:**                                                                                                                                |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | 0                                                                                                                                                 |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id | String                | Specifies the ID of the enterprise project that is associated with the DNAT rule when the DNAT rule is created.                                   |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at            | String                | Specifies the time when the DNAT rule was created. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                                             |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | updated_at            | String                | Specifies the time when the DNAT rule was updated. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                                             |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | Specifies the DNAT rule status of a private NAT gateway.                                                                                          |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | The value can be:                                                                                                                                 |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | -  **ACTIVE**: The DNAT rule is running properly.                                                                                                 |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | -  **FROZEN**: The DNAT rule is frozen.                                                                                                           |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | Enumeration values:                                                                                                                               |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | -  **ACTIVE**                                                                                                                                     |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | -  **FROZEN**                                                                                                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+

.. _listprivatednats__response_pageinfo:

.. table:: **Table 6** PageInfo

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                                             |
   +=======================+=======================+=========================================================================================================================================================================================+
   | next_marker           | String                | Specifies the ID of the last record in this query, which can be used in the next query.                                                                                                 |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | previous_marker       | String                | Specifies the ID of the first record in the pagination query result. When **page_reverse** is set to **true**, this parameter is used together to query resources on the previous page. |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | current_count         | Integer               | Specifies the ID of the last record in the pagination query result. It is usually used to query resources on the next page.                                                             |
   |                       |                       |                                                                                                                                                                                         |
   |                       |                       | **Value range:**                                                                                                                                                                        |
   |                       |                       |                                                                                                                                                                                         |
   |                       |                       | 1-2000                                                                                                                                                                                  |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

.. code-block:: text

   GET https://{Endpoint}/v3/da261828016849188f4dcc2ef94d9da9/private-nat/dnat-rules

Example Responses
-----------------

**Status code: 200**

DNAT rules queried.

.. code-block::

   {
     "dnat_rules" : [ {
       "id" : "24dd6bf5-48f2-4915-ad0b-5bb111d39c83",
       "project_id" : "da261828016849188f4dcc2ef94d9da9",
       "description" : "aa",
       "gateway_id" : "0adefb29-a6c2-48a5-8637-2be67fa03fec",
       "transit_ip_id" : "3faa719d-6d18-4ccb-a5c7-33e65a09663e",
       "enterprise_project_id" : "2759da7b-8015-404c-ae0a-a389007b0e2a",
       "network_interface_id" : "dae9393a-b536-491c-a5a2-72edc1104707",
       "type" : "COMPUTE",
       "protocol" : "any",
       "internal_service_port" : "0",
       "transit_service_port" : "0",
       "private_ip_address" : "192.168.1.72",
       "created_at" : "2019-04-29T07:10:01",
       "updated_at" : "2019-04-29T07:10:01",
       "status" : "ACTIVE"
     }, {
       "id" : "25dcdb21-97de-43cd-b476-31637a47f05d",
       "project_id" : "da261828016849188f4dcc2ef94d9da9",
       "description" : "aa",
       "gateway_id" : "0adefb29-a6c2-48a5-8637-2be67fa03fec",
       "transit_ip_id" : "15abdf29-4a68-474c-9963-79c4e6d495d7",
       "enterprise_project_id" : "2759da7b-8015-404c-ae0a-a389007b0e2a",
       "network_interface_id" : "9e2f0dbb-68b2-4c4b-9298-fa4f13187976",
       "type" : "COMPUTE",
       "protocol" : "any",
       "internal_service_port" : "0",
       "transit_service_port" : "0",
       "private_ip_address" : "192.168.1.99",
       "created_at" : "2019-04-29T07:15:41",
       "updated_at" : "2019-04-29T07:15:41",
       "status" : "ACTIVE"
     } ],
     "request_id" : "a7b00469-5a31-4274-bb10-59167243383e",
     "page_info" : {
       "previous_marker" : "14338426-6afe-4019-996b-018008113013",
       "current_count" : 2
     }
   }

Status Codes
------------

=========== ===================
Status Code Description
=========== ===================
200         DNAT rules queried.
=========== ===================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
