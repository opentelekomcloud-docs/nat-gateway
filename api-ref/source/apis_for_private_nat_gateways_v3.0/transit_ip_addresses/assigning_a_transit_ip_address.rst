:original_name: CreateTransitIp.html

.. _CreateTransitIp:

Assigning a Transit IP Address
==============================

Function
--------

This API is used to assign a transit IP address.

URI
---

POST /v3/{project_id}/private-nat/transit-ips

.. table:: **Table 1** Path Parameters

   ========== ========= ====== =========================
   Parameter  Mandatory Type   Description
   ========== ========= ====== =========================
   project_id Yes       String Specifies the project ID.
   ========== ========= ====== =========================

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

.. table:: **Table 3** Request body parameters

   +------------+-----------+------------------------------------------------------------------------------------+----------------------------------------------------------------+
   | Parameter  | Mandatory | Type                                                                               | Description                                                    |
   +============+===========+====================================================================================+================================================================+
   | transit_ip | Yes       | :ref:`CreatTransitIpOption <createtransitip__request_creattransitipoption>` object | Specifies the request body for assigning a transit IP address. |
   +------------+-----------+------------------------------------------------------------------------------------+----------------------------------------------------------------+

.. _createtransitip__request_creattransitipoption:

.. table:: **Table 4** CreatTransitIpOption

   +-----------------------+-----------------+------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory       | Type                                                       | Description                                                                                                                              |
   +=======================+=================+============================================================+==========================================================================================================================================+
   | virsubnet_id          | Yes             | String                                                     | Specifies the subnet ID of the current project.                                                                                          |
   +-----------------------+-----------------+------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | ip_address            | No              | String                                                     | Specifies the transit IP address.                                                                                                        |
   +-----------------------+-----------------+------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id | No              | String                                                     | Specifies the ID of the enterprise project that is associated with the transit IP address when the transit IP address is being assigned. |
   |                       |                 |                                                            |                                                                                                                                          |
   |                       |                 |                                                            | **Default value:**                                                                                                                       |
   |                       |                 |                                                            |                                                                                                                                          |
   |                       |                 |                                                            | 0                                                                                                                                        |
   +-----------------------+-----------------+------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | tags                  | No              | Array of :ref:`Tag <createtransitip__request_tag>` objects | Specifies the tag of the transit IP address.                                                                                             |
   +-----------------------+-----------------+------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+

.. _createtransitip__request_tag:

.. table:: **Table 5** Tag

   +-----------+-----------+--------+------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                          |
   +===========+===========+========+======================================================================================================+
   | key       | Yes       | String | Specifies the tag key. A key can contain up to 128 Unicode characters. **key** cannot be left blank. |
   +-----------+-----------+--------+------------------------------------------------------------------------------------------------------+
   | value     | Yes       | String | Specifies the tag value. Each value can contain up to 255 Unicode characters.                        |
   +-----------+-----------+--------+------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 201**

.. table:: **Table 6** Response body parameters

   +------------+---------------------------------------------------------------+--------------------------------------------------------+
   | Parameter  | Type                                                          | Description                                            |
   +============+===============================================================+========================================================+
   | transit_ip | :ref:`TransitIp <createtransitip__response_transitip>` object | Specifies the response body of the transit IP address. |
   +------------+---------------------------------------------------------------+--------------------------------------------------------+
   | request_id | String                                                        | Specifies the request ID.                              |
   +------------+---------------------------------------------------------------+--------------------------------------------------------+

.. _createtransitip__response_transitip:

.. table:: **Table 7** TransitIp

   +-----------------------+-------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                                        | Description                                                                                                                              |
   +=======================+=============================================================+==========================================================================================================================================+
   | id                    | String                                                      | Specifies the ID of the transit IP address.                                                                                              |
   +-----------------------+-------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | project_id            | String                                                      | Specifies the project ID.                                                                                                                |
   +-----------------------+-------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | network_interface_id  | String                                                      | Specifies the network interface ID of the transit IP address.                                                                            |
   +-----------------------+-------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | ip_address            | String                                                      | Specifies the transit IP address.                                                                                                        |
   +-----------------------+-------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at            | String                                                      | Specifies the time when the transit IP address was assigned. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                          |
   +-----------------------+-------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | updated_at            | String                                                      | Specifies the time when the transit IP address was updated. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                           |
   +-----------------------+-------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | virsubnet_id          | String                                                      | Specifies the subnet ID of the current tenant.                                                                                           |
   |                       |                                                             |                                                                                                                                          |
   |                       |                                                             | Constraint: Either this parameter or **transit_subnet_id** must be specified. The default value is an empty string.                      |
   +-----------------------+-------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | tags                  | Array of :ref:`Tag <createtransitip__response_tag>` objects | Specifies the list of tags.                                                                                                              |
   +-----------------------+-------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | gateway_id            | String                                                      | Specifies the ID of the private NAT gateway associated with the transit IP address.                                                      |
   +-----------------------+-------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id | String                                                      | Specifies the ID of the enterprise project that is associated with the transit IP address when the transit IP address is being assigned. |
   +-----------------------+-------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                                                      | Specifies the transit IP address status.                                                                                                 |
   |                       |                                                             |                                                                                                                                          |
   |                       |                                                             | The value can be:                                                                                                                        |
   |                       |                                                             |                                                                                                                                          |
   |                       |                                                             | -  **ACTIVE**: The transit IP address is running properly.                                                                               |
   |                       |                                                             |                                                                                                                                          |
   |                       |                                                             | -  **FROZEN**: The transit IP address is frozen.                                                                                         |
   |                       |                                                             |                                                                                                                                          |
   |                       |                                                             | Enumeration values:                                                                                                                      |
   |                       |                                                             |                                                                                                                                          |
   |                       |                                                             | -  **ACTIVE**                                                                                                                            |
   |                       |                                                             |                                                                                                                                          |
   |                       |                                                             | -  **FROZEN**                                                                                                                            |
   +-----------------------+-------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+

.. _createtransitip__response_tag:

.. table:: **Table 8** Tag

   +-----------+--------+------------------------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                                          |
   +===========+========+======================================================================================================+
   | key       | String | Specifies the tag key. A key can contain up to 128 Unicode characters. **key** cannot be left blank. |
   +-----------+--------+------------------------------------------------------------------------------------------------------+
   | value     | String | Specifies the tag value. Each value can contain up to 255 Unicode characters.                        |
   +-----------+--------+------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Assigning a transit IP address (Setting **virsubnet_id** to **2759da7b-8015-404c-ae0a-a389007b0e2a**, **ip_address** to **192.168.1.68**, and **enterprise_project_id** to **2759da7b-8015-404c-ae0a-a389007b0e2a**)

.. code-block:: text

   POST https://{Endpoint}/v3/da261828016849188f4dcc2ef94d9da9/private-nat/transit-ips

   {
     "transit_ip" : {
       "virsubnet_id" : "2759da7b-8015-404c-ae0a-a389007b0e2a",
       "enterprise_project_id" : "2759da7b-8015-404c-ae0a-a389007b0e2a",
       "ip_address" : "192.168.1.68",
       "tags" : [ {
         "key" : "key1",
         "value" : "value1"
       } ]
     }
   }

Example Responses
-----------------

**Status code: 201**

Transit IP address assigned.

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
       "virsubnet_id" : "2759da7b-8015-404c-ae0a-a389007b0e2a",
       "tags" : [ {
         "key" : "key1",
         "value" : "value1"
       } ],
       "status" : "ACTIVE"
     },
     "request_id" : "747a911c17067a39692f75ac146fb47e"
   }

Status Codes
------------

=========== ============================
Status Code Description
=========== ============================
201         Transit IP address assigned.
=========== ============================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
