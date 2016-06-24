
.. _get-san-mapping:

Retrieve the SAN-mapping list for the Akamai-related background job
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /admin/provider/akamai/background_job/san_mapping



This operation retrieves the SAN mapping for an Akamai-related background job.

In cases where an admin-defined queue was created, it was created with the
following parameters, which are defined in the response parameters table.

*  ``domain_name``
*  ``flavor_id``
*  ``project_id``
*  ``cert_type``
*  ``cert_details``





This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""

This operation does not require a request body.










**Example: Retrieve the SAN mapping for the Akamai-related background job HTTP request**


.. code::

   GET /v1.0/110011/admin/provider/akamai/background_job/san-mapping HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json










Response
""""""""""""""""


This table shows the body parameters for the response:


+------------------+-------------+---------------------------------------------+
|Name              |Type         |Description                                  |
+==================+=============+=============================================+
|\ **domain_name** |String       |Specifies a string representing the          |
|                  |             |the type of SSL certificate on the customer's|
|                  |             |domain name, such as                         |
|                  |             |``test-san1.cnamecdn.com``.                  |
+------------------+-------------+---------------------------------------------+
|\ **flavor_id**   |String       |Specifies the CDN provider flavor ID to use. |
+------------------+-------------+---------------------------------------------+
|\ **project_id**  |String       |Specifies the identifier for the user account|
|                  |             |account.                                     |
+------------------+-------------+---------------------------------------------+
|\ **cert_type**   |String       |Specifies the type of the SSL certificate.   |
|                  |             |The valid value is ``san``.                  |
+------------------+-------------+---------------------------------------------+
|\ **cert_details**|String       |Specifies certificate details for the        |
|                  |             |provider, which is ``Akamai`` for Rackspace  |
|                  |             |CDN.                                         |
+------------------+-------------+---------------------------------------------+
|cert_details.\    |String       |Specifies ``Akamai`` as the provider.        |
|**Akamai**        |             |                                             |
+------------------+-------------+---------------------------------------------+
|cert_details.\    |String       |Specifies additional information about the   |
|Akamai.\          |             |``Akamai`` SAN certificate.                  |
|**extra_info**    |             |                                             |
+------------------+-------------+---------------------------------------------+
|cert_details.\    |String       |Specifies the SAN certificate name.          |
|Akamai.\          |             |                                             |
|extra_info.\      |             |                                             |
|**san cert**      |             |                                             |
+------------------+-------------+---------------------------------------------+
|cert_details.\    |String       |Specifies Akamai SPS ID for the SAN          |
|Akamai.\          |             |certificate.                                 |
|extra_info.\      |             |                                             |
|**akamai_spsId**  |             |                                             |
+------------------+-------------+---------------------------------------------+








**Example: Retrieve the SAN-mapping list for the Akamai-related background job JSON response**


.. code::

   HTP/1.1 200 (OK)


.. code::

   [
     {
       "domain_name": "test-san1.cnamecdn.com",
       "flavor_id": "flavor_id",
       "project_id": "project_id",
       "cert_type": "san",
       "cert_details": {
         "Akamai": {
           "extra_info": {
             "san cert": "san1.example.com",
             "akamai_spsId": 1
           }
         }
       }
     },
     {
       "domain_name": "test-san2.cnamecdn.com",
       "flavor_id": "flavor_id",
       "project_id": "project_id",
       "cert_type": "san",
       "cert_details": {
        "Akamai": {
          "extra_info": {
            "san cert": "san2.example.com",
            "akamai_spsId": 2
          }
        }
      }
    }
 ]
