:original_name: UpdatePrivateDnat.html

.. _UpdatePrivateDnat:

Updating a DNAT Rule
====================

Function
--------

This API is used to update a specified DNAT rule.

URI
---

PUT /v3/{project_id}/private-nat/dnat-rules/{dnat_rule_id}

.. table:: **Table 1** Path Parameters

   ============ ========= ====== ===========================
   Parameter    Mandatory Type   Description
   ============ ========= ====== ===========================
   project_id   Yes       String Specifies the project ID.
   dnat_rule_id Yes       String Specifies the DNAT rule ID.
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

   +-----------+-----------+--------------------------------------------------------------------------------------------+------------------------------------------------------+
   | Parameter | Mandatory | Type                                                                                       | Description                                          |
   +===========+===========+============================================================================================+======================================================+
   | dnat_rule | No        | :ref:`UpdatePrivateDnatOption <updateprivatednat__request_updateprivatednatoption>` object | Specifies the request body for updating a DNAT rule. |
   +-----------+-----------+--------------------------------------------------------------------------------------------+------------------------------------------------------+

.. _updateprivatednat__request_updateprivatednatoption:

.. table:: **Table 4** UpdatePrivateDnatOption

   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                     |
   +=======================+=================+=================+=================================================================================================================================================================================================================================================================================+
   | description           | No              | String          | Provides supplementary information about the DNAT rule. The description can contain up to 255 characters and cannot contain angle brackets (<>).                                                                                                                                |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | transit_ip_id         | No              | String          | Specifies the ID of the transit IP address.                                                                                                                                                                                                                                     |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | network_interface_id  | No              | String          | Specifies the port ID of the resource that the NAT gateway is bound to. The resource can be a compute instance, load balancer (v2 or v3), or virtual IP address. Note: Either this parameter or **private_ip_address** must be specified. Otherwise, an error will be reported. |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | private_ip_address    | No              | String          | Specifies the port IP address that the NAT gateway uses. The resource can be a compute instance, load balancer (v2 or v3), or virtual IP address. Note: Either this parameter or **network_interface_id** must be specified. Otherwise, an error will be reported.              |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | protocol              | No              | String          | Specifies the protocol type.                                                                                                                                                                                                                                                    |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | TCP, UDP, and ANY are supported.                                                                                                                                                                                                                                                |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | The protocol number of TCP, UDP, and ANY are 6, 17, and 0, respectively.                                                                                                                                                                                                        |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | Enumeration values:                                                                                                                                                                                                                                                             |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | -  **tcp**                                                                                                                                                                                                                                                                      |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | -  **udp**                                                                                                                                                                                                                                                                      |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | -  **any**                                                                                                                                                                                                                                                                      |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | internal_service_port | No              | String          | Specifies the port number of the resource, which can be a compute instance, load balancer (v2 or v3), or virtual IP address.                                                                                                                                                    |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | **Value range:**                                                                                                                                                                                                                                                                |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | 0-65535                                                                                                                                                                                                                                                                         |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | **Default value:**                                                                                                                                                                                                                                                              |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | 0                                                                                                                                                                                                                                                                               |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | transit_service_port  | No              | String          | Specifies the port number of the transit IP address.                                                                                                                                                                                                                            |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | **Value range:**                                                                                                                                                                                                                                                                |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | 0-65535                                                                                                                                                                                                                                                                         |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | **Default value:**                                                                                                                                                                                                                                                              |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                 |
   |                       |                 |                 | 0                                                                                                                                                                                                                                                                               |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   +------------+---------------------------------------------------------------------+-----------------------------------------------+
   | Parameter  | Type                                                                | Description                                   |
   +============+=====================================================================+===============================================+
   | dnat_rule  | :ref:`PrivateDnat <updateprivatednat__response_privatednat>` object | Specifies the response body of the DNAT rule. |
   +------------+---------------------------------------------------------------------+-----------------------------------------------+
   | request_id | String                                                              | Specifies the request ID.                     |
   +------------+---------------------------------------------------------------------+-----------------------------------------------+

.. _updateprivatednat__response_privatednat:

.. table:: **Table 6** PrivateDnat

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

Example Requests
----------------

Updating a DNAT rule (Updating **description** to **my dnat-rules 03**)

.. code-block:: text

   PUT https://{Endpoint}/v3/da261828016849188f4dcc2ef94d9da9/private-nat/dnat-rules/24dd6bf5-48f2-4915-ad0b-5bb111d39c83

   {
     "dnat_rule" : {
       "description" : "my dnat-rules 03"
     }
   }

Example Responses
-----------------

**Status code: 200**

DNAT rule updated.

.. code-block::

   {
     "dnat_rule" : {
       "id" : "24dd6bf5-48f2-4915-ad0b-5bb111d39c83",
       "project_id" : "da261828016849188f4dcc2ef94d9da9",
       "description" : "dnat rule description",
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
     },
     "request_id" : "747a911c17067a39692f75ac146fb47e"
   }

Status Codes
------------

=========== ==================
Status Code Description
=========== ==================
200         DNAT rule updated.
=========== ==================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
