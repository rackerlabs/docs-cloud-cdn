.. _cdn-get-the-home-document:

Retrieve the home document
~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /v1.0/{project_id}/

This operation retrieves the home document.

The entire API is discoverable from a single 	starting point, the home document.
To explore the 	entire API, you need to know only this one URI.

The home document schema is currently not ratified in OpenStack and might change.
For more information about home documents, see `Home Documents for HTTP APIs <http://tools.ietf.org/html/draft-nottingham-json-home-03>`__
on the IEFT website.

The following table shows the possible response codes for this operation.

+--------------------------+-------------------------+------------------------+
|Response Code             |Name                     |Description             |
+==========================+=========================+========================+
|200                       |OK                       |Success.                |
+--------------------------+-------------------------+------------------------+

Request
-------

The following table shows the URI parameters for the request.

+-------------+-------+--------------------------------------------------------------+
|Name         |Type   |Description                                                   |
+=============+=======+==============================================================+
|{project_id} |String |The project ID for the user. If you do not set the ``X-       |
|             |       |Project-Id header`` in the request, use ``project_id`` in the |
|             |       |URI. For example: ``GET                                       |
|             |       |https://global.cdn.api.rackspacecloud.com/v1.0/{project_id}`` |
+-------------+-------+--------------------------------------------------------------+

This operation does not accept a request body.

**Example: Retrieve the home document HTTP request**

.. code::

   GET /v1.0/110011/ HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json

Response
--------

**Example: Retrieve the home document HTTP and JSON response**

.. code::

   HTTP/1.1 200 OK
   Content-Type: application/json

.. code::

   {
     "resources": {
       "rel/health": {
         "href-template": "/health",
         "href-vars": {
           "subsystem": "param/subsystem"
         },
         "hints": {
           "allow": [
             "GET"
           ],
           "formats": {
             "application/json": {}
           }
         }
       },
       "rel/flavors": {
         "href-template": "/flavors/{flavor_id}",
         "href-vars": {
           "marker": "param/flavor_id"
         },
         "hints": {
           "allow": [
             "GET",
             "POST",
             "DELETE"
           ],
           "formats": {
             "application/json": {}
           }
         }
       },
       "rel/ping": {
         "href-template": "/ping",
         "hints": {
           "allow": [
             "GET"
           ],
           "formats": {
             "application/json": {}
           }
         }
       },
       "rel/services": {
         "href-template": "/services{?marker,limit}",
         "href-vars": {
           "marker": "param/marker",
           "limit": "param/limit"
         },
         "hints": {
           "allow": [
             "GET",
             "POST"
           ],
           "formats": {
             "application/json": {}
           }
         }
       }
     }
   }
