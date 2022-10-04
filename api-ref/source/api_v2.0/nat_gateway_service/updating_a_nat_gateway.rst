:original_name: nat_api_0003.html

.. _nat_api_0003:

Updating a NAT Gateway
======================

Function
--------

This API is used to update a NAT gateway.

.. note::

   **admin_state_up = True & status = "ACTIVE"** can be updated. The name, description, and type of a NAT gateway can be updated.

URI
---

PUT /v2.0/nat_gateways/{nat_gateway_id}

.. table:: **Table 1** Parameter description

   ============== ====== ========= =============================
   Parameter      Type   Mandatory Description
   ============== ====== ========= =============================
   nat_gateway_id String Yes       Specifies the NAT gateway ID.
   ============== ====== ========= =============================

Request
-------

:ref:`Table 2 <nat_api_0003__table52686130>` describes the request parameters.

.. _nat_api_0003__table52686130:

.. table:: **Table 2** Request parameters

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                |
   +=================+=================+=================+============================================================================================================================================================================+
   | nat_gateway     | Yes             | Object          | Specifies the NAT gateway object. For details, see :ref:`Table 3 <nat_api_0003__table0906373491>`.                                                                         |
   |                 |                 |                 |                                                                                                                                                                            |
   |                 |                 |                 | Mandatory field: None. Only the **name**, **description**, and **spec** fields can be updated. At least one attribute must be specified for the NAT gateway to be updated. |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _nat_api_0003__table0906373491:

.. table:: **Table 3** Description of the **nat_gateway** field

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                  |
   +=================+=================+=================+==============================================================================+
   | name            | No              | String(64)      | Specifies the NAT gateway name.                                              |
   |                 |                 |                 |                                                                              |
   |                 |                 |                 | The name can contain only digits, letters, underscores (_), and hyphens (-). |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------+
   | description     | No              | String(255)     | Provides supplementary information about the NAT gateway.                    |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------+
   | spec            | No              | String          | Specifies the NAT gateway type.                                              |
   |                 |                 |                 |                                                                              |
   |                 |                 |                 | The value can be:                                                            |
   |                 |                 |                 |                                                                              |
   |                 |                 |                 | -  **0**: micro type, which supports up to 1,000 SNAT connections.           |
   |                 |                 |                 |                                                                              |
   |                 |                 |                 | -  **1**: small type, which supports up to 10,000 SNAT connections.          |
   |                 |                 |                 | -  **2**: medium type, which supports up to 50,000 SNAT connections.         |
   |                 |                 |                 | -  **3**: large type, which supports up to 200,000 SNAT connections.         |
   |                 |                 |                 | -  **4**: extra-large type, which supports up to 1,000,000 SNAT connections. |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------+

Response
--------

:ref:`Table 4 <nat_api_0003__table26619133>` lists response parameters.

.. _nat_api_0003__table26619133:

.. table:: **Table 4** Response parameters

   +-------------+--------+------------------------------------------------------------------------------------------------------+
   | Parameter   | Type   | Description                                                                                          |
   +=============+========+======================================================================================================+
   | nat_gateway | Object | Specifies the NAT gateway object. For details, see :ref:`Table 5 <nat_api_0003__table144824405116>`. |
   +-------------+--------+------------------------------------------------------------------------------------------------------+

.. _nat_api_0003__table144824405116:

.. table:: **Table 5** Description of the **nat_gateway** field

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
   |                       |                       | -  **0**: micro type, which supports up to 1,000 SNAT connections.                                                                         |
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
   | status                | String                | -  Specifies the status of the NAT gateway.                                                                                                |
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

      PUT https://{Endpoint}/v2.0/nat_gateways/a78fb3eb-1654-4710-8742-3fc49d5f04f8
        {
          "nat_gateway": {
              "name": "new_name",
              "description": "new description",
              "spec": "1"
          }
      }

-  Example response

   .. code-block::

      {
          "nat_gateway": {
              "router_id": "d84f345c-80a1-4fa2-a39c-d0d397c3f09a",
               "status": "ACTIVE",
               "description": "new description",
               "admin_state_up": true,
               "tenant_id": "27e25061336f4af590faeabeb7fcd9a3",
               "created_at": "2017-11-18 07:34:32.203044",
               "spec": "1",
               "internal_network_id": "89d66639-aacb-4929-969d-07080b0f9fd9",
               "id": "a78fb3eb-1654-4710-8742-3fc49d5f04f8",
               "name": "new_name"
          }
      }

Status Code
-----------

See :ref:`Status Codes <nat_api_0038>`.
