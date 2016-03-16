
.. _post-run-akamai-related-background-job:

Run Akamai-related background job
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /admin/provider/akamai/background_job



This operation runs an Akamai-related background job.

.. note::
   The following types of jobs are supported: 
   
   * akamai_update_papi_property_for_mod_san
   * akamai_check_and_update_cert_status
   
   
   
   
   



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |Accepted                 |The request has been     |
|                          |                         |accepted for processing. |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""








This table shows the body parameters for the request:

+------------------+-------------+---------------------------------------------+
|Name              |Type         |Description                                  |
+==================+=============+=============================================+
|\ **job_type**    |String       |Specifies the type of job, such as           |
|                  |*(Required)* |``akamai_update_papi_property_for_mod_san``. |
+------------------+-------------+---------------------------------------------+
|\ **domain_name** |String       |Specifies a string representing the domain,  |
|                  |*(Required)* |such as ``testabc.cnamecdn.com``.            |
+------------------+-------------+---------------------------------------------+
|\                 |String       |Specifies the SAN certificate name, such as  |
|**san_cert_name** |*(Required)* |``secure1.san1.altcdn.com``.                 |
+------------------+-------------+---------------------------------------------+





**Example: Run Akamai-related background job JSON request**


.. code::

   POST /v1.0/110011/admin/provider/akamai/background_job HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   


.. code::

   {
         "job_type": "akamai_update_papi_property_for_mod_san",
         "domain_name": "testabc.cnamecdn.com",
         "san_cert_name": "secure1.san1.altcdn.com"
    }





**Example: Run Akamai-related background job JSON request**


.. code::

   POST /v1.0/110011/admin/provider/akamai/background_job HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   


.. code::

   {
       "job_type": "akamai_check_and_update_cert_status",
       "domain_name": "testabc.test_san.com",
       "project_id": "000",
       "cert_type": "san",
       "flavor_id": "cdn"
   }





Response
""""""""""""""""










**Example: Run Akamai-related background job HTTP response**


.. code::

   HTP/1.1 202 (Accepted)
   




