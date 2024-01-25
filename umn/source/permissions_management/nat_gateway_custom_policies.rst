:original_name: nat_permission_0003.html

.. _nat_permission_0003:

NAT Gateway Custom Policies
===========================

Custom policies can be created to supplement the system-defined policies of NAT Gateway. For the actions that can be added to custom policies, see section "Permissions Policies and Supported Actions" in the *NAT Gateway API Reference*.

You can create custom policies in either of the following ways:

-  Visual editor: Select cloud services, actions, resources, and request conditions. This does not require knowledge of policy syntax.

-  JSON: Edit JSON policies from scratch or based on an existing policy.

   For details, see `Creating a Custom Policy <https://docs.otc.t-systems.com/identity-access-management/umn/user_guide/fine-grained_policy_management/creating_a_custom_policy.html>`__ The following section contains examples of common NAT Gateway custom policies.

Example Policies
----------------

-  Example 1: Allowing users to create and delete NAT gateways

   .. code-block::

      {
            "Version": "1.1",
            "Statement": [
                  {
                        "Effect": "Allow",
                        "Action": [
                              "nat:natGateways:create",
                              "nat:natGateways:delete"
                        ]
                  }
            ]
      }

-  Example 2: Denying NAT gateway deletion

   A deny policy must be used in conjunction with other policies to take effect. If the permissions assigned to a user contain both "Allow" and "Deny", the "Deny" permissions take precedence over the "Allow" permissions.

   The following method can be used if you need to assign permissions of the NAT Gateway **FullAccess** policy to a user but also forbid the user from deleting NAT gateways. Create a custom policy for denying NAT gateway deletion, and attach both policies to the group to which the user belongs. Then the user can perform all operations on NAT gateways except deleting NAT gateways. The following is an example of a deny policy:

   .. code-block::

      {
              "Version": "1.1",
              "Statement": [
                      {
                              "Action": [
                                      "nat:natGateways:delete"
                              ],
                              "Effect": "Deny"
                      }
              ]
      }

-  Example 3: Defining permissions for multiple services in a policy

   A custom policy can contain actions of multiple services that are of the global or project-level type. The following is an example policy containing actions of multiple services:

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Action": [
                      "nat:natGateways:update",
                      "nat:natGateways:create"
                  ],
                  "Effect": "Allow"
              },
              {
                  "Action": [
                      "vpc:vpcs:update"
                  ],
                  "Effect": "Allow"
              }
          ]
      }
