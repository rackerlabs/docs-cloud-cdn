=============================================================================
Service Action -  Rackspace CDN Developer Guide for Service Management
=============================================================================

Service Action
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <POST_service_action_admin_services_action.rst#request>`__
`Response <POST_service_action_admin_services_action.rst#response>`__

.. code-block:: javascript

    POST //admin/services/action

Enables, diables, or deletes services for a user account.

To change the operator status of or delete services for a ``project_id``, provide a JSON request body with ``action`` set to ``enable`` or ``disable`` along with the ``project_id`` of the user.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |Accepted                 |The request has been     |
|                          |                         |accepted for processing. |
+--------------------------+-------------------------+-------------------------+


Request
^^^^^^^^^^^^^^^^^









**Example Service Action: JSON request**


.. code::

    POST /v1.0/110011/admin/services/action HTTP/1.1
    Host: global.cdn.api.rackspacecloud.com
    X-Auth-Token: 0f6e9f63600142f0a970911583522217
    Accept: application/json
    Content-type: application/json
    


Response
^^^^^^^^^^^^^^^^^^





**Example Service Action: JSON request**


.. code::

    HTP/1.1 202 (Accepted)
    Location: https://global.cdn.api.rackspacecloud.com/v1.0/admin/services/action

