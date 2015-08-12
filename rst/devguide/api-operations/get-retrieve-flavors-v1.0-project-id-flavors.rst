
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Retrieve flavors
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v1.0/{project_id}/flavors

Retrieves a list of all available flavors.



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
|{project_id} |String       |The project ID for the user. If you do not set the ``X-       |
|             |*(Required)* |Project-Id header`` in the request, use ``project_id`` in the |
|             |             |URI. For example: ``GET                                       |
|             |             |https://global.cdn.api.rackspacecloud.com/v1.0/{project_id}`` |
+-------------+-------------+--------------------------------------------------------------+





This operation does not accept a request body.




**Example Retrieve flavors: JSON request**


.. code::

    GET /v1.0/110011/flavors HTTP/1.1
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
|                          |                         |flavor.                  |
+--------------------------+-------------------------+-------------------------+
|provider                  |                         |Specifies the name of    |
|                          |                         |the provider. The name   |
|                          |                         |must not exceed 64 bytes |
|                          |                         |in length and is limited |
|                          |                         |to Unicode, digits,      |
|                          |                         |underscores, and hyphens.|
+--------------------------+-------------------------+-------------------------+
|links                     |                         |Specifies a list with an |
|                          |                         |``href`` where ``rel``   |
|                          |                         |is ``provider_url``.     |
+--------------------------+-------------------------+-------------------------+
|links                     |                         |Specifies the self-      |
|                          |                         |navigating JSON document |
|                          |                         |paths.                   |
+--------------------------+-------------------------+-------------------------+
|href                      |                         |Specifies the location   |
|                          |                         |to use to access the     |
|                          |                         |resource.                |
+--------------------------+-------------------------+-------------------------+
|rel                       |                         |Specifies how the        |
|                          |                         |``href`` link provided   |
|                          |                         |is related to the        |
|                          |                         |resource_url.            |
+--------------------------+-------------------------+-------------------------+





**Example Retrieve flavors: JSON response**


.. code::

    HTTP/1.1 200 OK
    Content-Type: application/json


**Example Retrieve flavors: JSON response**


.. code::

    {
        "flavors": [
            {
                "id": "cdn",
                "providers": [
                    {
                        "provider": "akamai",
                        "links": [
                            {
                                "href": "http: //www.akamai.com",
                                "rel": "provider_url"
                            }
                        ]
                    }
                ],
                "links": [
                    {
                        "href": "https: //global.cdn.api.rackspacecloud.com/v1.0/110011/flavors/cdn",
                        "rel": "self"
                    }
                ]
            }
        ]
    }
    


