.. _gsg-list-flavors

Retrieve flavors
~~~~~~~~~~~~~~~~

A flavor is a mapping configuration to the Akamai CDN provider. This
operation retrieves a list of all available flavors.

 
**cURL retrieve flavors request**

.. code:: bash

   curl -i -X GET $API_ENDPOINT/v1.0/$TENANT_ID/flavors \
   -H "X-Auth-Token: $AUTH_TOKEN" \
   -H "Content-type: application/json" 

 
**Retrieve flavors response**

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
