:original_name: nat_api_0020.html

.. _nat_api_0020:

Querying NAT Gateway Tags
=========================

Function
--------

This API is used to query tags of a specified NAT gateway.

TMS uses this API to query all tags of a specified NAT gateway.

URI
---

GET /v2.0/{project_id}/nat_gateways/{nat_gateway_id}/tags

.. table:: **Table 1** Parameter description

   ============== ========= ====== =============================
   Parameter      Mandatory Type   Description
   ============== ========= ====== =============================
   project_id     Yes       String Specifies the project ID.
   nat_gateway_id Yes       String Specifies the NAT gateway ID.
   ============== ========= ====== =============================

Request
-------

None

Response
--------

:ref:`Table 2 <nat_api_0020__table22681993615>` lists response parameters.

.. _nat_api_0020__table22681993615:

.. table:: **Table 2** Response parameters

   ========= ========= ===== ===============
   Parameter Mandatory Type  Description
   ========= ========= ===== ===============
   tags      Yes       Array Specifies tags.
   ========= ========= ===== ===============

.. table:: **Table 3** Parameter description of field **tags**

   +-----------+-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                                                                                                                                        |
   +===========+===========+========+====================================================================================================================================================================================================================+
   | key       | Yes       | String | Specifies the tag key. It contains a maximum of 36 Unicode characters. It cannot be left empty or contain ASCII characters (0-31) and the following special characters: \*<>\\=                                    |
   +-----------+-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | value     | Yes       | String | Specifies the key value. The value can contain a maximum of 43 Unicode characters and can be an empty string. It cannot contain non-printable ASCII characters (0-31) or the following special characters: \*<>\\= |
   +-----------+-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   .. code-block:: text

      GET https://{VPC_endpoint}/v2.0/9ad601814ac94c80bf7bb9073ded66fc/nat_gateways/fe1a4cf0-27fe-4b97-a9b1-2c67c127f0e0/tags

-  Example response

   .. code-block::

      {
          "tags": [
              {
                  "key": "key1",
                  "value": "value1"
              },
              {
                  "key": "key2",
                  "value": "value2"
              }
          ]
      }

Status Code
-----------

See :ref:`Status Codes <nat_api_0038>`.
