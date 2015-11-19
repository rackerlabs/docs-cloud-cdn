.. _gsg-list-flavors

Retrieve flavors
~~~~~~~~~~~~~~~~

A flavor is a mapping configuration to the Akamai CDN provider. This
operation retrieves a list of all available flavors.

 
**Example: Retrieve flavors: Request**

.. code::  

   curl -i -X GET https://global.cdn.api.rackspacecloud.com/v1.0/yourAccountID/flavors \
   -H "X-Auth-Token: yourAuthToken" \
   -H "Content-type: application/json" 

 
**Example: Retrieve flavors: Response**

.. code::  

   HTTP/1.1 200 OK
   Content-Type: application/json 

    {     
      "flavors": [                 
        {
            "id": "cdn",
            "providers": [
                {
                    "provider": "akamai",
                    "links": [
                        {
                            "href": "http://www.akamai.com",
                            "rel": "provider_url"
                        }
                    ]
                }
            ],
            "links": [
                {
                    "href": "https://global.cdn.api.rackspacecloud.com/v1.0/yourAccountID/flavors/cdn",
                    "rel": "self"
                }
            ]
        }
    ]
