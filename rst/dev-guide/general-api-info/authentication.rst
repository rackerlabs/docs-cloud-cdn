.. _authentication:

Authenticate through the Rackspace Cloud Identity Service
---------------------------------------------------------

To authenticate access to the Rackspace CDN service, you issue an
authentication request to the Rackspace Cloud Identity Service endpoint.

In response to valid credentials, an authentication request to the
Rackspace Cloud Identity Service returns an authentication token and a
service catalog that contains a list of all services and endpoints
available for this token. Because the authentication token expires after
24 hours, you must generate a token each day that you need access.

The following sections list the Rackspace Cloud Identity Service
endpoint, show you how make an authentication request, and describe the
authentication response.

For detailed information about the Identity Service v2.0, see the
*Cloud Identity Client Developer Guide API v2.0*.

Rackspace Cloud Identity Service Endpoint
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When you authenticate, use the following endpoint:
``https://identity.api.rackspacecloud.com/v2.0/``

Authentication Request
~~~~~~~~~~~~~~~~~~~~~~

To authenticate, issue a **POST** **/tokens** request to the Rackspace Cloud Identity
Service endpoint.

In the request body, supply one of the following sets of credentials:

-  Username and password

-  Username and API key

Your username and password are the ones that you use to log in to the
Rackspace Cloud Control Panel.

.. note:: If you authenticate with username and password credentials, you can
   use multi-factor authentication to add an additional level of account
   security. This feature is not implemented for username and API
   credentials. For more information, search for multifactor authentication
   on the Rackspace site.

To find your API key, perform the following steps:

#. Log in to the Cloud Control Panel (https://mycloud.rackspace.com).

#. On the upper-right side of the top navigation pane, click your
   username.

#. From the menu, select Account Settings.

#. In the Login Details section of the Account Settings page, locate the
   API Key field and click Show.

The following cURL examples show how to get an authentication token by
entering your username and either password or your API key.

**Example: Authenticate to the Identity Endpoint – Username and
Password: JSON Request**

.. code::

    $ curl -s https://identity.api.rackspacecloud.com/v2.0/tokens -X 'POST' \
         -d '{"auth":{"passwordCredentials":{"username":"MyRackspaceAcct", \
         "password":"MyRackspacePwd"}}}' \
         -H "Content-Type: application/json" | python -m json.tool

**Example: Authenticate to the Identity Endpoint – Username and API
Key: JSON Request**

.. code::

    $ curl -s https://identity.api.rackspacecloud.com/v2.0/tokens -X 'POST' \
         -d '{"auth":{"RAX-KSKEY:apiKeyCredentials":{"username":"MyRackspaceAcct", "apiKey":"0000000000000000000"}}}' \
         -H "Content-Type: application/json" | python -m json.tool


.. note::
   In these examples, the following pipe command makes the JSON output
   more readable:
   ::

   | python -m json.tool

Authentication Response
~~~~~~~~~~~~~~~~~~~~~~~

In response to valid credentials, your request returns an authentication
token and a service catalog with the endpoints that you use to request
services.

Do not include explicit API endpoints in your scripts and applications.
Instead, find the endpoint for your service and region in your service catalog and use it.

.. note::
   If you authenticated with username and password credentials, and the
   Identity service returns a 401 message requesting additional credentials,
   your account is configured for multi-factor authentication.

   To complete the authentication process, submit a second POST tokens
   request with multi-factor authentication credentials.

The following output shows a partial authentication response in JSON
format:

**Example: Authenticate: JSON Response**

.. code::

    {
        "access": {
            "serviceCatalog": [
                {
                    "endpoints": [
                        {
                            "internalURL": "https://snet-storage101.dfw1.clouddrive.com/v1/MossoCloudFS_530f8649-324c-499c-a075-2195854d52a7",
                            "publicURL": "https://storage101.dfw1.clouddrive.com/v1/MossoCloudFS_530f8649-324c-499c-a075-2195854d52a7",
                            "region": "DFW",
                            "tenantId": "MossoCloudFS_530f8649-324c-499c-a075-2195854d52a7"
                        },
                        {
                            "internalURL": "https://snet-storage101.ord1.clouddrive.com/v1/MossoCloudFS_530f8649-324c-499c-a075-2195854d52a7",
                            "publicURL": "https://storage101.ord1.clouddrive.com/v1/MossoCloudFS_530f8649-324c-499c-a075-2195854d52a7",
                            "region": "ORD",
                            "tenantId": "MossoCloudFS_530f8649-324c-499c-a075-2195854d52a7"
                        }
                    ],
                    "name": "cloudFiles",
                    "type": "object-store"
                },
 				{
        			"endpoints": [
          				{
            				"region": "IAD",
            				"tenantId": "820712",
            				"publicURL": "https://iad.images.api.rackspacecloud.com/v2"
          				},
	          			{
    	        			"region": "ORD",
        	    			"tenantId": "820712",
            				"publicURL": "https://ord.images.api.rackspacecloud.com/v2"
          				},
          				{
	           			 	"region": "HKG",
    	        			"tenantId": "820712",
        	    			"publicURL": "https://hkg.images.api.rackspacecloud.com/v2"
          				},
          				{
            				"region": "DFW",
            				"tenantId": "820712",
	            			"publicURL": "https://dfw.images.api.rackspacecloud.com/v2"
    	      			},
        	  			{
            				"region": "SYD",
            				"tenantId": "820712",
            				"publicURL": "https://syd.images.api.rackspacecloud.com/v2"
          				}
        			],
        			"name": "cloudImages",
        			"type": "image"
      			},
                {
                    "endpoints": [
                        {
                            "publicURL": "https://dfw.servers.api.rackspacecloud.com/v2/010101",
                            "region": "DFW",
                            "tenantId": "010101",
                            "versionId": "2",
                            "versionInfo": "https://dfw.servers.api.rackspacecloud.com/v2",
                            "versionList": "https://dfw.servers.api.rackspacecloud.com/"
                        },
                        {
                            "publicURL": "https://ord.servers.api.rackspacecloud.com/v2/010101",
                            "region": "ORD",
                            "tenantId": "010101",
                            "versionId": "2",
                            "versionInfo": "https://ord.servers.api.rackspacecloud.com/v2",
                            "versionList": "https://ord.servers.api.rackspacecloud.com/"
                        }
                    ],
                    "name": "cloudServersOpenStack",
                    "type": "compute"
                }
                {
                 "endpoints":[
                     {
                         "tenantId":"110011",
                         "publicURL":"https://global.cdn.api.rackspacecloud.com/v1.0/110011",
                         "region":"IAD"
                     },
                     {
                         "tenantId":"110011",
                         "publicURL":"https://global.cdn.api.rackspacecloud.com/v1.0/110011",
                         "region":"LON"
                     }
            ],
            "name":"rackCDN",
            "type":"rax:cdn"
            }            ],
            "token": {
                "expires": "2012-09-14T15:11:57.585-05:00",
                "id": "858fb4c2-bf15-4dac-917d-8ec750ae9baa",
                "tenant": {
                    "id": "010101",
                    "name": "010101"
                }
            },
            "user": {
                "RAX-AUTH:defaultRegion": "DFW",
                "id": "170454",
                "name": "MyRackspaceAcct",
                "roles": [
                    {
                        "description": "User Admin Role.",
                        "id": "3",
                        "name": "identity:user-admin"
                    }
                ]
            }
        }
    }


Successful authentication returns the following information:

**Endpoints to request Rackspace Cloud services**. Appears in the
``endpoints`` element in the ``serviceCatalog`` element.

Endpoint information includes the public URL, which is the endpoint that
you use to access the service, as well as region, tenant ID, and version
information.

To access the Rackspace CDN service, use the endpoint for the ``rackCDN`` service.

**Tenant ID**. Appears in the ``tenantId`` field in the ``endpoints``
element. The tenant ID is also known as the account number or the project ID.

You include the tenant ID in the endpoint URL when you call a cloud
service.

**The name of the service**. Appears in the ``name`` field.

Locate the correct service name in the service catalog, as follows:

-  **Rackspace CDN**. Named ``rackCDN`` in the catalog.

   To access the Rackspace CDN service, use the ``publicURL`` value for the
   ``rackCDN`` service.

   The service might show multiple endpoints to enable regional
   choice. Select the appropriate endpoint for the region that you want
   to interact with by examining the ``region`` field.


If you use the authentication token to access this service, you can perform Rackspace CDN 
API operations.

**Expiration date and time for authentication token**. Appears in the
``expires`` field in the ``token`` element.

After this date and time, the token is no longer valid.

This field predicts the maximum lifespan for a token, but does not
guarantee that the token reaches that lifespan.

Clients are encouraged to cache a token until it expires.

Because the authentication token expires after 24 hours, you must
generate a token once a day.

**Authentication token**. Appears in the ``id`` field in the ``token``
element.

You pass the authentication token in the ``X-Auth-Token`` header each
time that you send a request to a service.

Once you have your authentication token and your endpoint you are ready to send a
request to the Rackspace CDN service.

In the following example, you first export the tenant ID, ``010101``, to the
``account`` environment variable and the authentication token to the
``token`` environment variable. Then, you issue a cURL command to send a
request to list all Rackspace CDN services as follows:

.. code::

    $ export account="010101"
    $ export token="00000000-0000-0000-000000000000"
    $ curl -s https://global.cdn.api.rackspacecloud.com/v1.0/yourAccountID/services \
         -X "GET" -H "X-Auth-Token: $token" | python -m json.tool
