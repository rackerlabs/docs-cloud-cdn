
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

=============================================================================
Retrieve Health Details -  Rackspace CDN Developer Guide for Service Management
=============================================================================

Retrieve Health Details
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <get-retrieve-health-details-health-subsystem.html#request>`__
`Response <get-retrieve-health-details-health-subsystem.html#response>`__

.. code::

    GET //health/{subsystem}

Retrieves the health details for a subsystem.

This operation shows whether a subsystem is online or offline. 



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
^^^^^^^^^^^^^^^^^

This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{subsystem}               |xsd:string               |The unique identifier    |
|                          |                         |for the user.            |
+--------------------------+-------------------------+-------------------------+








**Example Retrieve Health Details: JSON request**


.. code::

    GET /v1.0/110011/health/{subsystem} HTTP1.1
    Host: global.cdn.api.rackspacecloud.com
    X-Auth-Token: 0f6e9f63600142f0a970911583522217
    Accept: application/json
    Content-type: application/json
    


Response
^^^^^^^^^^^^^^^^^^





**Example Retrieve Health Details: JSON response**


.. code::

    HTTP/1.1 200 OK
    Content-Type: application/json

