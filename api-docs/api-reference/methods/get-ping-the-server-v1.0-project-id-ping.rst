.. _cdn-ping-the-server:

Ping the server
~~~~~~~~~~~~~~~

.. code::

    GET /v1.0/{project_id}/ping

This operation pings the server.


The following table shows the possible response codes for this operation.

+--------------------------+-------------------------+------------------------+
|Response Code             |Name                     |Description             |
+==========================+=========================+========================+
|204                       |No Content               |The server successfully |
|                          |                         |processed the request,  |
|                          |                         |but is not returning any|
|                          |                         |content.                |
+--------------------------+-------------------------+------------------------+
|500                       |Internal Server Error    |The implementation of   |
|                          |                         |ping may return a 500   |
|                          |                         |response in cases where |
|                          |                         |the API service is      |
|                          |                         |unable to communicate   |
|                          |                         |with one or more        |
|                          |                         |implementation nodes for|
|                          |                         |the service. Errors in  |
|                          |                         |the transport layer     |
|                          |                         |between the client and  |
|                          |                         |the API node may produce|
|                          |                         |other errors.           |
+--------------------------+-------------------------+------------------------+
|503                       |Service Unavailable      |The implementation of   |
|                          |                         |ping may return a 503   |
|                          |                         |response in cases where |
|                          |                         |the API service is      |
|                          |                         |unable to communicate   |
|                          |                         |with one or more        |
|                          |                         |implementation nodes for|
|                          |                         |the service. Errors in  |
|                          |                         |the transport layer     |
|                          |                         |between the client and  |
|                          |                         |the API node may produce|
|                          |                         |other errors.           |
+--------------------------+-------------------------+------------------------+

Request
-------

The following table shows the URI parameters for the request.

+-------------+-------+-------------------------------------------------------+
|Name         |Type   |Description                                            |
+=============+=======+=======================================================+
|{project_id} |String |The project ID for the user. If you do not set the     |
|             |       |``X-Project-Id header`` in the request, use            |
|             |       |``project_id`` in the URI. For example: ``GET          |
|             |       |https://global.cdn.api.rackspacecloud.com/v1.0/        |
|             |       |{project_id}``                                         |
+-------------+-------+-------------------------------------------------------+

This operation does not accept a request body.

**Example: Ping the server HTTP request**

.. code::

   GET /v1.0/110011/ping HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217

Response
--------

This operation does not return a response body.

**Example: Ping the server HTTP response**

.. code::

   HTTP/1.1 204 No Content
