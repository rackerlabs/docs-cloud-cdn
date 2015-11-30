.. _gsg-purge-asset

Purge a cached asset
~~~~~~~~~~~~~~~~~~~~

After working with the service you created, you might find that you want
to purge the current version of an asset that has been cached at the
edge node.

 
**Example: Purge a cached asset: Request**

.. code::  

   curl -i -X DELETE https://global.cdn.api.rackspacecloud.com/v1.0/yourAccountID/services/yourServiceID/assets?url=relativeURLofAssettoDelete \
   -H "X-Auth-Token: yourAuthToken" \
   -H "Content-type: application/json"

 
**Example: Purge a cached asset: Response**

.. code::  

   HTTP/1.1 202 Accepted
