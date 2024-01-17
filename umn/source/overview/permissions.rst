:original_name: nat_permission_0000.html

.. _nat_permission_0000:

Permissions
===========

You can use Identity and Access Management (IAM) to manage NAT Gateway permissions and control access to your resources. IAM provides identity authentication, permissions management, and access control.

You can create IAM users for your employees, and assign permissions to these users on a principle of least privilege (PoLP) basis to control their access to specific resource types. For example, you can create IAM users for software developers and assign specific permissions to allow them to use NAT Gateway resources but prevent them from being able to delete resources or perform any high-risk operations.

If your does not require individual IAM users, skip this section.

IAM can be used free of charge. You pay only for the resources in your account. For more information about IAM, see `What Is IAM? <https://docs.otc.t-systems.com/identity-access-management/umn/service_overview/index.html>`__

NAT Gateway Permissions
-----------------------

By default, new IAM users do not have any permissions assigned. To assign permissions to these new users, the administrator needs to add them to one or more groups, and attach permissions policies or roles to these groups.

NAT Gateway is a project-level service deployed and accessed in specific physical regions. When assigning NAT Gateway permissions to a user group, specify region-specific projects where the permissions will take effect. If you select **All projects**, the permissions will be granted for all region-specific projects. When accessing NAT Gateway, the users need to switch to a region where they have been authorized to use this service.

You can grant users permissions by using roles and policies.

-  Roles: A type of coarse-grained authorization mechanism that provides only a limited number of service-level roles. When using roles to grant permissions, you also need to assign dependency roles. However, roles are not an ideal choice for fine-grained authorization and secure access control.

-  Policies: A type of fine-grained authorization mechanism that defines permissions required to perform operations on specific cloud resources under certain conditions. This mechanism allows for more flexible policy-based authorization for more secure access control. For example, the administrator can grant NAT Gateway users only the permissions for managing a certain type of NAT gateways and SNAT rules. Most policies define permissions based on APIs. For the API actions supported by NAT Gateway, see section "Permissions Policies and Supported Actions" in the *NAT Gateway API Reference*.

:ref:`Table 1 <nat_permission_0000__table2073410015487>` lists all the system-defined roles and policies supported by NAT Gateway.

.. _nat_permission_0000__table2073410015487:

.. table:: **Table 1** System-defined roles and policies supported by NAT Gateway

   +---------------------------+----------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Policy Name               | Description                                                                                                                      | Type                  |
   +===========================+==================================================================================================================================+=======================+
   | NAT FullAccess            | All operations on NAT Gateway resources.                                                                                         | System-defined policy |
   +---------------------------+----------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | NAT ReadOnlyAccess        | Read-only permissions for all NAT Gateway resources.                                                                             | System-defined policy |
   +---------------------------+----------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | NAT Gateway Administrator | Full permissions for all NAT Gateway resources. Users granted these permissions must also have the **Tenant Guest** permissions. | System-defined role   |
   +---------------------------+----------------------------------------------------------------------------------------------------------------------------------+-----------------------+

:ref:`Table 2 <nat_permission_0000__en-us_topic_0171003465_table26611439131>` lists the common operations supported by each NAT Gateway system policy or role. Select the policies or roles as required.

.. _nat_permission_0000__en-us_topic_0171003465_table26611439131:

.. table:: **Table 2** Common operations supported by each system-defined policy or role of NAT Gateway

   +------------------------------+----------------+--------------------+---------------------------+
   | Operation                    | NAT FullAccess | NAT ReadOnlyAccess | NAT Gateway Administrator |
   +==============================+================+====================+===========================+
   | Creating a NAT gateway       | Y              | x                  | Y                         |
   +------------------------------+----------------+--------------------+---------------------------+
   | Querying NAT gateways        | Y              | Y                  | Y                         |
   +------------------------------+----------------+--------------------+---------------------------+
   | Querying NAT gateway details | Y              | Y                  | Y                         |
   +------------------------------+----------------+--------------------+---------------------------+
   | Updating a NAT gateway       | Y              | x                  | Y                         |
   +------------------------------+----------------+--------------------+---------------------------+
   | Deleting a NAT gateway       | Y              | x                  | Y                         |
   +------------------------------+----------------+--------------------+---------------------------+
   | Adding an SNAT rule          | Y              | x                  | Y                         |
   +------------------------------+----------------+--------------------+---------------------------+
   | Viewing an SNAT rule         | Y              | Y                  | Y                         |
   +------------------------------+----------------+--------------------+---------------------------+
   | Modifying an SNAT rule       | Y              | x                  | Y                         |
   +------------------------------+----------------+--------------------+---------------------------+
   | Deleting an SNAT rule        | Y              | x                  | Y                         |
   +------------------------------+----------------+--------------------+---------------------------+
   | Adding a DNAT rule           | Y              | x                  | Y                         |
   +------------------------------+----------------+--------------------+---------------------------+
   | Viewing a DNAT rule          | Y              | Y                  | Y                         |
   +------------------------------+----------------+--------------------+---------------------------+
   | Modifying a DNAT rule        | Y              | x                  | Y                         |
   +------------------------------+----------------+--------------------+---------------------------+
   | Deleting a DNAT rule         | Y              | x                  | Y                         |
   +------------------------------+----------------+--------------------+---------------------------+

.. note::

   -  Note the following when creating a DNAT rule:

      -  If you set **Instance Type** to **Server** and select an ECS, you also need to obtain the **ECS ReadOnlyAccess** permissions or the fine-grained permissions for action **ecs:cloudServers:get** and action **ecs:cloudServers:list**. For details, see the *Elastic Cloud Server API Reference*.
      -  If you set **Instance Type** to **Server** and select a BMS, you also need to obtain the **BMS ReadOnlyAccess** permissions or the fine-grained permissions for action **bms:servers:get** and action **bms:servers:list**. For details, see the *Bare Metal Server API Reference*.
      -  After a DNAT rule is created, add a security group rule to allow the Internet to access servers for which the DNAT rule is configured. Otherwise, the DNAT rule does not take effect. Obtain the **VPC FullAccess** permissions or the fine-grained permissions for action **vpc:securityGroups:create** by referring to the *Virtual Private Cloud API Reference*.

.. note::

   -  To view metrics, obtain the **CES ReadOnlyAccess** permissions. For details, see the *Cloud Eye API Reference*.
   -  To view access logs, obtain the **LTS ReadOnlyAccess** permissions. For details, see the *Log Tank Service API Reference*.
   -  To query predefined tags, obtain the **TMS** **Administrator** permissions. For details, see the *Tag Management Service API Reference*.

Helpful Links
-------------

-  `What Is IAM? <https://docs.otc.t-systems.com/identity-access-management/umn/service_overview/index.html>`__
-  :ref:`Creating a User and Granting NAT Gateway Permissions <nat_permission_0002>`
