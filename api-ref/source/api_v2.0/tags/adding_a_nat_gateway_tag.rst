:original_name: nat_api_0018.html

.. _nat_api_0018:

Adding a NAT Gateway Tag
========================

Function
--------

This API is used to add tags to a NAT gateway. You can add a maximum of 20 tags to a NAT gateway.

This API is idempotent.

If a to-be-created tag has the same key as an existing tag, the tag will be created and overwrite the existing one.

.. note::

   Ensure that the NAT gateway which you add the tag to exists.

URI
---

POST /v2.0/{project_id}/nat_gateways/{nat_gateway_id}/tags

.. table:: **Table 1** Parameter description

   ============== ========= ====== =============================
   Parameter      Mandatory Type   Description
   ============== ========= ====== =============================
   project_id     Yes       String Specifies the project ID.
   nat_gateway_id Yes       String Specifies the NAT gateway ID.
   ============== ========= ====== =============================

Request
-------

:ref:`Table 2 <nat_api_0018__table78225323114>` describes the request parameters.

.. _nat_api_0018__table78225323114:

.. table:: **Table 2** Request parameters

   ========= ========= ===== ===========================
   Parameter Mandatory Type  Description
   ========= ========= ===== ===========================
   tag       Yes       Array Specifies the list of tags.
   ========= ========= ===== ===========================

.. table:: **Table 3** Description of field **tag**

   +-----------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                                                                                                            |
   +===========+===========+========+========================================================================================================================================================================================+
   | key       | Yes       | String | Specifies the tag key. It contains a maximum of 36 Unicode characters. This parameter cannot be left blank or contain ASCII (0-31) or the following characters: ``=*<>\,|/``           |
   +-----------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | value     | Yes       | String | Specifies the key value. The value can contain a maximum of 43 Unicode characters and can be an empty string. It cannot contain ASCII (0-31) or the following characters: ``=*<>\,|/`` |
   +-----------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

None

Examples
--------

-  Example request

   .. code-block:: text

      POST  https://{VPC_endpoint}/v2.0/9ad601814ac94c80bf7bb9073ded66fc/nat_gateways/fe1a4cf0-27fe-4b97-a9b1-2c67c127f0e0/tags
      {
           "tag":
          {
              "key":"key1",
              "value":"value1"
          }
      }

Status Code
-----------

See :ref:`Status Codes <nat_api_0038>`.
