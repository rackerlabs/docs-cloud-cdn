.. _cdn-create-a-service:

Create a service
~~~~~~~~~~~~~~~~

.. code::

    POST /v1.0/{project_id}/services

This operation creates a service.

To create a new service, provide a JSON body for the new service with the required attributes.

For more information about rules ordering, caching rules, origin rules, and restrictions rules, see :how-to:`Rackspace CDN edge rules<rackspace-cdn-edge-rules>`.

For origin rules, use the path /* to include all content for the site.

.. note::
   ``service_id``, which is used in several of the services operations, is returned in the response to create a service. Take note this value. You can also retrieve ``service_id`` using :ref:`Retrieve a service <cdn-get-a-service>`.

The following table shows the possible response codes for this operation.

+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |Accepted                 |The request has been     |
|                          |                         |accepted for processing. |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Attempt to create a      |
|                          |                         |service with a flavor_id |
|                          |                         |that is not 'cdn'.       |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Invalid JSON.            |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Missing or empty domains |
|                          |                         |list.                    |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Missing or empty origins |
|                          |                         |list.                    |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Non-Boolean value for    |
|                          |                         |origins:origin:ssl.      |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Restrictions list        |
|                          |                         |present with no name.    |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Value for                |
|                          |                         |origins:origin:port is   |
|                          |                         |something other than 80  |
|                          |                         |or 443.                  |
+--------------------------+-------------------------+-------------------------+

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

The following table shows the body parameters for the request.

+-----------------------+-------------+------------------------------------------------------------------------------+
|Name                   |Type         |Description                                                                   |
+=======================+=============+==============================================================================+
|\ **name**             |String       |Specifies the name of the service. The minimum length for ``name`` is 3. The  |
|                       |*(Required)* |maximum length is 256.                                                        |
+-----------------------+-------------+------------------------------------------------------------------------------+
|\ **domains**          |String       |Specifies a list of domains used by users to access their website.            |
|                       |*(Required)* |                                                                              |
+-----------------------+-------------+------------------------------------------------------------------------------+
|\ domains.\            |String       |Specifies the domain used to access the assets on your website, for which you |
|**domain**             |*(Required)* |use a CNAME to the CDN provider. The minimum length for domain is 3. The      |
|                       |             |maximum length is 253.                                                        |
+-----------------------+-------------+------------------------------------------------------------------------------+
|domains.\ **protocol** |String       |Specifies the protocol used to access the assets on this domain. Only         |
|                       |             |``http`` or ``https`` are allowed. The default ``protocol`` is ``http``.      |
+-----------------------+-------------+------------------------------------------------------------------------------+
|domains.\              |String       |Specifies the type of security certificate. For the ``certificate`` parameter |
|**certificate**        |             |to apply, the ``protocol`` parameter must be set to ``https``. Use            |
|                       |             |``shared``, ``san``, or ``custom``. For all 3 types of security certificates, |
|                       |             |make sure that your origin (or origins) are SSL-enabled. Your SSL certificate |
|                       |             |needs to come from a trusted certificate authority (CA). For more information |
|                       |             |about security certificates and Rackspace CDN, see                            |
|                       |             |:how-to:`Rackspace CDN secure delivery options                                |
|                       |             |<rackspace-cdn-secure-delivery-options>`.                                     |
+-----------------------+-------------+------------------------------------------------------------------------------+
|domains.certificate.\  |String       |Uses a shared https operator domain. The ``domain`` parameter must be a       |
|**shared**             |             |single word that is not dot separated.                                        |
+-----------------------+-------------+------------------------------------------------------------------------------+
|\ **origins**          |String       |Specifies a list of origin domains or IP addresses where the original assets  |
|                       |*(Required)* |are stored.                                                                   |
+-----------------------+-------------+------------------------------------------------------------------------------+
|\ origins.\            |String       |Specifies the URL or IP address from which to pull origin content. The        |
|**origin**             |*(Required)* |minimum length for ``origin`` is 3. The maximum length is 253.                |
+-----------------------+-------------+------------------------------------------------------------------------------+
|origins.\ **port**     |String       |Specifies the port used to access the origin. The default is port 80. Note:   |
|                       |             |Rackspace CDN cannot be used with custom ports. Services are required to run  |
|                       |             |on HTTP (80) and HTTPS (443) for the origin servers. All origins in the       |
|                       |             |origin specification must define the port so that it that corresponds to the  |
|                       |             |domain's protocol. If the domain's protocol is http, the port should be 80;   |
|                       |             |if the domain's protocol is https, the port should be 443.                    |
+-----------------------+-------------+------------------------------------------------------------------------------+
|origins.\ **ssl**      |String       |Uses HTTPS to access the origin. The default is false.                        |
|                       |             |                                                                              |
+-----------------------+-------------+------------------------------------------------------------------------------+
|origins.\ **rules**    |String       |Specifies a collection of rules that define the conditions when this origin   |
|                       |*(Required)* |should be accessed. If there is more than one origin, the ``rules`` parameter |
|                       |             |is required.                                                                  |
+-----------------------+-------------+------------------------------------------------------------------------------+
|origins.rules.\        |String       |Specifies the name of this rule. The minimum length for ``name`` is 1. The    |
|**name**               |*(Required)* |maximum length is 256.                                                        |
+-----------------------+-------------+------------------------------------------------------------------------------+
|origins.rules.\        |String       |Specifies the request URL that this rule should match for this origin to be   |
|**request_url**        |*(Required)* |used. The minimum length for ``request_url`` is 1. The maximum length is      |
|                       |             |1024. Regex is supported. Note: Use a Perl Compatible Regex (PCRE). For more  |
|                       |             |information about PRCE, see `Regular Expressions (Perl-Compatible)            |
|                       |             |<http://php.net/manual/en/book.pcre.php>`__.                                  |
+-----------------------+-------------+------------------------------------------------------------------------------+
|origins.\              |String       |Specifies the type for the host header. The default value is ``domain``.      |
|**hostheadertype**     |             |Other valid values are ``origin`` and ``custom``.                             |
+-----------------------+-------------+------------------------------------------------------------------------------+
|origins.\              |String       |Specifies the value to be contained in the host header. The default value is  |
|**hostheadervalue**    |             |``NULL``; this value is assigned only when ``hostheadertype`` is ``domain``.  |
|                       |             |You are required to specify ``hostheadervalue`` only when ``hostheadertype``  |
|                       |             |is specified as ``custom``. If you specify ``hostheadertype`` as ``origin``,  |
|                       |             |``hostheadervalue`` takes the value of the origin domain.                     |
+-----------------------+-------------+------------------------------------------------------------------------------+
|\ **caching**          |String       |Specifies the TTL rules for the assets under this service. Supports wildcards |
|                       |             |for fine-grained control.                                                     |
+-----------------------+-------------+------------------------------------------------------------------------------+
|caching.\ **name**     |String       |Specifies the name of this caching rule. The minimum length for ``name`` is   |
|                       |*(Required)* |1. The maximum length is 256. Note: ``default`` is a reserved name used for   |
|                       |             |the default TTL setting.                                                      |
+-----------------------+-------------+------------------------------------------------------------------------------+
|caching.\ **ttl**      |String       |Specifies the TTL to apply. The value of ``ttl`` must be greater than or      |
|                       |*(Required)* |equal to 0. The maximum value that you can specify is 365 days.               |
+-----------------------+-------------+------------------------------------------------------------------------------+
|caching.\ **rules**    |String       |Specifies a collection of rules that determine if this TTL should be applied  |
|                       |             |to an asset. Note: This is a required property if more than one entry is      |
|                       |             |present for caching.                                                          |
+-----------------------+-------------+------------------------------------------------------------------------------+
|caching.rules.\        |String       |Specifies the name of this rule. The minimum length for ``name`` is 1. The    |
|**name**               |*(Required)* |maximum length is 256.                                                        |
+-----------------------+-------------+------------------------------------------------------------------------------+
|caching.rules.\        |String       |Specifies the request URL that this rule should match for this TTL to be      |
|**request_url**        |*(Required)* |used. The minimum length for ``request_url`` is 1. The maximum length is      |
|                       |             |1024. Regex is supported. Note: Use a Perl Compatible Regex (PCRE). For more  |
|                       |             |information about PRCE, see `Regular Expressions (Perl-Compatible)            |
|                       |             |<http://php.net/manual/en/book.pcre.php>`__.                                  |
+-----------------------+-------------+------------------------------------------------------------------------------+
|\ **restrictions**     |String       |Specifies the restrictions that define who can access assets (content from    |
|                       |             |the CDN cache).                                                               |
+-----------------------+-------------+------------------------------------------------------------------------------+
|restrictions.\ **name**|String       |Specifies the name of this restriction. The minimum length for ``name`` is 1. |
|                       |*(Required)* |The maximum length is 256.                                                    |
+-----------------------+-------------+------------------------------------------------------------------------------+
|restrictions.\         |String       |Specifies the type of this restriction. Valid values are ``whitelist``, which |
|**access**             |             |is the default value and allows access, or ``blacklist``, which does not      |
|                       |             |allow access. Note that ``blacklist`` and ``whitelist`` must use different    |
|                       |             |paths.                                                                        |
+-----------------------+-------------+------------------------------------------------------------------------------+
|restrictions.\         |String       |Specifies a collection of rules that determine if this restriction should be  |
|**rules**              |             |applied to an asset.                                                          |
+-----------------------+-------------+------------------------------------------------------------------------------+
|restrictions.rules.\   |String       |Specifies the name of this rule. The minimum length for ``name`` is 1. The    |
|**name**               |*(Required)* |maximum length is 256.                                                        |
+-----------------------+-------------+------------------------------------------------------------------------------+
|restrictions.rules.\   |String       |Specifies the HTTP host that requests must come from. The minimum length for  |
|**referrer**           |             |``referrer`` is 3. The maximum length is 1024.                                |
+-----------------------+-------------+------------------------------------------------------------------------------+
|restrictions.rules.\   |String       |Specifies the request URL to which the rule applies. The default value is     |
|**request_url**        |             |``/*``, which indicates all content at the request URL.                       |
+-----------------------+-------------+------------------------------------------------------------------------------+
|restrictions.rules.\   |String       |Specifies the geography from which to restrict requests.                      |
|**geography**          |             |                                                                              |
+-----------------------+-------------+------------------------------------------------------------------------------+
|restrictions.rules.\   |String       |Specifies the client IP address to which the rule applies. Note: Rackspace CDN|
|**client_ip**          |             |supports Classless Inter-Domain Routing (CIDR) for both IPv4 and IPv6 for     |
|                       |             |these restrictions.                                                           |
+-----------------------+-------------+------------------------------------------------------------------------------+
|\ **log_delivery**     |String       |Specifies whether to enable log delivery to a Cloud Files container. You can  |
|                       |*(Required)* |use access log delivery to analyze the number of requests for each object,    |
|                       |             |the client IP address, and time-based usage patterns (such as monthly or      |
|                       |             |seasonal usage).                                                              |
|                       |             |                                                                              |
|                       |             |Log files are named according to the following pattern:                       |
|                       |             |service name, log date, log hour, and MD5 hash. For example:                  |
|                       |             |``www.mywebsite.com/2015/02/01/16/096e6c4473f235db081deb51f42a8d98.log.gz``.  |
|                       |             |In this example, ``www.mywebsite.com`` is the name of the service,            |
|                       |             |``2015/02/01`` is the date (February 1, 2015), and ``16`` is the hour that    |
|                       |             |the log file was created. There might be multiple files for a given hour      |
|                       |             |because the system splits log files based on both time and log file size.     |
|                       |             |                                                                              |
|                       |             |All times in the access logs are UTC time. Within the gzip logs, the format of|
|                       |             |the entries is similar to National Center for Supercomputing Applications     |
|                       |             |(NCSA) combined log format, but without cookies. The pattern follows. The     |
|                       |             |dashes (-) denote fields that the NCSA combined log format dictates be        |
|                       |             |present but that Rackspace CDN does not capture.                              |
|                       |             |                                                                              |
|                       |             |For example: ``client_ip - - [day/month/year:hour:minute:second timezone]     |
|                       |             |“method request HTTP_version” return_code bytes_sent “referrer” “user_agent”``|
|                       |             |                                                                              |
|                       |             |Logs are stored in a Cloud Files container named.CDN_ACCESS_LOGS. If this     |
|                       |             |container does not exist, itis created.                                       |
+-----------------------+-------------+------------------------------------------------------------------------------+
|log_delivery.\         |String       |Specifies whether to enable or disable log delivery. Valid values are         |
|**enabled**            |*(Required)* |``true`` and ``false``.                                                       |
+-----------------------+-------------+------------------------------------------------------------------------------+
|\ **flavor_id**        |String       |Specifies the CDN provider flavor ID to use. For a list of flavors, see the   |
|                       |*(Required)* |operation to list the available flavors. The minimum length for ``flavor_id`` |
|                       |             |is 3. The maximum length is 256.                                              |
+-----------------------+-------------+------------------------------------------------------------------------------+

**Example: Create a service HTTP and JSON request**

.. code::

   POST /v1.0/110011/services HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json

.. code::

   {
       "name": "mywebsite.com",
       "domains": [
           {
               "domain": "www.mywebsite.com"
           },
           {
               "domain": "blog.mywebsite.com"
           }
       ],
       "origins": [
           {
               "origin": "mywebsite.com",
               "port": 80,
               "ssl": false,
               "hostheadertype": "origin",
               "rules": [
               ]
           }
       ],
       "restrictions": [
                        {
                        "name": "website only",
                        "rules": [
                                  {
                                  "name": "mywebsite.com",
                                  "referrer": "www.mywebsite.com"
                   }
               ]
           }
       ],
       "caching": [
           {
               "name": "default",
               "ttl": 3600
           }
       ],
       "log_delivery": {
           "enabled": true
       },
       "flavor_id": "cdn"
      }

Response
--------

This operation does not return a response body.

**Example: Create a service HTTP response**

.. code::

   HTTP/1.1 202 Accepted
   Content-Type: application/json
   Location: https://global.cdn.api.rackspacecloud.com/v1.0/services/96737ae3-cfc1-4c72-be88-5d0e7cc9a3f0
