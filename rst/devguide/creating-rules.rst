==============
Creating rules
==============

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

   The ``retrictions.rules`` parameter supports ``name`` and
   ``referrer`` parameters.

.. note:: Each of the parameters above are described in the API reference.

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

For more information, see `Rackspace CDN edge
rules <https://www.rackspace.com/knowledge_center/article/rackspace-cdn-edge-rules>`__.

Rule ordering
~~~~~~~~~~~~~

When you specify multiple rules within one rule type, such as
``origins``, ``caching``, or ``restrictions``, the order of these rules
is very important. 

When content comes into the CDN network for a Rackspace CDN domain,
rules in the policy file are evaluated from top to bottom. The last rule
matching the requesting URL is applied.   

If any parameter definitions are specified more than once in a set of
rules, the last definition overrides those definitions that precede it.
In some cases, the ordering of different parameter definitions that
perform similar functions for the service might also matter. In other
cases, you can reuse the same parameter definitions to do different
things that do not conflict with each other.

For example, a URL
of \ ``www.mywebsite.com/videos/marketingspot/abccompany/welcomevideo.mp4``
matches all of the following rule paths:

-  ``www.mywebsite.com``

-  ``www.mywebsite.com/videos``

-  ``www.mywebsite.com/videos/marketingspot``

-  ``www.mywebsite.com/videos/marketingspot/abccompany``

-  ``www.mywebsite.com/videos/marketingspot/abccompany/welcomevideo.mp4``


.. note: Because all of the paths match the rule, you must order rules from
   least specific to most specific, as shown above. 

When defining the path, you can use wildcards. For example, use ``/*``
to include all content, or include ``*.mp4`` to select all files with
the ``.mp4`` extension.

In your request, if you define a set of caching rules with the paths in
the following order, the last rule matches and assigns the TTL to 3600
seconds (or 1 hour) rather than 259200 seconds (or 3 days):

``www.mywebsite.com/videos/marketingspot`` ----->with ``"ttl":259200``
set in ``caching.rules``

``www.mywebsite.com/videos`` ----->with ``"ttl":3600`` set in
``caching.rules``

Multiple caching rules example
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Caching rules are designed to determine how long your content should
live on the edge before checking the origin for an update. If your
content changes frequently, you might want to set up a Time To Live
(TTL) rule that pulls every few minutes. If your content does not change
frequently, we suggest that you set a longer TTL of 12 to 24 hours. If
you create multiple rules, you must order rules from least specific to
most specific.

For example, you want most of the content on your website to have a TTL
of 3 days. The only exception is your dynamic content, hosted on your
origin at ``/dynamic``, which you want to have a TTL of 0 because the
experience changes for every user. 

In this case, you should order your TTL ``caching.rules`` as follows:

``www.mywebsite.com`` -----> with ``"ttl":259200`` set in
``caching.rules``

``www.mywebsite.com/dynamic`` -----> with ``"ttl":0`` set
in\ ``             caching.rules``

Multiple origin rules example
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can have Rackspace CDN point to multiple origin servers.

If you have multiple infrastructures setup to serve a single domain, you
should use origin rules. Adding an additional origin always requires
that you add a rule for which traffic should pull from that origin. If
you create multiple rules, you must order rules from least specific to
most specific.

For example, most of the content from your website should pull from your
Cloud Server origin, hosted at ``origin.cloudserver.com``. However, any
requests with the URL ``website.com/dedicated`` should be routed to your
dedicated server, hosted at ``origin.dedicatedserver.com``. In this
case, you should order your ``origin.rules`` as follows:  

``origin.cloudserver.com`` -----> with ``origin=origin.cloudserver.com``
in ``origin.rules``

``origin.dedicatedserver.com`` -----> with
``origin=origin.dedicatedserver.com`` in ``origin.rules``

Referrer rules example
~~~~~~~~~~~~~~~~~~~~~~

Restriction rules limit who can see your content and are designed to
show a list of traffic you allow. For example, a ``referrer`` value of
``website.com`` would allow traffic being requested from
``website.com``.

Unlike TTL rules, referrer restrictions are always applied to the full
CDN-enabled domain.  In other words, Rackspace CDN always sets your
referrer restriction to have a path of ``/``. 

Using referrer rules prevents other sites from hot-linking to your
content. Without this, someone might copy the link to your images and
serve those images on their site while your pay for the bandwidth. 

To avoid hot-linking, set up a rule that only allows your content to be
served to an end user if it is being requested by your domain. 

To do this, set up ``restrictions.rules.referrer`` similar to the
following definition:

``/`` -----> with ``"referrer":"www.mywebsite.com"`` set in
``restrictions.rules``

