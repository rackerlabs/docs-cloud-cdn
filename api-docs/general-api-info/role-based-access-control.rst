.. _role-based-access-control:

Role Based Access Control
~~~~~~~~~~~~~~~~~~~~~~~~~

Role Based Access Control (RBAC) restricts access to the capabilities of
Rackspace Cloud services, including the Rackspace CDN API, to authorized
users only. RBAC enables Rackspace Cloud customers to specify which account
users of their Cloud account have access to which Rackspace CDN API service
capabilities, based on
:ref:`roles defined by Rackspace <cdn-dg-rbac-available>`.

The permissions to perform certain operations in Rackspace CDN API – create,
read, update, delete – are assigned to specific roles, and these roles can be
assigned by the Cloud account admin user to account users of the account.


Assigning roles to account users
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The account owner (identity:user-admin) can create account users on the account
and then assign roles to those users. The roles grant the account users
specific permissions for accessing the capabilities of the Rackspace CDN
service. Each account has only one account owner, and that role is assigned by
default to any Rackspace Cloud account when the account is created.

See the
:rax-devguide:`Cloud Identity Client Developer Guide <cloud-identity/v2>` for
information about how to perform these tasks:

* :rax-devdocs:`Add user <cloud-identity/v2/developer-guide/#add-user>`

* :rax-devdocs:`Add role to user <cloud-identity/v2/developer-guide/#add-role-to-user>`

* :rax-devdocs:`Delete global role from user <cloud-identity/v2/developer-guide/#delete-global-role-from-user>`

..  note::
    The account admin user (identity:user-admin) role cannot hold any
    additional roles because it already has full access to all capabilities
    by default.

.. _cdn-dg-rbac-available:

Roles available for Rackspace CDN
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Three roles (admin, creator, and observer) can be used to access the Rackspace
CDN API specifically. The following table describes these roles and their
permissions.

+--------------------------------------+--------------------------------------+
| Role name                            | Role permissions                     |
+======================================+======================================+
| cdn:admin                            | This role provides Create, Read,     |
|                                      | Update, and Delete permissions in    |
|                                      | Rackspace CDN, where access is       |
|                                      | granted.                             |
+--------------------------------------+--------------------------------------+
| cdn:creator                          | This role provides Create, Read and  |
|                                      | Update permissions in Rackspace      |
|                                      | CDN, where access is granted.        |
+--------------------------------------+--------------------------------------+
| cdn:observer                         | This role provides Read permission   |
|                                      | in Rackspace CDN, where access is    |
|                                      | granted.                             |
+--------------------------------------+--------------------------------------+

Additionally, two multiproduct roles apply to all products. Users with
multiproduct roles inherit access to future products when those products become
RBAC-enabled. The following table describes these roles and their permissions.

+--------------------------------------+--------------------------------------+
| Role name                            | Role permissions                     |
+======================================+======================================+
| admin                                | This role provides Create, Read,     |
|                                      | Update, and Delete permissions in    |
|                                      | all products, where access is        |
|                                      | granted.                             |
+--------------------------------------+--------------------------------------+
| observer                             | This role provides Read permission   |
|                                      | in all products, where access is     |
|                                      | granted.                             |
+--------------------------------------+--------------------------------------+


Resolving conflicts between RBAC multiproduct vs. custom (product-specific) roles
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The account owner can set roles for both multiproduct and Rackspace CDN scope,
and it is important to understand how any potential conflicts among these roles
are resolved. When two roles appear to conflict, the role that provides the
more extensive permissions takes precedence. Therefore, admin roles take
precedence over observer and creator roles, because admin roles provide more
permissions.

The following table shows two examples of how potential conflicts between user
roles in the Control Panel are resolved:

+--------------------------+----------------------+-------------------------+
| Permission configuration | View of permission   | Can the user perform    |
|                          | in the Control Panel | product admin functions |
|                          |                      | in the Control Panel?   |
+==========================+======================+=========================+
| User is assigned the     | Appears that the     | Yes, for Rackspace CDN  |
| following roles:         | user has only the    | only. The user has the  |
| multiproduct observer    | multiproduct         | observer role for the   |
| and Rackspace CDN  admin | observer role        | rest of the products.   |
+--------------------------+----------------------+-------------------------+
| User is assigned the     | Appears that the     | Yes, for all of the     |
| following roles:         | user has only the    | products. The Rackspace |
| multiproduct admin and   | multiproduct admin   | CDN observer role is    |
| Rackspace CDN  observer  | role                 | ignored.                |
+--------------------------+----------------------+-------------------------+

RBAC permissions cross-reference to Rackspace CDN API operations
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

API operations for Rackspace CDN may or may not be available to all roles. To
see which operations are permitted to invoke which calls, review
:how-to:`Permissions Matrix for Role Based Access Control<permissions-matrix-for-role-based-access-control-rbac>`.
