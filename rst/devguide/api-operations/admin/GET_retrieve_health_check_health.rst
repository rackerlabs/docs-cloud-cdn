=============================================================================
Retrieve Health Check -  Rackspace CDN Developer Guide for Service Management
=============================================================================

Retrieve Health Check
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <GET_retrieve_health_check_health.rst#request>`__
`Response <GET_retrieve_health_check_health.rst#response>`__

.. code-block:: javascript

    GET //health

Retrieves a health check.

This operation retrieves a health check.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+
|503                       |Service Unavailable      |The service is           |
|                          |                         |temporarily unavailable  |
|                          |                         |(for example, for        |
|                          |                         |scheduledplatform        |
|                          |                         |maintenance). Try again  |
|                          |                         |later.                   |
+--------------------------+-------------------------+-------------------------+


Request
^^^^^^^^^^^^^^^^^









**Example Retrieve Health Check: JSON request**


.. code::

    GET /v1.0/110011/health HTTP/1.1
    Host: global.cdn.api.rackspacecloud.com
    X-Auth-Token: 0f6e9f63600142f0a970911583522217
    Accept:application/json
    Content-type: application/json
    


Response
^^^^^^^^^^^^^^^^^^





**Example Retrieve Health Check: JSON request**


.. code::

    HTTP/1.1 200 OK
    Content-Type: application/json

