
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Retrieve health check
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

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
|                          |                         |scheduled platform       |
|                          |                         |maintenance). Try again  |
|                          |                         |later.                   |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""






This operation does not accept a request body.




**Example Retrieve health check: JSON request**


.. code::

    GET /v1.0/110011/health HTTP/1.1
    Host: global.cdn.api.rackspacecloud.com
    X-Auth-Token: 0f6e9f63600142f0a970911583522217
    Accept:application/json
    Content-type: application/json
    


Response
""""""""""""""""





**Example Retrieve health check: JSON response**


.. code::

    HTTP/1.1 200 OK
    Content-Type: application/json


