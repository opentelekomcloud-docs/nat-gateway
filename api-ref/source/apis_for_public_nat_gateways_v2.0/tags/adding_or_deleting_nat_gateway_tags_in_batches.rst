:original_name: nat_api_0017.html

.. _nat_api_0017:

Adding or Deleting NAT Gateway Tags in Batches
==============================================

Function
--------

This API is used to add or delete tags of a specific NAT gateway in batches.

TMS uses this API to manage service resource tags.

You can add a maximum of 20 tags to a NAT gateway.

This API is idempotent.

If there are duplicate keys in the request body when you add tags, an error is reported.

If a to-be-created tag has the same key as an existing tag, the tag will be created and overwrite the existing one.

When tags are being deleted and some tags do not exist, the operation is considered successful by default. The character set of the tags will not be checked. A key and a value can respectively contain up to 127 and 255 Unicode characters. When you delete tags, the tag structure cannot be missing, and the key cannot be left blank or be an empty string.

URI
---

-  URI format

POST /v2.0/{project_id}/nat_gateways/{nat_gateway_id}/tags/action

.. table:: **Table 1** Parameter description

   ============== ========= ====== =============================
   Parameter      Mandatory Type   Description
   ============== ========= ====== =============================
   project_id     Yes       String Specifies the project ID.
   nat_gateway_id Yes       String Specifies the NAT gateway ID.
   ============== ========= ====== =============================

Request
-------

:ref:`Table 2 <nat_api_0017__table57458431295>` describes the request parameters.

.. _nat_api_0017__table57458431295:

.. table:: **Table 2** Request parameters

   +-----------+-----------+--------+-------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                     |
   +===========+===========+========+=================================================================================================+
   | tags      | Yes       | Array  | Specifies tags. For details, see :ref:`Table 3 <nat_api_0017__table9760114311291>`.             |
   +-----------+-----------+--------+-------------------------------------------------------------------------------------------------+
   | action    | Yes       | String | Specifies the operation to be performed. The value can be set to **create** or **delete** only. |
   +-----------+-----------+--------+-------------------------------------------------------------------------------------------------+

.. _nat_api_0017__table9760114311291:

.. table:: **Table 3** Parameter description of field **tags**

   +-----------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                                                                                                                                                                                                                                                 |
   +===========+===========+========+=============================================================================================================================================================================================================================================================================================================================+
   | key       | Yes       | String | Specifies the tag key. It contains a maximum of 36 Unicode characters. This parameter cannot be left blank or contain ASCII (0-31) or the following characters: ``=*<>\,|/``                                                                                                                                                |
   +-----------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | value     | Yes       | String | Specifies the key value. Each value contains a maximum of 43 Unicode characters. If **value** is specified, tags are deleted by key and value. If **value** is not specified, tags are deleted by key. The value can be an empty character string. It cannot contain ASCII (0-31) or the following characters: ``=*<>\,|/`` |
   +-----------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

None

Examples
--------

-  Example request

   .. code-block:: text

      POST  https://{VPC_endpoint}/v2.0/9ad601814ac94c80bf7bb9073ded66fc/nat_gateways/fe1a4cf0-27fe-4b97-a9b1-2c67c127f0e0/tags/action
      {
          "action": "create",
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
      Or
      {
          "action": "delete",
          "tags": [
              {
                  "key": "key1",
                  "value": "value1
               },
              {
                  "key": "key2",
                  "value": "value2"
              }
          ]
      }

Example response
----------------

None

Status Code
-----------

See :ref:`Status Codes <nat_api_0038>`.
