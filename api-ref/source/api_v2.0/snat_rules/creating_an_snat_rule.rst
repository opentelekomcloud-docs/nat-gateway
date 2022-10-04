:original_name: nat_api_0006.html

.. _nat_api_0006:

Creating an SNAT Rule
=====================

Function
--------

This API is used to create an SNAT rule.

.. note::

   You can create an SNAT rule only when **status** of the NAT gateway is set to **ACTIVE** and **admin_state_up** of the NAT gateway administrator to **True**.

URI
---

POST /v2.0/snat_rules

Request
-------

:ref:`Table 1 <nat_api_0006__table10267194320114>` describes the request parameters.

.. _nat_api_0006__table10267194320114:

.. table:: **Table 1** Request parameter

   +-----------+-----------+--------+----------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                        |
   +===========+===========+========+====================================================================================================+
   | snat_rule | Yes       | Object | Specifies the SNAT rule object. For details, see :ref:`Table 2 <nat_api_0006__table628219431019>`. |
   +-----------+-----------+--------+----------------------------------------------------------------------------------------------------+

.. _nat_api_0006__table628219431019:

.. table:: **Table 2** Description of the **snat_rule** field

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                              |
   +=================+=================+=================+==========================================================================================================================================+
   | nat_gateway_id  | Yes             | String          | Specifies the NAT gateway ID.                                                                                                            |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | network_id      | No              | String          | Specifies the network ID used by the SNAT rule. This parameter and **cidr** are alternative.                                             |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | cidr            | No              | String          | Specifies CIDR, which can be in the format of a network segment or a host IP address. This parameter and **network_id** are alternative. |
   |                 |                 |                 |                                                                                                                                          |
   |                 |                 |                 | If the value of **Source_type** is **0**, the CIDR block must be a subset of the VPC subnet CIDR block.                                  |
   |                 |                 |                 |                                                                                                                                          |
   |                 |                 |                 | If the value of **Source_type** is **1**, **cidr** must be a CIDR block of Direct Connect connection.                                    |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | source_type     | No              | Integer         | **0**: Either **network_id** or **cidr** can be specified in a VPC.                                                                      |
   |                 |                 |                 |                                                                                                                                          |
   |                 |                 |                 | **1**: Only **cidr** can be specified over a Direct Connect connection.                                                                  |
   |                 |                 |                 |                                                                                                                                          |
   |                 |                 |                 | If no value is entered, the default value **0** (VPC) is used.                                                                           |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_id  | Yes             | String          | Specifies the EIP ID. Multiple EIPs are separated using commas (,).                                                                      |
   |                 |                 |                 |                                                                                                                                          |
   |                 |                 |                 | The maximum length of the ID is 4096 bytes.                                                                                              |
   |                 |                 |                 |                                                                                                                                          |
   |                 |                 |                 | The number of EIP IDs cannot exceed 20.                                                                                                  |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

:ref:`Table 3 <nat_api_0006__table64245911>` lists response parameters.

.. _nat_api_0006__table64245911:

.. table:: **Table 3** Response parameter

   +-----------+--------+-------------------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                                     |
   +===========+========+=================================================================================================+
   | snat_rule | Object | Specifies the SNAT rule object. For details, see :ref:`Table 4 <nat_api_0006__table161525103>`. |
   +-----------+--------+-------------------------------------------------------------------------------------------------+

.. _nat_api_0006__table161525103:

.. table:: **Table 4** Description of the **snat_rule** field

   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                              |
   +=======================+=======================+==========================================================================================================================================+
   | id                    | String                | Specifies the SNAT rule ID.                                                                                                              |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id             | String                | Specifies the project ID.                                                                                                                |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | nat_gateway_id        | String                | Specifies the NAT gateway ID.                                                                                                            |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | network_id            | String                | Specifies the network ID used by the SNAT rule.                                                                                          |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | cidr                  | String                | Specifies a subset of the VPC subnet CIDR block or a CIDR block of Direct Connect connection.                                            |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | source_type           | Integer               | **0**: Either **network_id** or **cidr** can be specified in a VPC.                                                                      |
   |                       |                       |                                                                                                                                          |
   |                       |                       | **1**: Only **cidr** can be specified over a Direct Connect connection.                                                                  |
   |                       |                       |                                                                                                                                          |
   |                       |                       | If no value is entered, the default value **0** (VPC) is used.                                                                           |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_id        | String(4096)          | -  Specifies the EIP ID. Multiple EIPs are separated using commas (,).                                                                   |
   |                       |                       | -  The maximum length of the ID is 4096 bytes.                                                                                           |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_address   | String(1024)          | -  Specifies the EIP. Multiple EIPs are separated using commas (,).                                                                      |
   |                       |                       | -  The maximum length is 1024 bytes.                                                                                                     |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | -  Specifies the status of the SNAT rule.                                                                                                |
   |                       |                       | -  For details about all its values, see :ref:`Table 1 <nat_api_0042__table1390614366107>`.                                              |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up        | Boolean               | -  Specifies whether the SNAT rule is enabled or disabled.                                                                               |
   |                       |                       | -  The value can be:                                                                                                                     |
   |                       |                       |                                                                                                                                          |
   |                       |                       |    -  **true**: The SNAT rule is enabled.                                                                                                |
   |                       |                       |    -  **false**: The SNAT rule is disabled.                                                                                              |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at            | String                | Specifies when the SNAT rule is created (UTC time). Its value rounds to 6 decimal places for seconds. The format is yyyy-mm-dd hh:mm:ss. |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   #. Configure parameter **network_id** in a VPC.

      .. code-block:: text

         POST https://{Endpoint}/v2.0/snat_rules
         {
             "snat_rule": {
                 "nat_gateway_id": "a78fb3eb-1654-4710-8742-3fc49d5f04f8",
                 "network_id": "eaad9cd6-2372-4be1-9535-9bd37210ae7b",
                 "source_type":0,
                 "floating_ip_id": "bdc10a4c-d81a-41ec-adf7-de857f7c812a"
             }
         }

   2. Configure parameter **cider** in a VPC.

      .. code-block:: text

         POST https://{Endpoint}/v2.0/snat_rules
         {
            "snat_rule": {
                  "nat_gateway_id": "a78fb3eb-1654-4710-8742-3fc49d5f04f8",
                  "cidr": "192.168.1.10/32",
                  "source_type":0,
                  "floating_ip_id": "bdc10a4c-d81a-41ec-adf7-de857f7c812a"
               }
           }

   3. Configure parameter **cider** over a Direct Connect connection.

      .. code-block:: text

         POST https://{Endpoint}/v2.0/snat_rules
          {
               "snat_rule": {
                  "nat_gateway_id": "a78fb3eb-1654-4710-8742-3fc49d5f04f8",
                  "cidr": "172.30.0.0/24",
                  "source_type":1,
                  "floating_ip_id": "bdc10a4c-d81a-41ec-adf7-de857f7c812a"
               }
           }

-  Example response

   #. Response to the request for specifying the **network_id** for a VPC

      .. code-block::

         {
              "snat_rule": {
                  "floating_ip_id": "bdc10a4c-d81a-41ec-adf7-de857f7c812a",
                  "status": "PENDING_CREATE",
                  "nat_gateway_id": "a78fb3eb-1654-4710-8742-3fc49d5f04f8",
                  "admin_state_up": true,
                  "network_id": "eaad9cd6-2372-4be1-9535-9bd37210ae7b",
                  "cidr": null,
                  "source_type":0,
                  "tenant_id": "27e25061336f4af590faeabeb7fcd9a3",
                  "created_at": "2017-11-18 07:54:21.665430",
                  "id": "5b95c675-69c2-4656-ba06-58ff72e1d338",
                  "floating_ip_address": "5.21.11.226"
              }
          }

   #. Response to the request for specifying the CIDR block in a VPC

      .. code-block::

         {
              "snat_rule": {
                  "floating_ip_id": "bdc10a4c-d81a-41ec-adf7-de857f7c812a",
                  "status": "PENDING_CREATE",
                  "nat_gateway_id": "a78fb3eb-1654-4710-8742-3fc49d5f04f8",
                  "admin_state_up": true,
                  "cidr": "192.168.1.10/32",
                  "source_type":0,
                  "tenant_id": "27e25061336f4af590faeabeb7fcd9a3",
                  "created_at": "2017-11-18 07:54:21.665430",
                  "id": "5b95c675-69c2-4656-ba06-58ff72e1d338",
                  "floating_ip_address": "5.21.11.226"
              }
          }

   #. Response to the request for specifying the CIDR block in a VPC

      .. code-block::

         {
              "snat_rule": {
                  "floating_ip_id": "bdc10a4c-d81a-41ec-adf7-de857f7c812a",
                  "status": "PENDING_CREATE",
                  "nat_gateway_id": "a78fb3eb-1654-4710-8742-3fc49d5f04f8",
                  "admin_state_up": true,
                  "cidr": "172.30.0.0/24",
                  "source_type":1,
                  "tenant_id": "27e25061336f4af590faeabeb7fcd9a3",
                  "created_at": "2017-11-18 07:54:21.665430",
                  "id": "5b95c675-69c2-4656-ba06-58ff72e1d338",
                  "floating_ip_address": "5.21.11.226"
              }
          }

Status Code
-----------

See :ref:`Status Codes <nat_api_0038>`.
