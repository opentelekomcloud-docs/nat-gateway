:original_name: nat_api_0011.html

.. _nat_api_0011:

Creating a DNAT Rule
====================

Function
--------

This API is used to create a DNAT rule.

.. note::

   You can create a DNAT rule only when **status** of the NAT gateway is set to **ACTIVE** and **admin_state_up** of the NAT gateway administrator to **True**. Either **port_id** or **private_ip** is used each time. If you create a rule that applies to all port types, set **internal_service_port** to **0**, **external_service_port** to **0**, and **protocol** to **ANY**.

URI
---

POST /v2.0/dnat_rules

Request
-------

:ref:`Table 1 <nat_api_0011__table19385203615518>` lists the request parameters.

.. _nat_api_0011__table19385203615518:

.. table:: **Table 1** Request parameter

   +-----------+-----------+--------+----------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                        |
   +===========+===========+========+====================================================================================================+
   | dnat_rule | Yes       | Object | Specifies the DNAT rule object. For details, see :ref:`Table 2 <nat_api_0011__table132796437212>`. |
   +-----------+-----------+--------+----------------------------------------------------------------------------------------------------+

.. _nat_api_0011__table132796437212:

.. table:: **Table 2** Description of the **dnat_rule** field

   +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                                                                      |
   +=======================+=================+=================+==================================================================================================================================================================================================================================================================================================================================+
   | nat_gateway_id        | Yes             | String          | Specifies the NAT gateway ID.                                                                                                                                                                                                                                                                                                    |
   +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | port_id               | No              | String          | Specifies the port ID of an ECS or a BMS. This parameter and **private_ip** are alternative.                                                                                                                                                                                                                                     |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                                                                  |
   |                       |                 |                 | When the DNAT rule is used in the VPC scenario, use this parameter.                                                                                                                                                                                                                                                              |
   +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | private_ip            | No              | String          | Specifies the private IP address, for example, the IP address of a Direct Connect connection. This parameter and **port_id** are alternative.                                                                                                                                                                                    |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                                                                  |
   |                       |                 |                 | When the DNAT rule is used in the Direct Connect scenario, use this parameter.                                                                                                                                                                                                                                                   |
   +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | internal_service_port | Yes             | Integer         | Specifies the port used by ECSs or BMSs to provide services that are accessible from external systems. In the VPC scenario, this parameter indicates the NIC port of the ECS or BMS associated with the DNAT rule. In the Direct Connect scenario, this parameter indicates the port of the private IP address of the DNAT rule. |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                                                                  |
   |                       |                 |                 | The value ranges from 0 to 65535.                                                                                                                                                                                                                                                                                                |
   +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_id        | Yes             | String          | Specifies the EIP ID.                                                                                                                                                                                                                                                                                                            |
   +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | external_service_port | Yes             | Integer         | Specifies the port for providing services that are accessible from external systems..                                                                                                                                                                                                                                            |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                                                                  |
   |                       |                 |                 | The value ranges from 0 to 65535.                                                                                                                                                                                                                                                                                                |
   +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | protocol              | Yes             | String          | Specifies the protocol type. Currently, TCP, UDP, and ANY are supported.                                                                                                                                                                                                                                                         |
   |                       |                 |                 |                                                                                                                                                                                                                                                                                                                                  |
   |                       |                 |                 | The protocol number of TCP, UDP, and ANY are 6, 17, and 0, respectively.                                                                                                                                                                                                                                                         |
   +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. note::

   To map all ports, set **internal_service_port** and **external_service_port** to **0** and **protocol** to **ANY** or **0**.

Response
--------

:ref:`Table 3 <nat_api_0011__table4946919917549>` lists response parameters.

.. _nat_api_0011__table4946919917549:

.. table:: **Table 3** Response parameter

   +-----------+--------+-----------------------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                                         |
   +===========+========+=====================================================================================================+
   | dnat_rule | Object | Specifies the DNAT rule object. For details, see :ref:`Table 4 <nat_api_0011__table1730611321529>`. |
   +-----------+--------+-----------------------------------------------------------------------------------------------------+

.. _nat_api_0011__table1730611321529:

.. table:: **Table 4** Description of the **dnat_rule** field

   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                              |
   +=======================+=======================+==========================================================================================================================================+
   | id                    | String                | Specifies the DNAT rule ID.                                                                                                              |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id             | String                | Specifies the project ID.                                                                                                                |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | nat_gateway_id        | String                | Specifies the NAT gateway ID.                                                                                                            |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | port_id               | String                | Specifies the port ID of an ECS or a BMS. This parameter is used in the VPC scenario. This parameter and **private_ip** are alternative. |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | private_ip            | String                | Specifies the IP address of a Direct Connect connection.                                                                                 |
   |                       |                       |                                                                                                                                          |
   |                       |                       | This parameter is used in the Direct Connect scenario. This parameter and **port_id** are alternative.                                   |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | internal_service_port | Integer               | Specifies the port used by ECSs or BMSs to provide services for external systems.                                                        |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_id        | String                | Specifies the EIP ID.                                                                                                                    |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_address   | String                | Specifies the EIP.                                                                                                                       |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | external_service_port | Integer               | Specifies the port for providing external services.                                                                                      |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | protocol              | String                | Specifies the protocol type. Currently, TCP, UDP, and ANY are supported.                                                                 |
   |                       |                       |                                                                                                                                          |
   |                       |                       | The protocol number of TCP, UDP, and ANY are 6, 17, and 0, respectively.                                                                 |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | -  Specifies the status of the DNAT rule.                                                                                                |
   |                       |                       | -  For details about all its values, see :ref:`Table 1 <nat_api_0042__table1390614366107>`.                                              |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up        | Boolean               | -  Specifies whether the DNAT rule is enabled or disabled.                                                                               |
   |                       |                       | -  The value can be:                                                                                                                     |
   |                       |                       |                                                                                                                                          |
   |                       |                       |    -  **true**: The DNAT rule is enabled.                                                                                                |
   |                       |                       |    -  **false**: The DNAT rule is disabled.                                                                                              |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at            | String                | Specifies when the DNAT rule is created (UTC time). Its value rounds to 6 decimal places for seconds. The format is yyyy-mm-dd hh:mm:ss. |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   #. Create a rule for a specified port.

      .. code-block:: text

         POST https://{Endpoint}/v2.0/dnat_rules
         {
             "dnat_rule": {
                 "floating_ip_id": "bf99c679-9f41-4dac-8513-9c9228e713e1",
                 "nat_gateway_id": "cda3a125-2406-456c-a11f-598e10578541",
                 "port_id": "9a469561-daac-4c94-88f5-39366e5ea193",
                 "internal_service_port": 993,
                 "protocol": "tcp",
                 "external_service_port": 242
             }
         }

   2. Create a rule for all ports.

      .. code-block:: text

         POST https://{Endpoint}/v2.0/dnat_rules
         {
             "dnat_rule": {
                 "floating_ip_id": "Cf99c679-9f41-4dac-8513-9c9228e713e1",
                 "nat_gateway_id": "Dda3a125-2406-456c-a11f-598e10578541",
                 "private_ip": "192.168.1.100",
                 "internal_service_port": 0,
                 "protocol": "any",
                 "external_service_port": 0
             }
         }

-  Example response

   #. Create a response for a specified port.

      .. code-block::

         {
             "dnat_rule": {
                 "floating_ip_id": "bf99c679-9f41-4dac-8513-9c9228e713e1",
                 "status": "ACTIVE",
                 "nat_gateway_id": "cda3a125-2406-456c-a11f-598e10578541",
                 "admin_state_up": true,
                 "port_id": "9a469561-daac-4c94-88f5-39366e5ea193",
                 "internal_service_port": 993,
                 "protocol": "tcp",
                 "tenant_id": "abc",
                 "created_at": "2017-11-15 15:44:42.595173",
                 "id": "79195d50-0271-41f1-bded-4c089b2502ff",
                 "floating_ip_address": "5.21.11.226",
                 "external_service_port": 242,
                 "private_ip": ""
             }
         }

   #. Create a response for all ports.

      .. code-block::

         {
             "dnat_rule": {
                 "floating_ip_id": "cf99c679-9f41-4dac-8513-9c9228e713e1",
                 "status": "ACTIVE",
                 "nat_gateway_id": "dda3a125-2406-456c-a11f-598e10578541",
                 "admin_state_up": true,
                 "private_ip": "192.168.1.100",
                 "internal_service_port": 0,
                 "protocol": "any",
                 "tenant_id": "abc",
                 "created_at": "2017-11-15 15:44:42.595173",
                 "id": "79195d50-0271-41f1-bded-4c089b2502ff",
                 "floating_ip_address": "5.21.11.227",
                 "external_service_port": 0
             }
         }

Status Code
-----------

See :ref:`Status Codes <nat_api_0038>`.
