=============================================================================
Retrieve The Home Document -  Rackspace CDN Developer Guide
=============================================================================

Retrieve The Home Document
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <GET_retrieve_the_home_document_v1.0_project_id_.rst#request>`__
`Response <GET_retrieve_the_home_document_v1.0_project_id_.rst#response>`__

.. code-block:: javascript

    GET /v1.0/{project_id}/

Retrieves the home document.

The entire API is discoverable from a single starting point, the home document. To explore the entire API, you need to know only this one URI.

The home document schema is currently not ratified in OpenStack and might change. For more information about home documents, see `Home Documents for HTTP APIs <http://tools.ietf.org/html/draft-nottingham-json-home-03>`__ on the IEFT website.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+


Request
^^^^^^^^^^^^^^^^^

This table shows the URI parameters for the request:

+-------------+-----------+--------------------------------------------------------------+
|Name         |Type       |Description                                                   |
+=============+===========+==============================================================+
|{project_id} |xsd:string |The project ID for the user. If you do not set the ``X-       |
|             |           |Project-Id header`` in the request, use ``project_id`` in the |
|             |           |URI. For example: ``GET                                       |
|             |           |https://global.cdn.api.rackspacecloud.com/v1.0/{project_id}`` |
+-------------+-----------+--------------------------------------------------------------+








**Example Retrieve The Home Document: JSON request**


.. code::

    GET /v1.0/110011/ HTTP/1.1
    Host: global.cdn.api.rackspacecloud.com
    X-Auth-Token: 0f6e9f63600142f0a970911583522217
    Accept: application/json
    Content-type: application/json
    


Response
^^^^^^^^^^^^^^^^^^





**Example Retrieve The Home Document: JSON request**


.. code::

    HTTP/1.1 200 OK
    Content-Type: application/json

