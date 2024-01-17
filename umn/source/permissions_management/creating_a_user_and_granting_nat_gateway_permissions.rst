:original_name: nat_permission_0002.html

.. _nat_permission_0002:

Creating a User and Granting NAT Gateway Permissions
====================================================

This section describes how to use `IAM <https://docs.otc.t-systems.com/identity-access-management/umn/index.html>`__ to implement fine-grained permissions control for your NAT Gateway resources. With IAM, you can:

-  Create IAM users for employees based on your enterprise's organizational structure. Each IAM user will have their own security credentials for accessing NAT Gateway resources.
-  Grant only the permissions required for users to perform a specific task.
-  Entrust an account or cloud service to perform efficient O&M on your NAT Gateway resources.

If your account does not require individual IAM users, skip this section.

This section describes the procedure for granting permissions (see :ref:`Figure 1 <nat_permission_0002__en-us_topic_0171158980_fig111743404535>`).

Prerequisites
-------------

Learn about the permissions supported by NAT Gateway and choose policies or roles according to your requirements. For details, see :ref:`Permissions <nat_permission_0000>`. For the permissions of other services, see `Permissions <https://docs.otc.t-systems.com/additional/permissions.html>`__.

Process Flow
------------

.. _nat_permission_0002__en-us_topic_0171158980_fig111743404535:

.. figure:: /_static/images/en-us_image_0201532839.jpg
   :alt: **Figure 1** Process for granting NAT Gateway permissions

   **Figure 1** Process for granting NAT Gateway permissions

#. .. _nat_permission_0002__en-us_topic_0171158980_li527593485415:

   `Create a user group and assign permissions <https://docs.otc.t-systems.com/identity-access-management/umn/getting_started/creating_a_user_group_and_assigning_permissions.html>`__.

   Create a user group on the IAM console, and attach the policy to the group.

#. `Create an IAM user and add it to a user group. <https://docs.otc.t-systems.com/identity-access-management/umn/getting_started/creating_a_user_and_adding_the_user_to_a_user_group.html>`__

   Create a user on the IAM console and add the user to the group created in :ref:`1 <nat_permission_0002__en-us_topic_0171158980_li527593485415>`.

#. `Log in <https://docs.otc.t-systems.com/identity-access-management/umn/getting_started/logging_in_as_a_user.html>`__ and verify permissions.

   Log in to the management console as the created user. Switch to the authorized region and verify the permissions.

   -  Choose **Service List** > **NAT Gateway**. Then click **Create** **NAT Gateway**. If a message appears indicating that you have insufficient permissions to perform the operation, the **ReadOnlyAccess** policy has already taken effect.
   -  Choose any other service in **Service List**. If a message appears indicating that you have insufficient permissions to access the service, the **NAT ReadOnlyAccess** policy has already taken effect.
