:original_name: nat_api_0062.html

.. _nat_api_0062:

Querying Details of a NAT Gateway
=================================

Function
--------

This API is used to query details of a NAT gateway.

URI
---

GET /v2.0/nat_gateways/{nat_gateway_id}

.. table:: **Table 1** Parameter description

   ============== ========= ====== =============================
   Parameter      Mandatory Type   Description
   ============== ========= ====== =============================
   nat_gateway_id Yes       String Specifies the NAT gateway ID.
   ============== ========= ====== =============================

Request
-------

None

Response
--------

:ref:`Table 2 <nat_api_0062__table129831149144215>` lists response parameter.

.. _nat_api_0062__table129831149144215:

.. table:: **Table 2** Response parameter

   +-------------+--------+------------------------------------------------------------------------------------------------------+
   | Parameter   | Type   | Description                                                                                          |
   +=============+========+======================================================================================================+
   | nat_gateway | Object | Specifies the NAT gateway object. For details, see :ref:`Table 3 <nat_api_0062__table514165011429>`. |
   +-------------+--------+------------------------------------------------------------------------------------------------------+

.. _nat_api_0062__table514165011429:

.. table:: **Table 3** Description of the **nat_gateway** field

   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter                 | Type                  | Description                                                                                                                                 |
   +===========================+=======================+=============================================================================================================================================+
   | id                        | String                | Specifies the NAT gateway ID.                                                                                                               |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id                 | String                | Specifies the project ID.                                                                                                                   |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | name                      | String(64)            | Specifies the NAT gateway name.                                                                                                             |
   |                           |                       |                                                                                                                                             |
   |                           |                       | The name can contain only digits, letters, underscores (_), and hyphens (-).                                                                |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | description               | String(255)           | Provides supplementary information about the NAT gateway.                                                                                   |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | spec                      | String                | Specifies the NAT gateway specifications.                                                                                                   |
   |                           |                       |                                                                                                                                             |
   |                           |                       | The value can be:                                                                                                                           |
   |                           |                       |                                                                                                                                             |
   |                           |                       | -  **0**: micro type, which supports up to 1,000 SNAT connections.                                                                          |
   |                           |                       |                                                                                                                                             |
   |                           |                       | -  **1**: small type, which supports up to 10,000 SNAT connections.                                                                         |
   |                           |                       | -  **2**: medium type, which supports up to 50,000 SNAT connections.                                                                        |
   |                           |                       | -  **3**: large type, which supports up to 200,000 SNAT connections.                                                                        |
   |                           |                       | -  **4**: extra-large type, which supports up to 1,000,000 SNAT connections.                                                                |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | router_id                 | String                | Specifies the router ID.                                                                                                                    |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | internal_network_id       | String                | Specifies the network ID of the downstream interface (the next hop of the DVR) of the NAT gateway.                                          |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | status                    | String                | -  Specifies the NAT gateway status.                                                                                                        |
   |                           |                       | -  For details about all its values, see :ref:`Table 1 <nat_api_0042__table1390614366107>`.                                                 |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up            | Boolean               | -  Specifies whether the NAT gateway is started or stopped.                                                                                 |
   |                           |                       | -  The value can be:                                                                                                                        |
   |                           |                       |                                                                                                                                             |
   |                           |                       |    -  **true**: The NAT gateway is started.                                                                                                 |
   |                           |                       |    -  **false**: The NAT gateway is stopped.                                                                                                |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at                | String                | Specifies when the NAT gateway was created (UTC time). Its value rounds to 6 decimal places for seconds. The format is yyyy-mm-dd hh:mm:ss. |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | billinginfo               | String                | Specifies the order information. This parameter is left blank by default.                                                                   |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | sys_tags                  | List<String>          | Specifies the ID of the enterprise project associated with the NAT gateway when the NAT gateway is created.                                 |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | snat_rule_public_ip_limit | Integer               | Specifies the maximum number of EIPs in an SNAT rule on a NAT gateway. The default value is **20**.                                         |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | dnat_rules_limit          | Long                  | Specifies the maximum number of DNAT rules on a NAT gateway. The default value is **200**.                                                  |
   +---------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v2.0/nat_gateways/a78fb3eb-1654-4710-8742-3fc49d5f04f8

-  Example response

   .. code-block::

      {
          "nat_gateway": {
               "router_id": "d84f345c-80a1-4fa2-a39c-d0d397c3f09a",
               "status": "ACTIVE",
               "description": "my nat gateway 01",
               "admin_state_up": true,
               "tenant_id": "27e25061336f4af590faeabeb7fcd9a3",
               "created_at": "2017-11-18 07:34:32.203044",
               "spec": "1",
               "internal_network_id": "89d66639-aacb-4929-969d-07080b0f9fd9",
               "id": "a78fb3eb-1654-4710-8742-3fc49d5f04f8",
               "billinginfo": "",
               "dnat_rules_limit": 200,
               "snat_rule_public_ip_limit": 20,
               "sys_tags": [
                   "_sys_enterprise_project_id=0"
               ],
               "name": "nat_001"
          }
      }

Status Codes
------------

See :ref:`Status Codes <nat_api_0038>`.
