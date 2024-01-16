:original_name: nat_api_0021.html

.. _nat_api_0021:

Querying Tags in a Project
==========================

Function
--------

This API is used to query all tags of a resource type in a specified region.

TMS uses this API to list tags created by a tenant to facilitate tag creation and resource filtering on the console.

URI
---

GET /v2.0/{project_id}/nat_gateways/tags

.. table:: **Table 1** Parameter description

   ========== ========= ====== =========================
   Parameter  Mandatory Type   Description
   ========== ========= ====== =========================
   project_id Yes       String Specifies the project ID.
   ========== ========= ====== =========================

Request
-------

None

Response
--------

:ref:`Table 2 <nat_api_0021__table4116222183715>` lists response parameters.

.. _nat_api_0021__table4116222183715:

.. table:: **Table 2** Response parameters

   ========= ========= ===== ===============
   Parameter Mandatory Type  Description
   ========= ========= ===== ===============
   tags      Yes       Array Specifies tags.
   ========= ========= ===== ===============

.. table:: **Table 3** Parameter description of field **tags**

   +-----------+-----------+---------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type          | Description                                                                                                                                                                                                         |
   +===========+===========+===============+=====================================================================================================================================================================================================================+
   | key       | Yes       | String        | Specifies the tag key. It contains a maximum of 36 Unicode characters. It cannot be left empty or contain ASCII characters (0-31) and the following special characters: \*<>\\=                                     |
   +-----------+-----------+---------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | values    | Yes       | Array<String> | Specifies the tag values. The value can contain a maximum of 43 Unicode characters and can be an empty string. It cannot contain non-printable ASCII characters (0-31) or the following special characters: \*<>\\= |
   +-----------+-----------+---------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   .. code-block:: text

      GET  https://{VPC_endpoint}/v2.0/9ad601814ac94c80bf7bb9073ded66fc/nat_gateways/tags

-  Example response

   .. code-block::

      {
          "tags": [
              {
                  "key": "key1",
                  "values": [
                      "value1",
                      "value2"
                  ]
              },
              {
                  "key": "key2",
                  "values": [
                      "value3",
                      "value4"
                  ]
              }
          ]
      }

Status Code
-----------

See :ref:`Status Codes <nat_api_0038>`.
