.. _cdn-create-ssl-certificate:

Create an SSL certificate
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    POST /v1.0/{project_id}/ssl_certificate

This operation creates an SSL certificate.

The following table shows the possible response codes for this operation.

+--------------------------+-------------------------+------------------------+
|Response Code             |Name                     |Description             |
+==========================+=========================+========================+
|202                       |Accepted                 |The request has been    |
|                          |                         |fulfilled, but does not |
|                          |                         |return a representation |
|                          |                         |(that is, the response  |
|                          |                         |is empty).              |
+--------------------------+-------------------------+------------------------+

Request
-------

The following table shows the URI parameters for the request.

+-------------+-------------+--------------------------------------------------------------+
|Name         |Type         |Description                                                   |
+=============+=============+==============================================================+
|{project_id} |String       |The project ID for the user. If you do not set the ``X-       |
|             |             |Project-Id header`` in the request, use ``project_id`` in the |
|             |             |URI. For example: ``GET                                       |
|             |             |https://global.cdn.api.rackspacecloud.com/v1.0/{project_id}`` |
+-------------+-------------+--------------------------------------------------------------+

The following table shows the body parameters for the request.

+-----------------------+-------------+------------------------------------------------------------------------------+
|Name                   |Type         |Description                                                                   |
+=======================+=============+==============================================================================+
|\ **cert_type**        |String       |Specifies the type of SSL certificate. Valid values are ``san`` and           |
|                       |*(Required)* |``custom``. However, ``custom`` is not yet implemented.                       |
+-----------------------+-------------+------------------------------------------------------------------------------+
|\ **domain_name**      |String       |Specifies a string representing the type of the SSL                           |
|                       |*(Required)* |certificate, such as ``www.example.com``.                                     |
+-----------------------+-------------+------------------------------------------------------------------------------+
|\ **flavor_id**        |String       |Specifies the CDN provider flavor ID to use. For a list of flavors, see the   |
|                       |*(Required)* |operation to list the available flavors. The minimum length for ``flavor_id`` |
|                       |             |is 3. The maximum length is 256.                                              |
+-----------------------+-------------+------------------------------------------------------------------------------+
|\ **project_id**       |String       |The project ID for the user.                                                  |
|                       |*(Required)* |                                                                              |
+-----------------------+-------------+------------------------------------------------------------------------------+

**Example: Create an SSL certificate HTTP and JSON request**

.. code::

   POST /v1.0/110011/ssl_certificate HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json

.. code::

   {
       "cert_type": "san",
       "domain_name": "www.example.com",
       "flavor_id": "cdn",
       "project_id": "12345"
   }

Response
--------

This operation does not return a response body.

**Example: Create an SSL certificate HTTP response**


.. code::

   HTTP/1.1 202 Accepted
   Content-Type: application/json
