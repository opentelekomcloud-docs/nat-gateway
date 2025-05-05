:original_name: ShowTransitIp.html

.. _ShowTransitIp:

Querying Details About a Specified Transit IP Address
=====================================================

Function
--------

This API is used to query details about a specified transit IP address.

URI
---

GET /v3/{project_id}/private-nat/transit-ips/{transit_ip_id}

.. table:: **Table 1** Path Parameters

   +---------------+-----------+--------+---------------------------------------------+
   | Parameter     | Mandatory | Type   | Description                                 |
   +===============+===========+========+=============================================+
   | project_id    | Yes       | String | Specifies the project ID.                   |
   +---------------+-----------+--------+---------------------------------------------+
   | transit_ip_id | Yes       | String | Specifies the ID of the transit IP address. |
   +---------------+-----------+--------+---------------------------------------------+

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

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +------------+-------------------------------------------------------------+--------------------------------------------------------+
   | Parameter  | Type                                                        | Description                                            |
   +============+=============================================================+========================================================+
   | transit_ip | :ref:`TransitIp <showtransitip__response_transitip>` object | Specifies the response body of the transit IP address. |
   +------------+-------------------------------------------------------------+--------------------------------------------------------+
   | request_id | String                                                      | Specifies the request ID.                              |
   +------------+-------------------------------------------------------------+--------------------------------------------------------+

.. _showtransitip__response_transitip:

.. table:: **Table 4** TransitIp

   +-----------------------+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                                      | Description                                                                                                                              |
   +=======================+===========================================================+==========================================================================================================================================+
   | id                    | String                                                    | Specifies the ID of the transit IP address.                                                                                              |
   +-----------------------+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | project_id            | String                                                    | Specifies the project ID.                                                                                                                |
   +-----------------------+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | network_interface_id  | String                                                    | Specifies the network interface ID of the transit IP address.                                                                            |
   +-----------------------+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | ip_address            | String                                                    | Specifies the transit IP address.                                                                                                        |
   +-----------------------+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at            | String                                                    | Specifies the time when the transit IP address was assigned. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                          |
   +-----------------------+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | updated_at            | String                                                    | Specifies the time when the transit IP address was updated. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                           |
   +-----------------------+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | virsubnet_id          | String                                                    | Specifies the subnet ID of the current tenant.                                                                                           |
   |                       |                                                           |                                                                                                                                          |
   |                       |                                                           | Constraint: Either this parameter or **transit_subnet_id** must be specified. The default value is an empty string.                      |
   +-----------------------+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | tags                  | Array of :ref:`Tag <showtransitip__response_tag>` objects | Specifies the list of tags.                                                                                                              |
   +-----------------------+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | gateway_id            | String                                                    | Specifies the ID of the private NAT gateway associated with the transit IP address.                                                      |
   +-----------------------+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id | String                                                    | Specifies the ID of the enterprise project that is associated with the transit IP address when the transit IP address is being assigned. |
   +-----------------------+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                                                    | Specifies the transit IP address status.                                                                                                 |
   |                       |                                                           |                                                                                                                                          |
   |                       |                                                           | The value can be:                                                                                                                        |
   |                       |                                                           |                                                                                                                                          |
   |                       |                                                           | -  **ACTIVE**: The transit IP address is running properly.                                                                               |
   |                       |                                                           |                                                                                                                                          |
   |                       |                                                           | -  **FROZEN**: The transit IP address is frozen.                                                                                         |
   |                       |                                                           |                                                                                                                                          |
   |                       |                                                           | Enumeration values:                                                                                                                      |
   |                       |                                                           |                                                                                                                                          |
   |                       |                                                           | -  **ACTIVE**                                                                                                                            |
   |                       |                                                           |                                                                                                                                          |
   |                       |                                                           | -  **FROZEN**                                                                                                                            |
   +-----------------------+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+

.. _showtransitip__response_tag:

.. table:: **Table 5** Tag

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

   GET https://{Endpoint}/v3/da261828016849188f4dcc2ef94d9da9/private-nat/transit-ips/a2845109-3b2f-4627-b08f-09a726c0a6e7

Example Responses
-----------------

**Status code: 200**

Details about a specified transit IP address queried.

.. code-block::

   {
     "transit_ip" : {
       "id" : "a2845109-3b2f-4627-b08f-09a726c0a6e7",
       "project_id" : "da261828016849188f4dcc2ef94d9da9",
       "network_interface_id" : "adebbdca-8c26-4c14-b34f-3f53cd2c42f2",
       "ip_address" : "192.168.1.68",
       "gateway_id" : "521bb3d9-8bed-4c6c-9ee8-669bd0620f76",
       "enterprise_project_id" : "2759da7b-8015-404c-ae0a-a389007b0e2a",
       "created_at" : "2019-04-29T02:16:09",
       "updated_at" : "2019-04-29T02:16:09",
       "virsubnet_id" : "49ee5fb5-75bf-4320-946e-b21ef4c9c9c1",
       "status" : "ACTIVE",
       "tags" : [ {
         "key" : "key1",
         "value" : "value1"
       } ]
     },
     "request_id" : "747a911c17067a39692f75ac146fb47e"
   }

Status Codes
------------

=========== =====================================================
Status Code Description
=========== =====================================================
200         Details about a specified transit IP address queried.
=========== =====================================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
