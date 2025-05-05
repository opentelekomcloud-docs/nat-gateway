:original_name: DeleteTransitIp.html

.. _DeleteTransitIp:

Releasing a Transit IP Address
==============================

Function
--------

This API is used to release a transit IP address.

URI
---

DELETE /v3/{project_id}/private-nat/transit-ips/{transit_ip_id}

.. table:: **Table 1** Path Parameters

   +---------------+-----------+--------+---------------------------------------------+
   | Parameter     | Mandatory | Type   | Description                                 |
   +===============+===========+========+=============================================+
   | transit_ip_id | Yes       | String | Specifies the ID of the transit IP address. |
   +---------------+-----------+--------+---------------------------------------------+
   | project_id    | Yes       | String | Specifies the project ID.                   |
   +---------------+-----------+--------+---------------------------------------------+

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                             |
   +=================+=================+=================+=========================================================================================================================+
   | X-Auth-Token    | Yes             | String          | Specifies the user token.                                                                                               |
   |                 |                 |                 |                                                                                                                         |
   |                 |                 |                 | It is a response to the API used to obtain a user token. This API is the only one that does not require authentication. |
   |                 |                 |                 |                                                                                                                         |
   |                 |                 |                 | The value of **X-Subject-Token** in the response header is the token value.                                             |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 204**

Transit IP address released.

None

Example Requests
----------------

.. code-block:: text

   DELETE https://{Endpoint}/v3/da261828016849188f4dcc2ef94d9da9/private-nat/transit-ips/a2845109-3b2f-4627-b08f-09a726c0a6e7

Example Responses
-----------------

None

Status Codes
------------

=========== ============================
Status Code Description
=========== ============================
204         Transit IP address released.
=========== ============================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
