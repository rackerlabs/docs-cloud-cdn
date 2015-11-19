.. _gsg-delete-service:

Delete a service
~~~~~~~~~~~~~~~~

This operation deletes a service. Following are examples of a delete
service request and response:

 
**Example: Delete service: Request**

.. code::  

   curl -i -X DELETE https://global.cdn.api.rackspacecloud.com/v1.0/yourAccountID/services/yourServiceID \ 
   -H "Content-type: application/json" \
    -H "X-Auth-Token: yourAuthToken" \ 
   -H "Accept: application/json" 

 
**Example: Delete service: Response**

.. code::  

   HTTP/1.1 202 Accepted
