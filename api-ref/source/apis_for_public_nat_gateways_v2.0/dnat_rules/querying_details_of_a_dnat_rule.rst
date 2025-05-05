:original_name: nat_api_0013.html

.. _nat_api_0013:

Querying Details of a DNAT Rule
===============================

Function
--------

This API is used to query details of a DNAT rule.

URI
---

GET /v2.0/dnat_rules/{dnat_rule_id}

.. table:: **Table 1** Parameter description

   ============ ====== ========= ===========================
   Parameter    Type   Mandatory Description
   ============ ====== ========= ===========================
   dnat_rule_id String Yes       Specifies the DNAT rule ID.
   ============ ====== ========= ===========================

Request
-------

None

Response
--------

:ref:`Table 2 <nat_api_0013__table66411570165117>` lists response parameter.

.. _nat_api_0013__table66411570165117:

.. table:: **Table 2** Response parameter

   +-----------+--------+-----------------------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                                         |
   +===========+========+=====================================================================================================+
   | dnat_rule | Object | Specifies the DNAT rule object. For details, see :ref:`Table 3 <nat_api_0013__table9899152414719>`. |
   +-----------+--------+-----------------------------------------------------------------------------------------------------+

.. _nat_api_0013__table9899152414719:

.. table:: **Table 3** Description of the **dnat_rule** field

   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                               |
   +=======================+=======================+===========================================================================================================================================+
   | id                    | String                | Specifies the DNAT rule ID.                                                                                                               |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id             | String                | Specifies the project ID.                                                                                                                 |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | nat_gateway_id        | String                | Specifies the NAT gateway ID.                                                                                                             |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | port_id               | String                | Specifies the port ID of the cloud server (ECS or BMS).                                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | private_ip            | String                | Specifies the private IP address, for example, the IP address of an on-premises network connected by a Direct Connect connection.         |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | internal_service_port | Integer               | Specifies the port number used by the cloud server (ECS or BMS) to provide services for external systems.                                 |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_id        | String                | Specifies the EIP ID.                                                                                                                     |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_address   | String                | Specifies the EIP address.                                                                                                                |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | external_service_port | Integer               | Specifies the port for providing services for external systems.                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | protocol              | String                | Specifies the protocol. TCP, UDP, and ANY are supported.                                                                                  |
   |                       |                       |                                                                                                                                           |
   |                       |                       | The protocol number of TCP, UDP, and ANY are 6, 17, and 0, respectively.                                                                  |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | description           | String                | Provides supplementary information about the DNAT rule.                                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | -  Specifies the status of the DNAT rule.                                                                                                 |
   |                       |                       | -  For details about all its values, see :ref:`Table 1 <nat_api_0042__table1390614366107>`.                                               |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up        | Boolean               | -  Specifies whether the DNAT rule is enabled or disabled.                                                                                |
   |                       |                       | -  The value can be:                                                                                                                      |
   |                       |                       |                                                                                                                                           |
   |                       |                       |    -  **true**: The DNAT rule is enabled.                                                                                                 |
   |                       |                       |    -  **false**: The DNAT rule is disabled.                                                                                               |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at            | String                | Specifies when the DNAT rule was created (UTC time). Its value rounds to 6 decimal places for seconds. The format is yyyy-mm-dd hh:mm:ss. |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v2.0/dnat_rules/5b95c675-69c2-4656-ba06-58ff72e1d338

-  Example response

   .. code-block::

      {
        "dnat_rule": {
              "floating_ip_id": "bf99c679-9f41-4dac-8513-9c9228e713e1",
              "status": "ACTIVE",
              "nat_gateway_id": "cda3a125-2406-456c-a11f-598e10578541",
              "admin_state_up": true,
              "description": "description",
              "port_id": "9a469561-daac-4c94-88f5-39366e5ea193",
              "internal_service_port": 993,
              "protocol": "TCP",
              "tenant_id": "abc",
              "created_at": "2017-11-15 15:44:42.595173",
              "id": "79195d50-0271-41f1-bded-4c089b2502ff",
              "floating_ip_address": "5.21.11.226",
              "external_service_port": 242
              "private_ip": ""
         }
      }

Status Codes
------------

See :ref:`Status Codes <nat_api_0038>`.
