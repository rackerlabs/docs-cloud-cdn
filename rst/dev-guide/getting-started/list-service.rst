.. _gsg-list-service:

Retrieve a created service
~~~~~~~~~~~~~~~~~~~~~~~~~~

Perform a **GET** request on the ``Location`` header that was returned
in :ref:`Create a service <gsg-create-service>`.
 
**Example: Retrieve a service: Request**

.. code::  

   curl -i -X GET https://global.cdn.api.rackspacecloud.com/v1.0/yourAccountID/services/yourServiceID \
   -H "X-Auth-Token: yourAuthToken" \
   -H "Content-type: application/json" 

You see a response body similar to the one in the following example.

 
**Example: Retrieve a service: Response**

.. code::  

   HTTP/1.1 200 OK
   Content-Type: application/json 
       
    {
        "id": "yourServiceID",  
        "name": "mywebsite.com",
        "domains": [
            {
                "domain": "www.mywebsite.com",
                "protocol": "https"                 
            }
        ],
        "origins": [
            {
                "origin": "mywebsite.com",
                "port": 443,
                "ssl": false,
                 "rules": []                 
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
        "flavor_id": "cdn",
        "status": "deployed",
        "errors": [],                 
        "links": [
            {
                "href": "https://global.cdn.api.rackspacecloud.com/v1.0/yourAccountID/services/yourServiceID",
                "rel": "self"
            },
            {   "href": "https://global.cdn.api.rackspacecloud.com/v1.0/yourAccountID/flavors/cdn",
                "rel": "flavor"
            },                                  
            {
                "href": "www.mywebsite.com.cdn1.raxcdn.com",
                "rel": "access_url"
            }
        ]
    }
