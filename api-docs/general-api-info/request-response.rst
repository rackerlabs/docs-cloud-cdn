.. _req-resp-types:

==========================
Request and response types
==========================

The |apiservice| supports the JSON data serialization format.

The request format is specified by using the ``Content-Type`` header and is
required for operations that have a request body.

You can specify the response format in requests by using the ``Accept``
header or by adding a ``.json`` extension to the request URI. If no
response format is specified, JSON is the default.

The response format can be specified in requests either by using the ``Accept``
header or adding a ``.json`` extension to the request URI.
If no response format is specified, JSON is the default.

.. list-table:: **Response formats**
   :widths: 10 20 10 10
   :header-rows: 1

   * - Format
     - Accept header
     - Query extension
     - Default
   * - JSON
     - application/json
     - .json
     - Yes
