.. _gsg-delete-service:

Deleting a service
~~~~~~~~~~~~~~~~~~

This operation deletes a service.
 
**Example: cURL delete a service request**

.. code:: bash

   curl -i -X DELETE $API_ENDPOINT/v1.0/$TENANT_ID/services/yourServiceID \
   -H "Content-type: application/json" \
   -H "X-Auth-Token: $AUTH_TOKEN" \
   -H "Accept: application/json"

**Example: Delete a service response**

.. code::

   HTTP/1.1 202 Accepted
