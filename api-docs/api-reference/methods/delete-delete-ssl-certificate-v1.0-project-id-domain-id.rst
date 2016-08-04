.. _cdn-delete-ssl-certificate:

Delete an SSL certificate
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    DELETE /v1.0/{project_id}/ssl_certificate/{domain_name}

This operation deletes an SSL certificate.

**WARNING**: If you delete a working SSL certificate, you will break your CDN service.

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

+-------------+-------------+-------------------------------------------------+
|Name         |Type         |Description                                      |
+=============+=============+=================================================+
|{project_id} |String       |The project ID for the user. If you do not set   |
|             |             |the ``X-Project-Id header`` in the request, use  |
|             |             |``project_id`` in the URI. For example: ``GET    |
|             |             |https://global.cdn.api.rackspacecloud.com/v1.0/  |
|             |             |{project_id}``                                   |
+-------------+-------------+-------------------------------------------------+
|{domain_name}|String       |Specifies a string representing the type of the  |
|             |             |SSL certificate, such as ``www.example.com.``    |
+-------------+-------------+-------------------------------------------------+

This operation does not accept a request body.

**Example: Delete an SSL certificate HTTP request**

.. code::

   DELETE /v1.0/110011/ssl_certificate/{domain_name} HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json

Response
--------

This operation does not return a response body.

**Example: Delete an SSL certificate HTTP response**

.. code::

   HTTP/1.1 202 Accepted
