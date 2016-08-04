.. _cdn-get-flavor-details:

Retrieve flavor details
~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /v1.0/{project_id}/flavors/{flavor_id}

This operation retrieves details for the flavor specified by flavor_id.

The following table shows the possible response codes for this operation.

+--------------------------+-------------------------+------------------------+
|Response Code             |Name                     |Description             |
+==========================+=========================+========================+
|200                       |OK                       |Success.                |
+--------------------------+-------------------------+------------------------+

Request
-------

The following table shows the URI parameters for the request.

+-------------+-------------+--------------------------------------------------------------+
|Name         |Type         |Description                                                   |
+=============+=============+==============================================================+
|{project_id} |String       |The project ID for the user. If you do not set the ``X-       |
|             |             |Project-Id header`` in the request, use ``project_id`` in the |
|             |             |URI. For example: ``GET                                       |
|             |             |https://global.cdn.api.rackspacecloud.com/v1.0/{project_id}`` |
+-------------+-------------+--------------------------------------------------------------+
|{flavor_id}  |String       |Specifies the flavor ID. For example: cdn                     |
|             |             |                                                              |
+-------------+-------------+--------------------------------------------------------------+

This operation does not accept a request body.

**Example: Retrieve flavor details HTTP request**

.. code::

   GET /v1.0/110011/flavors/cdn HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json

Response
--------

The following table shows the body parameters for the response.

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|\ **id**                  |String                   |Specifies the name of    |
|                          |                         |the flavor. The name     |
|                          |                         |must not exceed 64 bytes |
|                          |                         |in length and is limited |
|                          |                         |to Unicode, digits,      |
|                          |                         |underscores, and hyphens.|
+--------------------------+-------------------------+-------------------------+
|\ **providers**           |String                   |Specifies the list of    |
|                          |                         |providers mapped to this |
|                          |                         |flavor class.            |
+--------------------------+-------------------------+-------------------------+
|\ providers.\             |String                   |Specifies the name of    |
|**provider**              |                         |the provider. The name   |
|                          |                         |must not exceed 64 bytes |
|                          |                         |in length and is limited |
|                          |                         |to Unicode, digits,      |
|                          |                         |underscores, and hyphens.|
+--------------------------+-------------------------+-------------------------+
|providers.\ **links**     |String                   |Specifies a list with a  |
|                          |                         |``href`` where ``rel``   |
|                          |                         |is ``provider_url``.     |
+--------------------------+-------------------------+-------------------------+
|\ **links**               |String                   |Specifies the self-      |
|                          |                         |navigating JSON document |
|                          |                         |paths.                   |
+--------------------------+-------------------------+-------------------------+
|links.\ **href**          |String                   |Specifies the location   |
|                          |                         |to access this resource. |
+--------------------------+-------------------------+-------------------------+
|links.\ **rel**           |String                   |Specifies how the href   |
|                          |                         |link provided is related |
|                          |                         |to this resource_url.    |
+--------------------------+-------------------------+-------------------------+

**Example: Retrieve flavor details HTTP and JSON response**

.. code::

   HTTP/1.1 200 OK
   Content-Type: application/json

.. code::

   {
       "id": "cdn",
       "providers": [
           {
               "provider": "akamai",
               "links": [
                   {
                       "href": "http://www.akamai.com",
                       "rel": "provider_url"
                   }
               ]
           }
       ],
       "links": [
           {
               "href": "https://global.cdn.api.rackspacecloud.com/v1.0/110011/flavors/cdn",
               "rel": "self"
           }
       ]
   }
