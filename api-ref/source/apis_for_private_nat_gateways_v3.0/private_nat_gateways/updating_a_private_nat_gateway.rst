:original_name: UpdatePrivateNat.html

.. _UpdatePrivateNat:

Updating a Private NAT Gateway
==============================

Function
--------

This API is used to update a private NAT gateway.

URI
---

PUT /v3/{project_id}/private-nat/gateways/{gateway_id}

.. table:: **Table 1** Path Parameters

   ========== ========= ====== =====================================
   Parameter  Mandatory Type   Description
   ========== ========= ====== =====================================
   project_id Yes       String Specifies the project ID.
   gateway_id Yes       String Specifies the private NAT gateway ID.
   ========== ========= ====== =====================================

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

   +-----------+-----------+-----------------------------------------------------------------------------------------+------------------------------------------------------------------+
   | Parameter | Mandatory | Type                                                                                    | Description                                                      |
   +===========+===========+=========================================================================================+==================================================================+
   | gateway   | Yes       | :ref:`UpdatePrivateNatOption <updateprivatenat__request_updateprivatenatoption>` object | Specifies the request body for updating the private NAT gateway. |
   +-----------+-----------+-----------------------------------------------------------------------------------------+------------------------------------------------------------------+

.. _updateprivatenat__request_updateprivatenatoption:

.. table:: **Table 4** UpdatePrivateNatOption

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                |
   +=================+=================+=================+============================================================================================================================================================+
   | name            | No              | String          | Specifies the private NAT gateway name.                                                                                                                    |
   |                 |                 |                 |                                                                                                                                                            |
   |                 |                 |                 | Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                                                        |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description     | No              | String          | Provides supplementary information about the private NAT gateway. The description can contain up to 255 characters and cannot contain angle brackets (<>). |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | spec            | No              | String          | Specifies the private NAT gateway specifications.                                                                                                          |
   |                 |                 |                 |                                                                                                                                                            |
   |                 |                 |                 | The value can be:                                                                                                                                          |
   |                 |                 |                 |                                                                                                                                                            |
   |                 |                 |                 | -  **Small**                                                                                                                                               |
   |                 |                 |                 |                                                                                                                                                            |
   |                 |                 |                 | -  **Medium**                                                                                                                                              |
   |                 |                 |                 |                                                                                                                                                            |
   |                 |                 |                 | -  **Large**                                                                                                                                               |
   |                 |                 |                 |                                                                                                                                                            |
   |                 |                 |                 | -  **Extra-large**                                                                                                                                         |
   |                 |                 |                 |                                                                                                                                                            |
   |                 |                 |                 | Enumeration values:                                                                                                                                        |
   |                 |                 |                 |                                                                                                                                                            |
   |                 |                 |                 | -  **Small**                                                                                                                                               |
   |                 |                 |                 |                                                                                                                                                            |
   |                 |                 |                 | -  **Medium**                                                                                                                                              |
   |                 |                 |                 |                                                                                                                                                            |
   |                 |                 |                 | -  **Large**                                                                                                                                               |
   |                 |                 |                 |                                                                                                                                                            |
   |                 |                 |                 | -  **Extra-large**                                                                                                                                         |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   +------------+------------------------------------------------------------------+----------------------------------------------------------+
   | Parameter  | Type                                                             | Description                                              |
   +============+==================================================================+==========================================================+
   | gateway    | :ref:`PrivateNat <updateprivatenat__response_privatenat>` object | Specifies the response body for the private NAT gateway. |
   +------------+------------------------------------------------------------------+----------------------------------------------------------+
   | request_id | String                                                           | Specifies the request ID.                                |
   +------------+------------------------------------------------------------------+----------------------------------------------------------+

.. _updateprivatenat__response_privatenat:

.. table:: **Table 6** PrivateNat

   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter                | Type                                                                         | Description                                                                                                                                                |
   +==========================+==============================================================================+============================================================================================================================================================+
   | id                       | String                                                                       | Specifies the private NAT gateway ID.                                                                                                                      |
   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | project_id               | String                                                                       | Specifies the project ID.                                                                                                                                  |
   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name                     | String                                                                       | Specifies the private NAT gateway name.                                                                                                                    |
   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description              | String                                                                       | Provides supplementary information about the private NAT gateway. The description can contain up to 255 characters and cannot contain angle brackets (<>). |
   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | spec                     | String                                                                       | Specifies the private NAT gateway specifications.                                                                                                          |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | The value can be:                                                                                                                                          |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | -  **Small**                                                                                                                                               |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | -  **Medium**                                                                                                                                              |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | -  **Large**                                                                                                                                               |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | -  **Extra-large**                                                                                                                                         |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | **Default value:**                                                                                                                                         |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | Small                                                                                                                                                      |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | Enumeration values:                                                                                                                                        |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | -  **Small**                                                                                                                                               |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | -  **Medium**                                                                                                                                              |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | -  **Large**                                                                                                                                               |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | -  **Extra-large**                                                                                                                                         |
   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                   | String                                                                       | Specifies the private NAT gateway status.                                                                                                                  |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | The value can be:                                                                                                                                          |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | -  **ACTIVE**: The private NAT gateway is running properly.                                                                                                |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | -  **FROZEN**: The private NAT gateway is frozen.                                                                                                          |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | Enumeration values:                                                                                                                                        |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | -  **ACTIVE**                                                                                                                                              |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | -  **FROZEN**                                                                                                                                              |
   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at               | String                                                                       | Specifies the time when the private NAT gateway was created. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                                            |
   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | updated_at               | String                                                                       | Specifies the time when the private NAT gateway was updated. It is a UTC time in *yyyy-mm-ddThh:mm:ssZ* format.                                            |
   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | downlink_vpcs            | Array of :ref:`DownlinkVpc <updateprivatenat__response_downlinkvpc>` objects | Specifies the VPC where the private NAT gateway works.                                                                                                     |
   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags                     | Array of :ref:`Tag <updateprivatenat__response_tag>` objects                 | Specifies the list of tags.                                                                                                                                |
   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id    | String                                                                       | Specifies the ID of the enterprise project that is associated with the private NAT gateway when the private NAT gateway is created.                        |
   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | rule_max                 | Integer                                                                      | Specifies the maximum number of rules.                                                                                                                     |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | **Value range:**                                                                                                                                           |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | 0-65535                                                                                                                                                    |
   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | transit_ip_pool_size_max | Integer                                                                      | Specifies the maximum number of transit IP addresses in a transit IP address pool.                                                                         |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | **Value range:**                                                                                                                                           |
   |                          |                                                                              |                                                                                                                                                            |
   |                          |                                                                              | 1-100                                                                                                                                                      |
   +--------------------------+------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _updateprivatenat__response_downlinkvpc:

.. table:: **Table 7** DownlinkVpc

   +-------------------+--------+---------------------------------------------------------------------+
   | Parameter         | Type   | Description                                                         |
   +===================+========+=====================================================================+
   | vpc_id            | String | Specifies the ID of the VPC where the private NAT gateway works.    |
   +-------------------+--------+---------------------------------------------------------------------+
   | virsubnet_id      | String | Specifies the ID of the subnet where the private NAT gateway works. |
   +-------------------+--------+---------------------------------------------------------------------+
   | ngport_ip_address | String | Specifies the private IP address of the private NAT gateway.        |
   +-------------------+--------+---------------------------------------------------------------------+

.. _updateprivatenat__response_tag:

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

Updating a private NAT gateway. (Setting **name** to **private-nat-gateway-name**, **description** to **private-nat-gateway-description**, and **spec** to **Medium**)

.. code-block:: text

   PUT https://{Endpoint}/v3/70505c941b9b4dfd82fd351932328a2f/private-nat/gateways/14338426-6afe-4019-996b-3a9525296e11

   {
     "gateway" : {
       "name" : "private-nat-gateway-name",
       "description" : "private-nat-gateway-description",
       "spec" : "Medium"
     }
   }

Example Responses
-----------------

**Status code: 200**

Private NAT gateway updated.

.. code-block::

   {
     "gateway" : {
       "id" : "14338426-6afe-4019-996b-3a9525296e11",
       "name" : "private-nat-gateway-name",
       "description" : "private-nat-gateway-description",
       "spec" : "Medium",
       "project_id" : "70505c941b9b4dfd82fd351932328a2f",
       "enterprise_project_id" : "2759da7b-8015-404c-ae0a-a389007b0e2a",
       "status" : "ACTIVE",
       "created_at" : "2019-04-22T08:47:13",
       "updated_at" : "2019-04-22T08:47:13",
       "tags" : [ {
         "key" : "key1",
         "value" : "value1"
       } ],
       "downlink_vpcs" : [ {
         "vpc_id" : "3cb66d44-9f75-4237-bfff-e37b14d23ad2",
         "virsubnet_id" : "373979ee-f4f0-46c5-80e3-0fbf72646b70",
         "ngport_ip_address" : "10.0.0.17"
       } ],
       "transit_ip_pool_size_max" : 1,
       "rule_max" : 20
     },
     "request_id" : "e7e3323e95b348708d26e68a0ddece71"
   }

Status Codes
------------

=========== ============================
Status Code Description
=========== ============================
200         Private NAT gateway updated.
=========== ============================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
