:original_name: nat_api_0063.html

.. _nat_api_0063:

Introduction
============

This section describes fine-grained permissions management for your NAT gateways. If your account does not need individual IAM users, then you may skip this section.

By default, new IAM users do not have permissions assigned. You need to add a user to one or more groups and attach permissions policies to these groups. The users then inherit permissions from the groups and can perform specified operations on cloud services based on the permissions they have been assigned.

.. note::

   Policy-based authorization is useful if you want to allow or deny the access to an API.

An account has all of the permissions required to call all APIs, but IAM users must have the required permissions specifically assigned. The permissions required for calling an API are determined by the actions supported by the API. Only users who have been granted permissions allowing the actions can call the API successfully. For example, if an IAM user wants to query NAT gateways using an API, the user must have been granted permissions that allow the **nat:natGateways:list** action.

Supported Actions
-----------------

NAT Gateway provides system-defined policies, which can be directly used in IAM. The account administrator can also create custom policies to supplement system-defined policies for more refined access control. Operations supported by policies are specific to APIs. The following are common concepts related to policies:

-  Permissions: Statements in a policy that allow or deny certain operations.
-  APIs: REST APIs that can be called by a user who has been granted specific permissions.
-  Actions: Specific operations that are allowed or denied.
-  IAM or enterprise projects: Type of projects for which an action will take effect. Policies that contain actions for both IAM and enterprise projects can be used and take effect for both IAM and Enterprise Management. Policies that only contain actions for IAM projects can be used and only take effect for IAM. The account administrator can check whether an action supports IAM projects or enterprise projects in the action list. The check mark (Y) indicates that the action supports the project and the cross symbol (x) indicates that the action does not support the project.

.. note::

   Private NAT gateways do not have dedicated permissions, please use public NAT gateway roles/policies.

NAT Gateway supports the following actions that can be defined in custom policies:

-  :ref:`NAT Gateway v2.0 <nat_api_0032>`, including actions supported by all APIs of NAT Gateway, such as creating, updating, and deleting a NAT gateway.
-  :ref:`SNAT Rule v2.0 <nat_api_0033>`, including actions supported by all APIs of the SNAT rule, such as creating an SNAT rule and querying SNAT rules.
-  :ref:`DNAT Rule v2.0 <nat_api_0034>`, including actions supported by all APIs of the DNAT rule, such as creating a DNAT rule and querying DNAT rules.
-  :ref:`NAT Gateway Tag v2.0 <nat_api_0035>`, including actions supported by NAT Gateway tags, such as adding a tag to a NAT gateway and querying NAT gateway tags.
