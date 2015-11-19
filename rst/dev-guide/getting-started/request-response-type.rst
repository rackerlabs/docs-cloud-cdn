.. _gsg-request-and-response-types:

Request and response types
~~~~~~~~~~~~~~~~~~~~~~~~~~

The Rackspace CDN API supports JSON data serialization formats.

Specify the request format by using the ``Content-Type`` header, which
is required for operations that have a request body.

You can specify the response format in requests by using the ``Accept``
header or by adding a ``.json`` extension to the request URI. If no
response format is specified, JSON is the default.

**Response formats**

+--------+------------------+-----------------+---------+
| Format |  Accept header   | Query extension | Default |
+========+==================+=================+=========+
| JSON   | application/json | .json           | Yes     |
+--------+------------------+-----------------+---------+
