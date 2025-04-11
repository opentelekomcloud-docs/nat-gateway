:original_name: nat_permission_0000.html

.. _nat_permission_0000:

Permissions Management
======================

If you need to grant your enterprise personnel permission to access your NAT Gateway resources, use Identity and Access Management (IAM). IAM provides identity authentication, fine-grained permissions management, and access control. IAM helps you secure access to your resources.

With IAM, you can create IAM users and grant them permissions to access only specific resources. For example, if you want some software developers in your enterprise to be able to use NAT Gateway resources but do not want them to be able to delete NAT gateways or perform any other high-risk operations, you can create IAM users and grant permission to use NAT gateways but not permission to delete them.

If your account does not require individual IAM users for permissions management, you can skip this section.

IAM is a free service. You only pay for the resources in your account. For more information about IAM, see `What Is IAM? <https://docs.otc.t-systems.com/identity-access-management/umn/service_overview/index.html>`__

NAT Gateway Permissions
-----------------------

New IAM users do not have any permissions assigned by default. You need to first add them to one or more groups and then attach policies or roles to these groups. The users then inherit permissions from the groups and can perform specified operations on cloud services based on the permissions they have been assigned.

NAT Gateway is a project-level service deployed for specific regions. To assign NAT Gateway permissions to a user group, specify the scope as region-specific projects and select projects for which you want the permissions to take effect. If you select **All projects**, the permissions will take effect for the user group in all region-specific projects. When accessing NAT gateways, the users need to switch to the authorized region.

You can grant users permissions by using roles and policies.

-  Roles: A coarse-grained authorization strategy that defines permissions by job responsibility. Only a limited number of service-level roles are available for authorization. Cloud services often depend on each other. When you grant permissions using roles, you also need to attach any existing role dependencies. Roles are not ideal for fine-grained authorization and least privilege access.

-  Policies: A fine-grained authorization strategy that defines permissions required to perform operations on specific cloud resources under certain conditions. This type of authorization is more flexible and is ideal for least privilege access. For example, you can grant users only permission to manage a certain type of NAT gateways. A majority of fine-grained policies contain permissions for specific APIs, and permissions are defined using API actions. For the API actions supported by NAT Gateway, see section "Permissions Policies and Supported Actions" in the *NAT Gateway API Reference*.

:ref:`Table 1 <nat_permission_0000__en-us_topic_0201532969_table2073410015487>` lists all the system-defined permissions for NAT Gateway.

.. _nat_permission_0000__en-us_topic_0201532969_table2073410015487:

.. table:: **Table 1** System-defined permissions for NAT Gateway

   +---------------------------+--------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Policy Name               | Description                                                                                                                    | Type                  |
   +===========================+================================================================================================================================+=======================+
   | NAT FullAccess            | All operations on NAT Gateway resources.                                                                                       | System-defined policy |
   +---------------------------+--------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | NAT ReadOnlyAccess        | Read-only permissions for all NAT Gateway resources.                                                                           | System-defined policy |
   +---------------------------+--------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | NAT Gateway Administrator | All operations on NAT Gateway resources. To be granted this permission, users must also have the **Tenant Guest** permissions. | System-defined role   |
   +---------------------------+--------------------------------------------------------------------------------------------------------------------------------+-----------------------+

:ref:`Table 2 <nat_permission_0000__en-us_topic_0201532969_en-us_topic_0171003465_table26611439131>` lists the common operations supported by each NAT Gateway system policy or role. Select the policies or roles as required.

.. _nat_permission_0000__en-us_topic_0201532969_en-us_topic_0171003465_table26611439131:

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

      -  If you set **Instance Type** to **Server** and select an ECS, you also need to obtain the **ECS ReadOnlyAccess** permissions or the fine-grained permissions for actions **ecs:cloudServers:get** and **ecs:cloudServers:list**. For details, see the *Elastic Cloud Server API Reference*.
      -  If you set **Instance Type** to **Server** and select a BMS, you also need to obtain the **BMS ReadOnlyAccess** permissions or the fine-grained permissions for actions **bms:servers:get** and **bms:servers:list**. For details, see the *Bare Metal Server API Reference*.
      -  If you create a DNAT rule on a private NAT gateway and select **Load balancer** for **Instance Type**, you need to obtain the **ELB ReadOnlyAccess** permissions or the fine-grained permissions for actions **elb:loadbalancers:get** and **elb:loadbalancers:list**. For details, see the *Elastic Load Balance API Reference*.
      -  After a DNAT rule is created, add a security group rule to allow the Internet to access servers for which the DNAT rule is configured. Otherwise, the DNAT rule does not take effect. Obtain the **VPC FullAccess** permissions or the fine-grained permissions for action **vpc:securityGroups:create** by referring to the *Virtual Private Cloud API Reference*.

   -  To view metrics, obtain the **CES ReadOnlyAccess** permissions. For details, see the *Cloud Eye API Reference*.
   -  To view access logs, obtain the **LTS ReadOnlyAccess** permissions. For details, see the *Log Tank Service API Reference*.
   -  To query predefined tags, obtain the **TMS** **Administrator** permissions. For details, see the *Tag Management Service API Reference*.
