
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Retrieve a service by domain name
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET //admin/domains/{domain_name}

Retrieves a service by domain name.

This operation retrieves a service by domain name. 



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{domain_name}             |String                   |The name of the domain.  |
|                          |                         |For example,             |
|                          |                         |blog.mywebsite.com.      |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example Retrieve a service by domain name: JSON request**


.. code::

    GET /v1.0/110011/admin/domains/blog.mywebsite.com HTTP1.1
    Host: global.cdn.api.rackspacecloud.com
    X-Auth-Token: 0f6e9f63600142f0a970911583522217
    Accept: application/json
    Content-type: application/json
    


Response
""""""""""""""""







**Example Retrieve a service by domain name: JSON response**


.. code::

    HTTP/1.1 200 OK
    Content-Type: application/json


