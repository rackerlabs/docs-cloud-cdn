.. _response-codes:

==============
Response codes
==============

Rackspace CDN returns an HTTP code that denotes the type of response.

-  Successful response codes are returned only if all configured
   providers were successful in processing the request.

-  Error response codes are accompanied by an ``application/json``
   response body that contains the error messages.

This API uses `standard HTTP 1.1 response codes`_.

The following table lists possible responses with their associated codes
and descriptions.

+--------------------------+--------------------------+-----------------------+
| Response                 | Associated               | Description           |
|                          | response code            |                       |
+--------------------------+--------------------------+-----------------------+
| OK                       | 200                      | The request has       |
|                          |                          | succeeded.            |
|                          |                          | (Some API calls       |
|                          |                          | return 201 instead.   |
+--------------------------+--------------------------+-----------------------+
| Created                  | 201                      | The request has been  |
|                          |                          | fulfilled and a       |
|                          |                          | resource was created. |
+--------------------------+--------------------------+-----------------------+
| Accepted                 | 202                      | The request has been  |
|                          |                          | accepted for          |
|                          |                          | processing.           |
+--------------------------+--------------------------+-----------------------+
| No Content               | 204                      | The request has been  |
|                          |                          | fulfilled but does not|
|                          |                          | return a              |
|                          |                          | representation (that  |
|                          |                          | is, the response is   |
|                          |                          | empty).               |
+--------------------------+--------------------------+-----------------------+
| Bad Request              | 400                      | The request was not   |
|                          |                          | understood or was     |
|                          |                          | missing required      |
|                          |                          | parameters.           |
+--------------------------+--------------------------+-----------------------+
| Unauthorized             | 401                      | Authentication failed,|
|                          |                          | or the user does not  |
|                          |                          | have permissions for a|
|                          |                          | requested operation.  |
+--------------------------+--------------------------+-----------------------+
| Forbidden                | 403                      | The server understood |
|                          |                          | the request but       |
|                          |                          | refused to fulfill it.|
+--------------------------+--------------------------+-----------------------+
| Not Found                | 404                      | A requested resource  |
|                          |                          | was not found.        |
+--------------------------+--------------------------+-----------------------+
| Method Not Allowed       | 405                      | The request method is |
|                          |                          | not supported for this|
|                          |                          | resource.             |
+--------------------------+--------------------------+-----------------------+
| Request Entity Too Large | 413                      | The server is refusing|
|                          |                          | to process a request  |
|                          |                          | because the request   |
|                          |                          | entity is larger than |
|                          |                          | the server is willing |
|                          |                          | or able to process.   |
+--------------------------+--------------------------+-----------------------+
| URI Too Long             | 414                      | The request URI       |
|                          |                          | provides is too long  |
|                          |                          | for the server to     |
|                          |                          | process.              |
+--------------------------+--------------------------+-----------------------+
| Too Many Requests        | 429                      | Too many requests have|
|                          |                          | been sent in a given  |
|                          |                          | amount of time. Pause |
|                          |                          | requests, wait up to  |
|                          |                          | one minute, and try   |
|                          |                          | again. (Intended for  |
|                          |                          | use with rate         |
|                          |                          | limiting.)            |
+--------------------------+--------------------------+-----------------------+
| Internal Server Error    | 500                      | The service           |
|                          |                          | encountered an        |
|                          |                          | unexpected condition  |
|                          |                          | that prevented it     |
|                          |                          | from fulfilling the   |
|                          |                          | request.              |
+--------------------------+--------------------------+-----------------------+
| Service Unavailable      | 503                      | The service is        |
|                          |                          | temporarily           |
|                          |                          | unavailable, for      |
|                          |                          | example, for scheduled|
|                          |                          | platform maintenance. |
|                          |                          | Try again later.      |
+--------------------------+--------------------------+-----------------------+

An example of an error message follows.

**Example: Error message example**

.. code::

    HTTP/1.1 400 Bad Request
    Content-Type: application/json

    {
        "message": {
            "errors": [
                {
                    "message": "['domains']-[] is too short"
                }
            ]
        }
    }

.. _standard HTTP 1.1 response codes: http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html