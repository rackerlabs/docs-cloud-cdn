.. _gsg-purge-asset:

Purging a cached asset
~~~~~~~~~~~~~~~~~~~~~~

After working with the service you created, you might find that you want
to purge the current version of an asset that has been cached at the
edge node.

**Example: cURL purge a cached asset request**

.. code::

   curl -i -X DELETE $API_ENDPOINT/v1.0/$TENANT_ID/services/yourServiceID/assets?url=relativeURLofAssettoDelete \
   -H "X-Auth-Token: $AUTH_TOKEN" \
   -H "Content-type: application/json"

**Example: Purge a cached asset response**

.. code::

   HTTP/1.1 202 Accepted
