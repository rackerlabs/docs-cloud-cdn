=============================================================================
Retrieve A Service By Domain Name -  Rackspace CDN Developer Guide for Service Management
=============================================================================

Retrieve A Service By Domain Name
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <GET_retrieve_a_service_by_domain_name_admin_domains_domain_name_.rst#request>`__
`Response <GET_retrieve_a_service_by_domain_name_admin_domains_domain_name_.rst#response>`__

.. code-block:: javascript

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
^^^^^^^^^^^^^^^^^

This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{domain_name}             |xsd:string               |The name of the domain.  |
|                          |                         |For example,             |
|                          |                         |blog.mywebsite.com.      |
+--------------------------+-------------------------+-------------------------+








**Example Retrieve A Service By Domain Name: JSON request**


.. code::

    GET /v1.0/110011/admin/domains/blog.mywebsite.com HTTP1.1
    Host: global.cdn.api.rackspacecloud.com
    X-Auth-Token: 0f6e9f63600142f0a970911583522217
    Accept: application/json
    Content-type: application/json
    


Response
^^^^^^^^^^^^^^^^^^





**Example Retrieve A Service By Domain Name: JSON request**


.. code::

    HTTP/1.1 200 OK
    Content-Type: application/json

