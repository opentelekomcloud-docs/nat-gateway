:original_name: nat_api_0061.html

.. _nat_api_0061:

Creating a NAT Gateway
======================

Function
--------

This API is used to create a NAT gateway.

URI
---

POST /v2.0/nat_gateways

Request
-------

:ref:`Table 1 <nat_api_0061__table531642713017>` describes the request parameters.

.. _nat_api_0061__table531642713017:

.. table:: **Table 1** Request parameter

   +-------------+-----------+--------+--------------------------------------------------------------------------------------------------------+
   | Parameter   | Mandatory | Type   | Description                                                                                            |
   +=============+===========+========+========================================================================================================+
   | nat_gateway | Yes       | Object | Specifies the NAT gateway object. For details, see :ref:`Table 2 <nat_api_0061__table93481227153014>`. |
   +-------------+-----------+--------+--------------------------------------------------------------------------------------------------------+

.. _nat_api_0061__table93481227153014:

.. table:: **Table 2** Description of the **nat_gateway** field

   +---------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------+
   | Parameter           | Mandatory       | Type            | Description                                                                                        |
   +=====================+=================+=================+====================================================================================================+
   | tenant_id           | No              | String          | Specifies the project ID.                                                                          |
   +---------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------+
   | name                | Yes             | String(64)      | Specifies the NAT gateway name.                                                                    |
   |                     |                 |                 |                                                                                                    |
   |                     |                 |                 | The name can contain only digits, letters, underscores (_), and hyphens (-).                       |
   +---------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------+
   | description         | No              | String(255)     | Provides supplementary information about the NAT gateway.                                          |
   +---------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------+
   | spec                | Yes             | String          | Specifies the NAT gateway type.                                                                    |
   |                     |                 |                 |                                                                                                    |
   |                     |                 |                 | The value can be:                                                                                  |
   |                     |                 |                 |                                                                                                    |
   |                     |                 |                 | -  **1**: small type, which supports up to 10,000 SNAT connections.                                |
   |                     |                 |                 | -  **2**: medium type, which supports up to 50,000 SNAT connections.                               |
   |                     |                 |                 | -  **3**: large type, which supports up to 200,000 SNAT connections.                               |
   |                     |                 |                 | -  **4**: extra-large type, which supports up to 1,000,000 SNAT connections.                       |
   +---------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------+
   | router_id           | Yes             | String          | Specifies the VPC ID.                                                                              |
   +---------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------+
   | internal_network_id | Yes             | String          | Specifies the network ID of the downstream interface (the next hop of the DVR) of the NAT gateway. |
   +---------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------+

Response
--------

:ref:`Table 3 <nat_api_0061__table1899835483516>` lists response parameters.

.. _nat_api_0061__table1899835483516:

.. table:: **Table 3** Response parameter

   +-------------+--------+-------------------------------------------------------------------------------------------------------+
   | Parameter   | Type   | Description                                                                                           |
   +=============+========+=======================================================================================================+
   | nat_gateway | Object | Specifies the NAT gateway object. For details, see :ref:`Table 4 <nat_api_0061__table5998115418352>`. |
   +-------------+--------+-------------------------------------------------------------------------------------------------------+

.. _nat_api_0061__table5998115418352:

.. table:: **Table 4** Description of the **nat_gateway** field

   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                |
   +=======================+=======================+============================================================================================================================================+
   | id                    | String                | Specifies the NAT gateway ID.                                                                                                              |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id             | String                | Specifies the project ID.                                                                                                                  |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | name                  | String(64)            | Specifies the NAT gateway name.                                                                                                            |
   |                       |                       |                                                                                                                                            |
   |                       |                       | The name can contain only digits, letters, underscores (_), and hyphens (-).                                                               |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | description           | String(255)           | Provides supplementary information about the NAT gateway.                                                                                  |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | spec                  | String                | Specifies the NAT gateway type.                                                                                                            |
   |                       |                       |                                                                                                                                            |
   |                       |                       | The value can be:                                                                                                                          |
   |                       |                       |                                                                                                                                            |
   |                       |                       | -  **1**: small type, which supports up to 10,000 SNAT connections.                                                                        |
   |                       |                       | -  **2**: medium type, which supports up to 50,000 SNAT connections.                                                                       |
   |                       |                       | -  **3**: large type, which supports up to 200,000 SNAT connections.                                                                       |
   |                       |                       | -  **4**: extra-large type, which supports up to 1,000,000 SNAT connections.                                                               |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | router_id             | String                | Specifies the router ID.                                                                                                                   |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | internal_network_id   | String                | Specifies the network ID of the downstream interface (the next hop of the DVR) of the NAT gateway.                                         |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | -  Specifies the NAT gateway status.                                                                                                       |
   |                       |                       | -  For details about all its values, see :ref:`Table 1 <nat_api_0042__table1390614366107>`.                                                |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up        | Boolean               | -  Specifies whether the NAT gateway is up or down.                                                                                        |
   |                       |                       | -  The value can be:                                                                                                                       |
   |                       |                       |                                                                                                                                            |
   |                       |                       |    -  **true**: The NAT gateway is up.                                                                                                     |
   |                       |                       |    -  **false**: The NAT gateway is down.                                                                                                  |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at            | String                | Specifies when the NAT gateway is created (UTC time). Its value rounds to 6 decimal places for seconds. The format is yyyy-mm-dd hh:mm:ss. |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   .. code-block:: text

      POST https://{Endpoint}/v2.0/nat_gateways
      {
          "nat_gateway": {
              "name": "nat_001",
              "description": "my nat gateway 01",
              "router_id": "d84f345c-80a1-4fa2-a39c-d0d397c3f09a",
              "internal_network_id": "89d66639-aacb-4929-969d-07080b0f9fd9",
              "spec": "1"
          }
      }

-  Example response

   .. code-block::

      {
          "nat_gateway": {
               "router_id": "d84f345c-80a1-4fa2-a39c-d0d397c3f09a",
               "status": "PENDING_CREATE",
               "description": "my nat gateway 01",
               "admin_state_up": true,
               "tenant_id": "27e25061336f4af590faeabeb7fcd9a3",
               "created_at": "2017-11-18 07:34:32.203044",
               "spec": "1",
               "internal_network_id": "89d66639-aacb-4929-969d-07080b0f9fd9",
               "id": "a78fb3eb-1654-4710-8742-3fc49d5f04f8",
               "name": "nat_001"
          }
      }

Status Code
-----------

See :ref:`Status Codes <nat_api_0038>`.
