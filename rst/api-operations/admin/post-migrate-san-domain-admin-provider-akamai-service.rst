
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

=============================================================================
Migrate San Domain -  Rackspace CDN Developer Guide for Service Management
=============================================================================

Migrate San Domain
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <post-migrate-san-domain-admin-provider-akamai-service.html#request>`__
`Response <post-migrate-san-domain-admin-provider-akamai-service.html#response>`__

.. code::

    POST //admin/provider/akamai/service

Updates the domain with a new SAN URL.

This operation updates the domain with a new SAN URL.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+


Request
^^^^^^^^^^^^^^^^^









**Example Migrate San Domain: JSON request**


.. code::

    POST /v1.0/110011/admin/provider/akamai/service HTTP1.1
    Host: global.cdn.api.rackspacecloud.com
    X-Auth-Token: 0f6e9f63600142f0a970911583522217
    Accept: application/json
    Content-type: application/json
    


Response
^^^^^^^^^^^^^^^^^^





**Example Migrate San Domain: JSON response**


.. code::

    HTP/1.1 202 (Accepted)
    Location: https://global.cdn.api.rackspacecloud.com/v1.0/admin/provider/akamai/service

