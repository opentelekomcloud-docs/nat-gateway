:original_name: UpdatePrivateSnat.html

.. _UpdatePrivateSnat:

Updating an SNAT Rule
=====================

Function
--------

This API is used to update a specified SNAT rule.

URI
---

PUT /v3/{project_id}/private-nat/snat-rules/{snat_rule_id}

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

.. table:: **Table 3** Request body parameters

   +-----------+-----------+--------------------------------------------------------------------------------------------+-------------------------------------------------------+
   | Parameter | Mandatory | Type                                                                                       | Description                                           |
   +===========+===========+============================================================================================+=======================================================+
   | snat_rule | Yes       | :ref:`UpdatePrivateSnatOption <updateprivatesnat__request_updateprivatesnatoption>` object | Specifies the request body for updating an SNAT rule. |
   +-----------+-----------+--------------------------------------------------------------------------------------------+-------------------------------------------------------+

.. _updateprivatesnat__request_updateprivatesnatoption:

.. table:: **Table 4** UpdatePrivateSnatOption

   +----------------+-----------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter      | Mandatory | Type             | Description                                                                                                                                      |
   +================+===========+==================+==================================================================================================================================================+
   | transit_ip_ids | No        | Array of strings | Specifies the ID list of transit IP addresses.                                                                                                   |
   +----------------+-----------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | description    | No        | String           | Provides supplementary information about the SNAT rule. The description can contain up to 255 characters and cannot contain angle brackets (<>). |
   +----------------+-----------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   +------------+---------------------------------------------------------------------+-----------------------------------------------+
   | Parameter  | Type                                                                | Description                                   |
   +============+=====================================================================+===============================================+
   | request_id | String                                                              | Specifies the request ID.                     |
   +------------+---------------------------------------------------------------------+-----------------------------------------------+
   | snat_rule  | :ref:`PrivateSnat <updateprivatesnat__response_privatesnat>` object | Specifies the response body of the SNAT rule. |
   +------------+---------------------------------------------------------------------+-----------------------------------------------+

.. _updateprivatesnat__response_privatesnat:

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
   | transit_ip_associations | Array of :ref:`AssociatedTransitIp <updateprivatesnat__response_associatedtransitip>` objects | Specifies the list of details of associated transit IP addresses.                                                                                |
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

.. _updateprivatesnat__response_associatedtransitip:

.. table:: **Table 7** AssociatedTransitIp

   ================== ====== ===========================================
   Parameter          Type   Description
   ================== ====== ===========================================
   transit_ip_id      String Specifies the ID of the transit IP address.
   transit_ip_address String Specifies the transit IP address.
   ================== ====== ===========================================

Example Requests
----------------

Updating an SNAT rule (Setting **transit_ip_ids** to **bbe7c2e7-3bad-445b-a067-b30acce66053** and **description** to **my_snat_rule_update**)

.. code-block:: text

   PUT https://{Endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/private-nat/snat-rules/af4dbb83-7ca0-4ed1-b28b-668c1f9c6b81

   {
     "snat_rule" : {
       "description" : "my_snat_rule_update",
       "transit_ip_ids" : [ "bbe7c2e7-3bad-445b-a067-b30acce66053" ]
     }
   }

Example Responses
-----------------

**Status code: 200**

SNAT rule updated.

.. code-block::

   {
     "request_id" : "15bd32b2-1464-4817-b559-444d22499f6c",
     "snat_rule" : {
       "id" : "af4dbb83-7ca0-4ed1-b28b-668c1f9c6b81",
       "project_id" : "cfa563efb77d4b6d9960781d82530fd8",
       "description" : "my_snat_rule_update",
       "gateway_id" : "80da6f26-94eb-4537-97f0-5a56f4d04cfb",
       "cidr" : "10.1.1.64/30",
       "virsubnet_id" : "",
       "transit_ip_associations" : [ {
         "transit_ip_id" : "bbe7c2e7-3bad-445b-a067-b30acce66053",
         "transit_ip_address" : "172.20.1.98"
       } ],
       "created_at" : "2019-10-22T03:31:19",
       "updated_at" : "2019-10-22T03:39:52",
       "status" : "ACTIVE"
     }
   }

Status Codes
------------

=========== ==================
Status Code Description
=========== ==================
200         SNAT rule updated.
=========== ==================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
