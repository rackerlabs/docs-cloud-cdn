.. _limits:

===============
Absolute limits
===============

The following table provides details about the absolute limits for the
Rackspace CDN API.

.. list-table:: **Absolute limits**
   :widths: 20 40 10
   :header-rows: 1

   * - Name
     - Description
     - Limit
   * - Client maximum body size restriction
     - Maximum size of request body. Exceeding the limit results in a 413
       (Rquest Entity Too Large) error.
     - 8 KB
   * - Maximum for the entire length for a domain URI
     - Maximum size of request URI. Exceeding the limit results in a 414
       (URI Too Long) error.
     - 320 characters
   * - TTL when creating a service
     - Maximum TTL value.
     - 365 days
   * - Limit on the number of services per page that can be listed when retrieving
       all services
     - Maximum number of services that can be listed, per page.
     - 20 services
   * - Limit on the number of domains per service
     - Maximum domains per service.
     - 10 domains
   * - Rate limit on the :ref:`Purge a cached asset operation \
       <cdn-purge-a-cached-asset>`
     - Number of requests per minute.
     - 20 requests per minute
