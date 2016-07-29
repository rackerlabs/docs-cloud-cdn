.. _absolute-limits:

Absolute limits
~~~~~~~~~~~~~~~

The following table provides details about the absolute limits for the
Rackspace CDN API.

**Table: Absolute limits**

+----------------------------+------------------------------+-----------------+
| Name                       | Description                  | Limit           |
+============================+==============================+=================+
| Client maximum body        | Maximum size of request body.| 8 KB            |
| size restriction           | Exceeding the limit results  |                 |
|                            | in a 413 (Request Entity Too |                 |
|                            | Large) error.                |                 |
+----------------------------+------------------------------+-----------------+
| Maximum for the entire     | Maximum size of request URI. | 320 characters  |
| length for a domain        | Exceeding the limit results  |                 |
| URI                        | in a 414 (URI Too Long)      |                 |
|                            | error.                       |                 |
+----------------------------+------------------------------+-----------------+
| TTL when creating          | Maximum TTL value.           | 365 days        |
| a service                  |                              |                 |
+----------------------------+------------------------------+-----------------+
| Limit on the number        | Maximum number of domains    | 20 domains      |
| of domains that can        | that can be listed.          |                 |
| be listed when             |                              |                 |
| retrieving all             |                              |                 |
| services                   |                              |                 |
+----------------------------+------------------------------+-----------------+
| Rate limit on the          | Number of requests per       | 20 requests per |
| :ref:`Purge a cached       | minute.                      | minute          |
| asset operation            |                              |                 |
| <cdn-purge-a-cached-asset>`|                              |                 |
+----------------------------+------------------------------+-----------------+
