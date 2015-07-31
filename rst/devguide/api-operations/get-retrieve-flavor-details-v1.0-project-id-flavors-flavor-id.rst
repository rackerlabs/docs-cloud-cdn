
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Retrieve Flavor Details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v1.0/{project_id}/flavors/{flavor_id}

Retrieves details for the flavor specified by flavor_id.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""

This table shows the URI parameters for the request:

+-------------+-------------+--------------------------------------------------------------+
|Name         |Type         |Description                                                   |
+=============+=============+==============================================================+
|{project_id} |xsd:string   |The project ID for the user. If you do not set the ``X-       |
|             |             |Project-Id header`` in the request, use ``project_id`` in the |
|             |             |URI. For example: ``GET                                       |
|             |             |https://global.cdn.api.rackspacecloud.com/v1.0/{project_id}`` |
+-------------+-------------+--------------------------------------------------------------+
|{flavor_id}  |xsd:string   |Specifies the flavor ID. For example: cdn                     |
|             |*(Required)* |                                                              |
+-------------+-------------+--------------------------------------------------------------+





This operation does not accept a request body.




**Example Retrieve Flavor Details: JSON request**


.. code::

    GET /v1.0/110011/flavors/cdn HTTP/1.1
    Host: global.cdn.api.rackspacecloud.com
    X-Auth-Token: 0f6e9f63600142f0a970911583522217
    Accept: application/json
    Content-type: application/json
    
    


Response
""""""""""""""""


This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|id                        |                         |Specifies the name of    |
|                          |                         |the flavor. The name     |
|                          |                         |must not exceed 64 bytes |
|                          |                         |in length and is limited |
|                          |                         |to Unicode, digits,      |
|                          |                         |underscores, and hyphens.|
+--------------------------+-------------------------+-------------------------+
|providers                 |                         |Specifies the list of    |
|                          |                         |providers mapped to this |
|                          |                         |flavor class.            |
+--------------------------+-------------------------+-------------------------+
|provider                  |                         |Specifies the name of    |
|                          |                         |the provider. The name   |
|                          |                         |must not exceed 64 bytes |
|                          |                         |in length and is limited |
|                          |                         |to Unicode, digits,      |
|                          |                         |underscores, and hyphens.|
+--------------------------+-------------------------+-------------------------+
|links                     |                         |Specifies a list with a  |
|                          |                         |``href`` where ``rel``   |
|                          |                         |is ``provider_url``.     |
+--------------------------+-------------------------+-------------------------+
|links                     |                         |Specifies the self-      |
|                          |                         |navigating JSON document |
|                          |                         |paths.                   |
+--------------------------+-------------------------+-------------------------+
|href                      |                         |Specifies the location   |
|                          |                         |to access this resource. |
+--------------------------+-------------------------+-------------------------+
|rel                       |                         |Specifies how the href   |
|                          |                         |link provided is related |
|                          |                         |to this resource_url.    |
+--------------------------+-------------------------+-------------------------+





**Example Retrieve Flavor Details: JSON response**


.. code::

    HTTP/1.1 200 OK
    Content-Type: application/json

