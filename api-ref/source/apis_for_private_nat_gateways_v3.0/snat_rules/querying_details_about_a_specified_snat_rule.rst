:original_name: ShowPrivateSnat.html

.. _ShowPrivateSnat:

Querying Details About a Specified SNAT Rule
============================================

Function
--------

This API is used to query details about a specified SNAT rule.

URI
---

GET /v3/{project_id}/private-nat/snat-rules/{snat_rule_id}

.. table:: **Table 1** Path Parameters

   ============ ========= ====== ===========================
   Parameter    Mandatory Type   Description
   ============ ========= ====== ===========================
   project_id   Yes       String Specifies the project ID.
   snat_rule_id Yes       String Specifies the SNAT rule ID.
   ============ ========= ====== ===========================

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

   +------------+-------------------------------------------------------------------+-----------------------------------------------+
   | Parameter  | Type                                                              | Description                                   |
   +============+===================================================================+===============================================+
   | snat_rule  | :ref:`PrivateSnat <showprivatesnat__response_privatesnat>` object | Specifies the response body of the SNAT rule. |
   +------------+-------------------------------------------------------------------+-----------------------------------------------+
   | request_id | String                                                            | Specifies the request ID.                     |
   +------------+-------------------------------------------------------------------+-----------------------------------------------+

.. _showprivatesnat__response_privatesnat:

.. table:: **Table 4** PrivateSnat

   +-------------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter               | Type                                                                                        | Description                                                                                                                                      |
   +=========================+=============================================================================================+==================================================================================================================================================+
   | id                      | String                                                                                      | Specifies the SNAT rule ID.                                                                                                                      |
   +-------------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | project_id              | String                                                                                      | Specifies the project ID.                                                                                                                        |
   +-------------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | gateway_id              | String                                                                                      | Specifies the private NAT gateway ID.                                                                                                            |
   +-------------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | cidr                    | String                                                                                      | Specifies the CIDR block that matches the SNAT rule.                                                                                             |
   |                         |                                                                                             |                                                                                                                                                  |
   |                         |                                                                                             | Constraints:                                                                                                                                     |
   |                         |                                                                                             |                                                                                                                                                  |
   |                         |                                                                                             | -  Either this parameter or **virsubnet_id** must be specified.                                                                                  |
   |                         |                                                                                             |                                                                                                                                                  |
   |                         |                                                                                             | -  The CIDR block cannot be the same as that of an existing SNAT rule.                                                                           |
   +-------------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | virsubnet_id            | String                                                                                      | Specifies the ID of the subnet that matches the SNAT rule.                                                                                       |
   |                         |                                                                                             |                                                                                                                                                  |
   |                         |                                                                                             | Constraint: Either this parameter or **cidr** must be specified.                                                                                 |
   +-------------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | description             | String                                                                                      | Provides supplementary information about the SNAT rule. The description can contain up to 255 characters and cannot contain angle brackets (<>). |
   +-------------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | transit_ip_associations | Array of :ref:`AssociatedTransitIp <showprivatesnat__response_associatedtransitip>` objects | Specifies the list of details of associated transit IP addresses.                                                                                |
   +-------------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at              | String                                                                                      | Specifies the time when the SNAT rule was created. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                                            |
   +-------------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | updated_at              | String                                                                                      | Specifies the time when the SNAT rule was updated. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                                            |
   +-------------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id   | String                                                                                      | Specifies the enterprise project ID.                                                                                                             |
   +-------------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                  | String                                                                                      | Specifies the SNAT rule status of a private NAT gateway.                                                                                         |
   |                         |                                                                                             |                                                                                                                                                  |
   |                         |                                                                                             | The value can be:                                                                                                                                |
   |                         |                                                                                             |                                                                                                                                                  |
   |                         |                                                                                             | -  **ACTIVE**: The SNAT rule is running properly.                                                                                                |
   |                         |                                                                                             |                                                                                                                                                  |
   |                         |                                                                                             | -  **FROZEN**: The SNAT rule is frozen.                                                                                                          |
   |                         |                                                                                             |                                                                                                                                                  |
   |                         |                                                                                             | Enumeration values:                                                                                                                              |
   |                         |                                                                                             |                                                                                                                                                  |
   |                         |                                                                                             | -  **ACTIVE**                                                                                                                                    |
   |                         |                                                                                             |                                                                                                                                                  |
   |                         |                                                                                             | -  **FROZEN**                                                                                                                                    |
   +-------------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+

.. _showprivatesnat__response_associatedtransitip:

.. table:: **Table 5** AssociatedTransitIp

   ================== ====== ===========================================
   Parameter          Type   Description
   ================== ====== ===========================================
   transit_ip_id      String Specifies the ID of the transit IP address.
   transit_ip_address String Specifies the transit IP address.
   ================== ====== ===========================================

Example Requests
----------------

.. code-block:: text

   GET https://{Endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/private-nat/snat-rules/8a522ff9-8158-494b-83cd-533b045700e6

Example Responses
-----------------

**Status code: 200**

SNAT rule details queried.

.. code-block::

   {
     "snat_rule" : {
       "id" : "8a522ff9-8158-494b-83cd-533b045700e6",
       "project_id" : "cfa563efb77d4b6d9960781d82530fd8",
       "description" : "my_snat_rule02",
       "gateway_id" : "80da6f26-94eb-4537-97f0-5a56f4d04cfb",
       "cidr" : "",
       "virsubnet_id" : "95df1b88-d9bc-4edd-a808-a771dd4ded32",
       "transit_ip_associations" : [ {
         "transit_ip_id" : "bbe7c2e7-3bad-445b-a067-b30acce66053",
         "transit_ip_address" : "172.20.1.98"
       } ],
       "created_at" : "2019-10-22T03:33:07",
       "updated_at" : "2019-10-22T03:33:07",
       "status" : "ACTIVE"
     },
     "request_id" : "c8b21002-a594-414d-9585-2cc5963d4c3e"
   }

Status Codes
------------

=========== ==========================
Status Code Description
=========== ==========================
200         SNAT rule details queried.
=========== ==========================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
