:original_name: nat_api_0007.html

.. _nat_api_0007:

Querying SNAT Rules
===================

Function
--------

This API is used to query SNAT rules.

URI
---

GET /v2.0/snat_rules

.. note::

   You can type the question mark (?) and ampersand (&) at the end of the URI to define multiple search criteria. All optional parameters can be filtered. For details, see the example request.

.. table:: **Table 1** Parameter description

   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter           | Mandatory       | Type            | Description                                                                                                                                                 |
   +=====================+=================+=================+=============================================================================================================================================================+
   | id                  | No              | String          | Specifies the SNAT rule ID.                                                                                                                                 |
   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit               | No              | Integer         | Specifies the number of records on each page.                                                                                                               |
   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id           | No              | String          | Specifies the project ID.                                                                                                                                   |
   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | nat_gateway_id      | No              | String          | Specifies the NAT gateway ID.                                                                                                                               |
   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | network_id          | No              | String          | Specifies the network ID used by the SNAT rule.                                                                                                             |
   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | cidr                | No              | String          | Specifies CIDR, which can be in the format of a network segment or a host IP address. Specify either this parameter or **network_id**.                      |
   |                     |                 |                 |                                                                                                                                                             |
   |                     |                 |                 | If **source_type** is set to **0**, **cidr** must be a subset of the VPC subnet.                                                                            |
   |                     |                 |                 |                                                                                                                                                             |
   |                     |                 |                 | If **source_type** is set to **1**, **cidr** must be a CIDR block of your on-premises network connected to the VPC through Direct Connect or Cloud Connect. |
   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | source_type         | No              | Integer         | **0**: Either **network_id** or **cidr** can be specified in a VPC.                                                                                         |
   |                     |                 |                 |                                                                                                                                                             |
   |                     |                 |                 | **1**: Only **cidr** can be specified over a Direct Connect connection.                                                                                     |
   |                     |                 |                 |                                                                                                                                                             |
   |                     |                 |                 | If no value is entered, the default value **0** (VPC) is used.                                                                                              |
   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_id      | No              | String(4096)    | Specifies the EIP ID.                                                                                                                                       |
   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_address | No              | String(1024)    | Specifies the EIP.                                                                                                                                          |
   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description         | No              | String          | Provides supplementary information about the SNAT rule.                                                                                                     |
   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status              | No              | String          | -  Specifies the status of the SNAT rule.                                                                                                                   |
   |                     |                 |                 | -  For details about all its values, see :ref:`Table 1 <nat_api_0042__table1390614366107>`.                                                                 |
   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up      | No              | Boolean         | -  Specifies whether the SNAT rule is enabled or disabled.                                                                                                  |
   |                     |                 |                 | -  The state can be:                                                                                                                                        |
   |                     |                 |                 |                                                                                                                                                             |
   |                     |                 |                 |    -  **true**: The SNAT rule is enabled.                                                                                                                   |
   |                     |                 |                 |    -  **false**: The SNAT rule is disabled.                                                                                                                 |
   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at          | No              | String          | Specifies when the SNAT rule was created (UTC time). Its value rounds to 6 decimal places for seconds. The format is yyyy-mm-dd hh:mm:ss.                   |
   +---------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

None

Response
--------

:ref:`Table 2 <nat_api_0007__table25574495>` lists response parameters.

.. _nat_api_0007__table25574495:

.. table:: **Table 2** Response parameter

   +------------+-------------------+-----------------------------------------------------------------------------------------------------+
   | Parameter  | Type              | Description                                                                                         |
   +============+===================+=====================================================================================================+
   | snat_rules | List (SNAT rules) | Specifies the SNAT rule objects. For details, see :ref:`Table 3 <nat_api_0007__table589411291812>`. |
   +------------+-------------------+-----------------------------------------------------------------------------------------------------+

.. _nat_api_0007__table589411291812:

.. table:: **Table 3** Description of the **snat_rule** field

   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                               |
   +=======================+=======================+===========================================================================================================================================+
   | id                    | String                | Specifies the SNAT rule ID.                                                                                                               |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id             | String                | Specifies the project ID.                                                                                                                 |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | nat_gateway_id        | String                | Specifies the NAT gateway ID.                                                                                                             |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | network_id            | String                | Specifies the network ID used by the SNAT rule.                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | cidr                  | String                | Specifies a subset of the VPC subnet CIDR block or a CIDR block of a Direct Connect connection.                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | source_type           | Integer               | **0**: Either **network_id** or **cidr** can be specified in a VPC.                                                                       |
   |                       |                       |                                                                                                                                           |
   |                       |                       | **1**: Only **cidr** can be specified over a Direct Connect connection.                                                                   |
   |                       |                       |                                                                                                                                           |
   |                       |                       | If no value is entered, the default value **0** (VPC) is used.                                                                            |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_id        | String(4096)          | -  Specifies the EIP ID. Use commas (,) to separate multiple IDs.                                                                         |
   |                       |                       | -  The maximum length of the ID is 4,096 bytes.                                                                                           |
   |                       |                       | -  Constraints: The number of EIP IDs cannot exceed 20.                                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_address   | String(1024)          | -  Specifies the EIP. Use commas (,) to separate multiple EIPs.                                                                           |
   |                       |                       | -  The maximum length is 1,024 bytes.                                                                                                     |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | freezed_ip_address    | String(1024)          | -  Specifies the frozen EIP. Use commas (,) to separate frozen EIPs.                                                                      |
   |                       |                       | -  The maximum length is 1,024 bytes.                                                                                                     |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | description           | String(255)           | Provides supplementary information about the SNAT rule.                                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | -  Specifies the status of the SNAT rule.                                                                                                 |
   |                       |                       | -  For details about all its values, see :ref:`Table 1 <nat_api_0042__table1390614366107>`.                                               |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up        | Boolean               | -  Specifies whether the SNAT rule is enabled or disabled.                                                                                |
   |                       |                       | -  The state can be:                                                                                                                      |
   |                       |                       |                                                                                                                                           |
   |                       |                       |    -  **true**: The SNAT rule is enabled.                                                                                                 |
   |                       |                       |    -  **false**: The SNAT rule is disabled.                                                                                               |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at            | String                | Specifies when the SNAT rule was created (UTC time). Its value rounds to 6 decimal places for seconds. The format is yyyy-mm-dd hh:mm:ss. |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v2.0/snat_rules?limit=10

-  Example response

   .. code-block::

      {
          "snat_rules": [
            {
                  "floating_ip_id": "bf99c679-9f41-4dac-8513-9c9228e713e1",
                  "status": "ACTIVE",
                  "nat_gateway_id": "cda3a125-2406-456c-a11f-598e10578541",
                  "admin_state_up": true,
                  "network_id": "9a469561-daac-4c94-88f5-39366e5ea193",
                  "cidr": "null",
                  "source_type":0,
                  "tenant_id": "abc",
                  "created_at": "2017-11-15 15:44:42.595173",
                  "id": "79195d50-0271-41f1-bded-4c089b2502ff",
                  "floating_ip_address": "5.21.11.242",
                  "freezed_ip_address": "",
                  "description": "description"
              },
              {
                  "floating_ip_id": "6e496fba-abe9-4f5e-9406-2ad8c809ac8c",
                  "status": "ACTIVE",
                  "nat_gateway_id": "e824f1b4-4290-4ebc-8322-cfff370dbd1e",
                  "admin_state_up": true,
                  "network_id": "97e89905-f9c8-4ae3-9856-392b0b2fbe7f",
                  "cidr": "null",
                  "source_type":0,
                  "tenant_id": "abc",
                  "created_at": "2017-11-17 07:43:44.830845",
                  "id": "4a1a10d7-0d9f-4846-8cda-24cffeffef5c",
                  "floating_ip_address": "5.21.11.142",
                  "freezed_ip_address": "",
                  "description": "description"
              }
          ]
      }

Status Codes
------------

See :ref:`Status Codes <nat_api_0038>`.
