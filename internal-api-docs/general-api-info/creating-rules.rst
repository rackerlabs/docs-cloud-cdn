.. _creating-rules:

Creating rules
~~~~~~~~~~~~~~

When you create a service POST call to /v1.0/{project_id}/services you can define rules for the service for the following parameters within the request:

-  ``origins``: Specifies a collection of rules that define the
   conditions when the origin should be accessed. If there is more than
   one origin,the rules parameter is required.

   The ``origin.rules`` parameter supports the ``name`` and
   ``request_url`` parameters.

-  ``caching``: Specifies a collection of rules that determine if the
   TTL should be applied to an asset.

   The ``caching.rules`` parameter supports the ``name`` and
   ``request_url`` parameters.

-  ``restrictions``: Specifies a collection of rules that define the
   restrictions to impose on the service. Rules can be combined
   together.

   The ``restrictions.rules`` parameter supports ``name``,
   ``referrer``, ``request_url``, ``geography``, and ``client_ip`` parameters.

.. note:: 

   Each of the parameters above are described in the `Create a service`_ method description.

These rules are stored in a policy file at every edge server and are
applied to your traffic when a request is issued that matches the path
of your rule. For that reason, creating rules for your content always
begins by setting a path for which the rule should be applied. Because
Rackspace CDN applies rules using a path, you can specify rules as
granular as the file level. 

Within the Rackspace CDN API, paths are defined using the ``domain`` and
``origin`` parameters in the request to create a service. Then, for
example, with the ``caching.rules``, you might set ``ttl`` equal to 3600
seconds (1 hour) for a specific file by making the rule path
``/videos/marketingspot/abccompany/welcomevideo.mp4``.

For more information about rules, see :how-to:`Rackspace CDN edge
rules<rackspace-cdn-edge-rules>`.

.. _Create a service: https://developer.rackspace.com/docs/cdn/v1/developer-guide/#create-a-service