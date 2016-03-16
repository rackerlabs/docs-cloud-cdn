
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _post-update-the-san-certificate-sps-id-admin-provider-akamai-ssl-certificate-config-san-cert-name:

Update the SAN certificate SPS ID
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST //admin/provider/akamai/ssl_certificate/config/{san_cert_name}

Updates the SAN certificate SPS ID.

This operation updates the SAN certificate SPS ID.

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
|{san_cert_name}           |String                   |The name of the SAN      |
|                          |                         |certificate, such as     |
|                          |                         |secure1.san1.altcdn.com. |
+--------------------------+-------------------------+-------------------------+





This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|\ **spsId**               |String                   |Specifies the SPS ID to  |
|                          |                         |update.                  |
+--------------------------+-------------------------+-------------------------+





**Example Update the SAN certificate SPS ID: JSON request**


.. code::

   POST /v1.0/110011/admin/provider/akamai/ssl_certificate/config/{san_cert_name} HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   


.. code::

   {
       "spsId": 1234
   }





Response
""""""""""""""""





This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|\ **ipVersion**           |String                   |Specifies the the        |
|                          |                         |version of the IP you    |
|                          |                         |are using, such as       |
|                          |                         |``ipv4``.                |
+--------------------------+-------------------------+-------------------------+
|slot-deploymentclass      |String                   |Specifies the slot       |
|                          |                         |deployment class.        |
+--------------------------+-------------------------+-------------------------+
|\ **createType**          |String                   |Specifies the creating   |
|                          |                         |type for the certificate.|
+--------------------------+-------------------------+-------------------------+
|\ **jobId**               |String                   |Specifies the job ID.    |
+--------------------------+-------------------------+-------------------------+
|\ **createHostname**      |String                   |Specifies the creation   |
|                          |                         |host name.               |
+--------------------------+-------------------------+-------------------------+
|\ **spsId**               |String                   |Specifies the SPS ID.    |
+--------------------------+-------------------------+-------------------------+
|\ **issuer**              |String                   |Specifies who issued the |
|                          |                         |certificate.             |
+--------------------------+-------------------------+-------------------------+







**Example Update the SAN certificate SPS ID: JSON response**


.. code::

   HTTP/1.1 200 OK


.. code::

   {
     "ipVersion": "ipv4",
     "slot-deployment.class": "esslType",
     "createType": "modSan",
     "jobId": "5123",
     "cnameHostname": "secure2.san1.altcdn.com",
     "spsId": "1234",
     "issuer": "symantec"
   }




