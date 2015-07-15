=============================================================================
Retrieve Flavors -  Rackspace CDN Developer Guide
=============================================================================

Retrieve Flavors
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <GET_retrieve_flavors_v1.0_project_id_flavors.rst#request>`__
`Response <GET_retrieve_flavors_v1.0_project_id_flavors.rst#response>`__

.. code-block:: javascript

    GET /v1.0/{project_id}/flavors

Retrieves a list of all available flavors.

This operation retrieves a list of all available flavors.



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








**Example Retrieve Flavors: JSON request**


.. code::

    GET /v1.0/110011/flavors HTTP/1.1
    Host: global.cdn.api.rackspacecloud.com
    X-Auth-Token: 0f6e9f63600142f0a970911583522217
    Accept: application/json
    Content-type: application/json
    


Response
^^^^^^^^^^^^^^^^^^


This table shows the body parameters for the response:

+-----------------+-----------------+------------------------------------------+
|Name             |Type             |Description                               |
+=================+=================+==========================================+
|id               |                 |Specifies the name of the flavor. The     |
|                 |                 |name must not exceed 64 bytes in length   |
|                 |                 |and is limited to Unicode, digits,        |
|                 |                 |underscores, and hyphens.                 |
+-----------------+-----------------+------------------------------------------+
|providers        |                 |Specifies the list of providers mapped to |
|                 |                 |this flavor.                              |
+-----------------+-----------------+------------------------------------------+
|provider         |                 |Specifies the name of the provider. The   |
|                 |                 |name must not exceed 64 bytes in length   |
|                 |                 |and is limited to Unicode, digits,        |
|                 |                 |underscores, and hyphens.                 |
+-----------------+-----------------+------------------------------------------+
|links            |                 |Specifies a list with                     |
|                 |                 |an``href``where``rel``is``provider_url``. |
+-----------------+-----------------+------------------------------------------+
|links            |                 |Specifies the self-navigating JSON        |
|                 |                 |document paths.                           |
+-----------------+-----------------+------------------------------------------+
|href             |                 |Specifies the location to use to access   |
|                 |                 |the resource.                             |
+-----------------+-----------------+------------------------------------------+
|rel              |                 |Specifies how the``href``link provided is |
|                 |                 |related to the resource_url.              |
+-----------------+-----------------+------------------------------------------+





**Example Retrieve Flavors: JSON request**


.. code::

    HTTP/1.1 200 OK
    Content-Type: application/json

