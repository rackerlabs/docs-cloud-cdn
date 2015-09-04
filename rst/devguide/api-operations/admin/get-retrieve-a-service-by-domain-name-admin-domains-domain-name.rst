
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _get-retrieve-a-service-by-domain-name-admin-domains-domain-name:

Retrieve a service by domain name
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET //admin/domains/{domain_name}

Retrieves a service by domain name.

This operation retrieves a service by domain name. 

.. note::
   This endpoint is accessible only by users with the ``support`` role in their Cloud Identity service catalog.
   
   



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{domain_name}             |String                   |The name of the domain.  |
|                          |                         |For example,             |
|                          |                         |blog.mywebsite.com.      |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example Retrieve a service by domain name: JSON request**


.. code::

   GET /v1.0/110011/admin/domains/blog.mywebsite.com HTTP1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   





Response
""""""""""""""""










**Example Retrieve a service by domain name: JSON response**


.. code::

   HTTP/1.1 200 OK
   Content-Type: application/json


.. code::

   {
       "id": "96737ae3-cfc1-4c72-be88-5d0e7cc9a3f0",
       "name": "mywebsite.com",
       "domains": [
           {
               "domain": "blog.mywebsite.com"
           }
       ],
       "origins": [
           {
               "origin": "mywebsite.com",
               "port": 443,
               "ssl": false,
               "hostheadertype": "origin",
               "hostheadervalue": "mywebsite.com"
           },
           {
               "origin": "77.66.55.44",
               "port": 443,
               "ssl": false,
               "rules": [
                   {
                       "name": "videos",
                       "request_url": "^/videos/*.m3u"
                   }
               ],
               "hostheadertype": "domain",
               "hostheadervalue": null
           }
       ],
       "caching": [
           {
               "name": "default",
               "ttl": 3600
           },
           {
               "name": "home",
               "ttl": 17200,
               "rules": [
                   {
                       "name": "index",
                       "request_url": "/index.htm"
                   }
               ]
           },
           {
               "name": "images",
               "ttl": 12800,
               "rules": [
                   {
                       "name": "images",
                       "request_url": "*.png"
                   }
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
       "flavor_id" : "europe",
       "log_delivery" : {
           "enabled": true
       },
       "status" : "deployed",
       "errors" : [],
       "links": [
           {
               "href": "https://www.poppycdn.io/v1.0/services/96737ae3-cfc1-4c72-be88-5d0e7cc9a3f0",
               "rel": "self"
           },
           {
               "href": "mywebsite.com.poppycdn.net",
               "rel": "access_url"
           },
           {
               "href": "https://www.poppycdn.io/v1.0/flavors/europe",
               "rel": "flavor"
           },
           {
               "href" : "https://swiftstorageurl.com/v1.0/.ACCESS_LOGS",
               "rel" : "log_url"
           }
       ]
   }




