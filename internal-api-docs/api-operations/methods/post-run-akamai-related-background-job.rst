
.. _post-run-akamai-related-background-job:

Run Akamai-related background job
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    POST /admin/provider/akamai/background_job



This operation runs an Akamai-related background job.

.. note::
   Currently, the following types of jobs are supported: 
   
   * akamai_update_papi_property_for_mod_san (does not consume the queue)
   * akamai_check_and_update_cert_status (consumes the queue)

   You provide these values in the ``job_type`` parameters in the request.
   
   
   
   
   



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

+--------------------+-------------+---------------------------------------------+
|Name                |Type         |Description                                  |
+====================+=============+=============================================+
|\ **job_type**      |String       |Specifies the type of background job. The    |
|                    |*(Required)* |following types of jobs are supported:       |
|                    |             |``akamai_update_papi_property_for_mod_san``  |
|                    |             |and ``akamai_check_and_update_cert_status``. |
|                    |             |For each value of ``job_type``, see the      |
|                    |             |following parameters descriptions for        |
|                    |             |specific requirements.                       |
+--------------------+-------------+---------------------------------------------+
|\ **action**        |String       |When ``job_type`` is                         |
|                    |*(Optional)* |``akamai_update_papi_property_for_mod_san``, |
|                    |             |valid values for ``action`` are ``add`` or   |
|                    |             |``remove``.                                  |
+--------------------+-------------+---------------------------------------------+
|\ **update_type**   |String       |When ``job_type`` is                         |
|                    |*(Optional)* |``akamai_update_papi_property_for_mod_san``, |
|                    |             |the valid value is ``hostnames``.            |
+--------------------+-------------+---------------------------------------------+
|\ **property-spec** |String       |When ``job_type`` is                         |
|                    |*(Optional)* |``akamai_update_papi_property_for_mod_san``, |
|                    |             |the valid value is                           |
|                    |             |``akamai_https_san_config_numbers``.         |
+--------------------+-------------+---------------------------------------------+
|\ **project_id**    |String       |When ``job_type`` is                         |
|                    |*(Required)* |``akamai_check_and_update_cert_status``,     |
|                    |             |the valid value is the customers's project   |
|                    |             |ID.                                          |
+--------------------+-------------+---------------------------------------------+




**Example: Run Akamai-related background job JSON request**


.. code::

   POST /v1.0/110011/admin/provider/akamai/background_job HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   


.. code::
    
    {
      "job_type": "akamai_update_papi_property_for_mod_san"
    }   


or

.. code::

   POST /v1.0/110011/admin/provider/akamai/background_job HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   


.. code::
    
    {
      "job_type": "akamai_check_and_update_cert_status",
      "project_id": "000"
    } 




Response
""""""""""""""""






**Example: Run Akamai-related background job HTTP response**


.. code::

   HTP/1.1 202 (Accepted)
   




