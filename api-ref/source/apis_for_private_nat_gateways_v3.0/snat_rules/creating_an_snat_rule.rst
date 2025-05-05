:original_name: CreatePrivateSnat.html

.. _CreatePrivateSnat:

Creating an SNAT Rule
=====================

Function
--------

This API is used to create an SNAT rule.

Constraints
-----------

When you are creating an SNAT rule, status of the NAT gateway must be set to **ACTIVE**.

URI
---

POST /v3/{project_id}/private-nat/snat-rules

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

   +-----------+-----------+--------------------------------------------------------------------------------------------+-------------------------------------------------------+
   | Parameter | Mandatory | Type                                                                                       | Description                                           |
   +===========+===========+============================================================================================+=======================================================+
   | snat_rule | Yes       | :ref:`CreatePrivateSnatOption <createprivatesnat__request_createprivatesnatoption>` object | Specifies the request body for creating an SNAT rule. |
   +-----------+-----------+--------------------------------------------------------------------------------------------+-------------------------------------------------------+

.. _createprivatesnat__request_createprivatesnatoption:

.. table:: **Table 4** CreatePrivateSnatOption

   +-----------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type             | Description                                                                                                                                      |
   +=================+=================+==================+==================================================================================================================================================+
   | gateway_id      | Yes             | String           | Specifies the private NAT gateway ID.                                                                                                            |
   +-----------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | cidr            | No              | String           | Specifies the CIDR block that matches the SNAT rule.                                                                                             |
   |                 |                 |                  |                                                                                                                                                  |
   |                 |                 |                  | Constraint: Either this parameter or **virsubnet_id** must be specified.                                                                         |
   +-----------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | virsubnet_id    | No              | String           | Specifies the ID of the subnet that matches the SNAT rule.                                                                                       |
   |                 |                 |                  |                                                                                                                                                  |
   |                 |                 |                  | Constraint: Either this parameter or **cidr** must be specified.                                                                                 |
   +-----------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | description     | No              | String           | Provides supplementary information about the SNAT rule. The description can contain up to 255 characters and cannot contain angle brackets (<>). |
   +-----------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | transit_ip_ids  | Yes             | Array of strings | Specifies the IDs of the transit IP addresses.                                                                                                   |
   |                 |                 |                  |                                                                                                                                                  |
   |                 |                 |                  | Constraints: A maximum number of 20 IDs is allowed.                                                                                              |
   +-----------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 201**

.. table:: **Table 5** Response body parameters

   +------------+---------------------------------------------------------------------+-----------------------------------------------+
   | Parameter  | Type                                                                | Description                                   |
   +============+=====================================================================+===============================================+
   | snat_rule  | :ref:`PrivateSnat <createprivatesnat__response_privatesnat>` object | Specifies the response body of the SNAT rule. |
   +------------+---------------------------------------------------------------------+-----------------------------------------------+
   | request_id | String                                                              | Specifies the request ID.                     |
   +------------+---------------------------------------------------------------------+-----------------------------------------------+

.. _createprivatesnat__response_privatesnat:

.. table:: **Table 6** PrivateSnat

   +-------------------------+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter               | Type                                                                                          | Description                                                                                                                                      |
   +=========================+===============================================================================================+==================================================================================================================================================+
   | id                      | String                                                                                        | Specifies the SNAT rule ID.                                                                                                                      |
   +-------------------------+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | project_id              | String                                                                                        | Specifies the project ID.                                                                                                                        |
   +-------------------------+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | gateway_id              | String                                                                                        | Specifies the private NAT gateway ID.                                                                                                            |
   +-------------------------+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | cidr                    | String                                                                                        | Specifies the CIDR block that matches the SNAT rule.                                                                                             |
   |                         |                                                                                               |                                                                                                                                                  |
   |                         |                                                                                               | Constraints:                                                                                                                                     |
   |                         |                                                                                               |                                                                                                                                                  |
   |                         |                                                                                               | -  Either this parameter or **virsubnet_id** must be specified.                                                                                  |
   |                         |                                                                                               |                                                                                                                                                  |
   |                         |                                                                                               | -  The CIDR block cannot be the same as that of an existing SNAT rule.                                                                           |
   +-------------------------+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | virsubnet_id            | String                                                                                        | Specifies the ID of the subnet that matches the SNAT rule.                                                                                       |
   |                         |                                                                                               |                                                                                                                                                  |
   |                         |                                                                                               | Constraint: Either this parameter or **cidr** must be specified.                                                                                 |
   +-------------------------+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | description             | String                                                                                        | Provides supplementary information about the SNAT rule. The description can contain up to 255 characters and cannot contain angle brackets (<>). |
   +-------------------------+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | transit_ip_associations | Array of :ref:`AssociatedTransitIp <createprivatesnat__response_associatedtransitip>` objects | Specifies the list of details of associated transit IP addresses.                                                                                |
   +-------------------------+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at              | String                                                                                        | Specifies the time when the SNAT rule was created. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                                            |
   +-------------------------+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | updated_at              | String                                                                                        | Specifies the time when the SNAT rule was updated. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                                            |
   +-------------------------+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id   | String                                                                                        | Specifies the enterprise project ID.                                                                                                             |
   +-------------------------+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                  | String                                                                                        | Specifies the SNAT rule status of a private NAT gateway.                                                                                         |
   |                         |                                                                                               |                                                                                                                                                  |
   |                         |                                                                                               | The value can be:                                                                                                                                |
   |                         |                                                                                               |                                                                                                                                                  |
   |                         |                                                                                               | -  **ACTIVE**: The SNAT rule is running properly.                                                                                                |
   |                         |                                                                                               |                                                                                                                                                  |
   |                         |                                                                                               | -  **FROZEN**: The SNAT rule is frozen.                                                                                                          |
   |                         |                                                                                               |                                                                                                                                                  |
   |                         |                                                                                               | Enumeration values:                                                                                                                              |
   |                         |                                                                                               |                                                                                                                                                  |
   |                         |                                                                                               | -  **ACTIVE**                                                                                                                                    |
   |                         |                                                                                               |                                                                                                                                                  |
   |                         |                                                                                               | -  **FROZEN**                                                                                                                                    |
   +-------------------------+-----------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+

.. _createprivatesnat__response_associatedtransitip:

.. table:: **Table 7** AssociatedTransitIp

   ================== ====== ===========================================
   Parameter          Type   Description
   ================== ====== ===========================================
   transit_ip_id      String Specifies the ID of the transit IP address.
   transit_ip_address String Specifies the transit IP address.
   ================== ====== ===========================================

Example Requests
----------------

Creating an SNAT rule (Setting **description** to **my_snat_rule01**, **gateway_id** to **80da6f26-94eb-4537-97f0-5a56f4d04cfb**, **virsubnet_id** to **5b9ea497-727d-4ad0-a99e-3984b3f5aaed**, and **transit_ip_ids** to **36a3049a-1682-48b3-b1cf-cb986a3350ef**)

.. code-block:: text

   POST https://{Endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/private-nat/snat-rules

   {
     "snat_rule" : {
       "description" : "my_snat_rule01",
       "gateway_id" : "80da6f26-94eb-4537-97f0-5a56f4d04cfb",
       "virsubnet_id" : "5b9ea497-727d-4ad0-a99e-3984b3f5aaed",
       "transit_ip_ids" : [ "36a3049a-1682-48b3-b1cf-cb986a3350ef" ]
     }
   }

Example Responses
-----------------

**Status code: 201**

SNAT rule created.

.. code-block::

   {
     "snat_rule" : {
       "id" : "af4dbb83-7ca0-4ed1-b28b-668c1f9c6b81",
       "project_id" : "cfa563efb77d4b6d9960781d82530fd8",
       "description" : "snat rule description",
       "gateway_id" : "80da6f26-94eb-4537-97f0-5a56f4d04cfb",
       "cidr" : "",
       "virsubnet_id" : "5b9ea497-727d-4ad0-a99e-3984b3f5aaed",
       "transit_ip_associations" : [ {
         "transit_ip_id" : "36a3049a-1682-48b3-b1cf-cb986a3350ef",
         "transit_ip_address" : "172.20.1.10"
       } ],
       "created_at" : "2019-10-22T03:31:19",
       "updated_at" : "2019-10-22T03:31:19",
       "status" : "ACTIVE"
     },
     "request_id" : "2937502e-73f9-4ba5-ae75-2293a0b35fb8"
   }

Status Codes
------------

=========== ==================
Status Code Description
=========== ==================
201         SNAT rule created.
=========== ==================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
