.. _gsg-create-service:

Creating a service 
~~~~~~~~~~~~~~~~~~

A service represents an application that has its content cached to the
edge nodes, such as a website. To create a service, issue a **POST**
request and provide a JSON body with the required attributes for the new
service. (Each of these attributes is described in the *Rackspace CDN
Developer Guide* in the create service operation description.)

The service defines the domain used to access the website via CDN, and
the origin from which to pull content.

Following are examples of a create service request and response.

**Example: cURL create a service request**

.. code:: bash

   curl -i -X POST $API_ENDPOINT/v1.0/$TENANT_ID/services \
   -H "Accept: application/json" \
   -H "X-Auth-Token: $AUTH_TOKEN" \
   -H "Content-Type: application/json" -d \
    '{
        "name": "mywebsite.com",
        "domains": [
            {"domain": "www.mywebsite.com", "protocol": "https"},
            {"domain": "blog.mywebsite.com", "protocol": "https"}
        ],
        "origins": [
            {
                "origin": "mywebsite.com",
                "port": 443,
                "ssl": false,
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
        "flavor_id": "cdn"
    }'

When the service is created, you see an HTTP 202 response with the
``Location`` header returned.

**Example: Create a service response**

.. code::

   HTTP/1.1 202 Accepted
   Content-TYpe: application/json
   Location:  https://global.cdn.api.rackspacecloud.com/v1.0/services/yourServiceID
