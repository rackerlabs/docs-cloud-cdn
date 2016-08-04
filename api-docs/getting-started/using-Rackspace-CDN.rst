.. _gsg-using-Rackspace-CDN:

===========================
Create and manage a service
===========================

You can use the simple examples in the following sections for basic Rackspace
CDN requests that you will commonly use to create and manage a service by using
Rackspace CDN API operations. Example requests are provided in cURL, followed
by the response.

Before running the examples, review the :ref:`Rackspace CDN concepts<concepts>`.

To start using the API and run the examples in this section, you need the
following items:

- Rackspace Cloud account. If you don't have one, sign up for a
  :rax-cart:`Rackspace Cloud account <cloud>`.
- Username and password to access the account
- API key to access Rackspace Cloud services
- Account number
- :ref:`Command-line tool or browser client <send-api-requests>` for
  communicating with the API service.
- :ref:`Configured environment variables <configure-environment-variables>`

.. note::
     These examples use the ``$API_ENDPOINT``, ``$AUTH_TOKEN``, and
     ``$TENANT_ID`` environment variables to specify the API endpoint,
     authentication token, and account ID values for accessing the service.
     Make sure you
     :ref:`configure these variables<configure-environment-variables>` before
     running the code samples.

For more information about all Rackspace CDN operations, see the
:ref:`API reference <api-reference>`.

.. include:: examples/create-service.rst
.. include:: examples/list-service.rst
.. include:: examples/update-DNS.rst
.. include:: examples/access-website.rst
.. include:: examples/purge-asset.rst
.. include:: examples/list-flavors.rst
.. include:: examples/delete-service.rst
