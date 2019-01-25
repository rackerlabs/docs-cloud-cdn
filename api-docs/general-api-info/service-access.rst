.. _service-access:

========================
Service access endpoints
========================

Rackspace CDN has a global endpoint. Data is replicated to all data
centers. The global endpoint is as follows:

.. code::

    https://global.cdn.api.rackspacecloud.com/v1.0/123456

Replace the example account ID number, ``123456``, with your actual
account ID returned as part of the
:ref:`authentication service response<review-auth-resp>`.
Your account ID is located after the final slash (/) in the
``publicURL`` field returned by the authentication response.

.. note:: The account ID from the Identity service is the same as the project
   ID given in the ``X-Project-Id`` header in Rackspace CDN. (You might also
   see the account ID or project ID referred to as the tenant ID.)
