
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Migrate SAN domain
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

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
""""""""""""""""








This operation does not accept a request body.




**Example Migrate SAN domain: JSON request**


.. code::

    POST /v1.0/110011/admin/provider/akamai/service HTTP1.1
    Host: global.cdn.api.rackspacecloud.com
    X-Auth-Token: 0f6e9f63600142f0a970911583522217
    Accept: application/json
    Content-type: application/json
    


Response
""""""""""""""""










**Example Migrate SAN domain: JSON response**


.. code::

    HTP/1.1 202 (Accepted)
    Location: https://global.cdn.api.rackspacecloud.com/v1.0/admin/provider/akamai/service

