.. _common-headers:

==============
Common headers
==============

The following table describes the common headers used by the API.

**Table: Common headers**

+-----------------------+------------------------------------------------------------+
| Header                | Description                                                |
+=======================+============================================================+
| X-Auth-Token          | Authentication token. Required.                            |
+-----------------------+------------------------------------------------------------+
| X-Project-Id          | A unique ID for the user to which the value of             |
|                       | ``X-Auth-Token`` grants access. The unique ID is           |
|                       | your account ID.                                           |
+-----------------------+------------------------------------------------------------+
| Accept                | Media type. Initially, only ``application/json`` is        |
|                       | supported.                                                 |
+-----------------------+------------------------------------------------------------+
| Accept-Encoding       | Specifies that the agent accepts gzip-encoded              |
|                       | response bodies.                                           |
+-----------------------+------------------------------------------------------------+
| Client-ID             | A unique ID for each client instance. The ``Client-ID``    |
|                       | is used to avoid echoing a sender's messages back to       |
|                       | the same instance, and it can be logged by the             |
|                       | server for future use. The client generates the            |
|                       | ``Client-ID`` once, and it persists between restarts of    |
|                       | the client. The client should reuse the same               |
|                       | ``Client-ID``. Note: All message-related operations        |
|                       | require that ``Client-ID`` is included in the headers to   |
|                       | ensure that messages are not echoed back to the            |
|                       | client that posted them, unless the client                 |
|                       | explicitly requests this.                                  |
+-----------------------+------------------------------------------------------------+
| Content-Length        | For POST or PUT requests, the length in bytes of           |
|                       | the message document being submitted.                      |
+-----------------------+------------------------------------------------------------+
| Content-Type          | ``application/json``                                       |
+-----------------------+------------------------------------------------------------+
| Date                  | Current date and time                                      |
+-----------------------+------------------------------------------------------------+
| Host                  | Host name of the API                                       |
+-----------------------+------------------------------------------------------------+

