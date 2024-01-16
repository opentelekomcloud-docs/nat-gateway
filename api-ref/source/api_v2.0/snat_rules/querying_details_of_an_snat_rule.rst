:original_name: nat_api_0008.html

.. _nat_api_0008:

Querying Details of an SNAT Rule
================================

Function
--------

This API is used to query details of an SNAT rule.

URI
---

GET /v2.0/snat_rules/{snat_rule_id}

.. table:: **Table 1** Parameter description

   ============ ========= ====== ===========================
   Parameter    Mandatory Type   Description
   ============ ========= ====== ===========================
   snat_rule_id Yes       String Specifies the SNAT rule ID.
   ============ ========= ====== ===========================

Request
-------

None

Response
--------

:ref:`Table 2 <nat_api_0008__table65459315>` lists response parameter.

.. _nat_api_0008__table65459315:

.. table:: **Table 2** Response parameter

   +-----------+--------+-------------------------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                                           |
   +===========+========+=======================================================================================================+
   | snat_rule | Object | Specifies the SNAT rule object. For details, see :ref:`Table 3 <nat_api_0008__table113261845122312>`. |
   +-----------+--------+-------------------------------------------------------------------------------------------------------+

.. _nat_api_0008__table113261845122312:

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
   | floating_ip_id        | String(4096)          | -  Specifies the EIP ID. Use commas (,) to separate IDs.                                                                                  |
   |                       |                       | -  The maximum length of the ID is 4,096 bytes.                                                                                           |
   |                       |                       | -  Constraints: The number of EIP IDs cannot exceed 20.                                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_address   | String(1024)          | -  Specifies the EIP. Use commas (,) to separate EIPs.                                                                                    |
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
   |                       |                       | -  The value can be:                                                                                                                      |
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

      GET https://{Endpoint}/v2.0/snat_rules/5b95c675-69c2-4656-ba06-58ff72e1d338

-  Example response

   .. code-block::

      {
          "snat_rule": {
              "floating_ip_id": "bdc10a4c-d81a-41ec-adf7-de857f7c812a",
              "status": "ACTIVE",
              "nat_gateway_id": "a78fb3eb-1654-4710-8742-3fc49d5f04f8",
              "admin_state_up": true,
              "network_id": "eaad9cd6-2372-4be1-9535-9bd37210ae7b",
              "cidr": "null",
              "source_type":0,
              "tenant_id": "27e25061336f4af590faeabeb7fcd9a3",
              "created_at": "2017-11-18 07:54:21.665430",
              "id": "5b95c675-69c2-4656-ba06-58ff72e1d338",
              "floating_ip_address": "5.21.11.226",
              "freezed_ip_address": "",
              "description": "description"
          }
      }

Status Codes
------------

See :ref:`Status Codes <nat_api_0038>`.
