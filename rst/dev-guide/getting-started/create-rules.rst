.. _gsg-create-rules:

Creating rules
~~~~~~~~~~~~~~

When you create a service with the operation described at :ref:`Create a service <gsg-create-service>``, within the request,
you can define rules for the service for the following parameters:

-  ``origins``: Specifies a collection of rules that define the
   conditions when the origin should be accessed. If there is more than
   one origin, the rules parameter is required.

   The ``origin.rules`` parameter supports the ``name`` and
   ``request_url`` parameters.

-  ``caching``: Specifies a collection of rules that determine if the
   TTL should be applied to an asset.

   The ``caching.rules`` parameter supports the ``name`` and
   ``request_url`` parameters.

-  ``restrictions``: Specifies a collection of rules that define the
   restrictions to impose on the service. Rules can be combined
   together.

   The ``retrictions.rules`` parameter supports ``name`` and
   ``referrer`` parameters.

..  note:: 
    Each of the parameters above is described in the API reference in 
   :ref:`Create a service <cdn-create-a-service>`.

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

For more information about rules, see `Rackspace CDN edge
rules <https://www.rackspace.com/knowledge_center/article/rackspace-cdn-edge-rules>`__.
