.. _paginated-collections:

=====================
Paginated collections
=====================

.. COMMENT: Adapt this topic to provide information that is relevant for your
   product.

To reduce load on the service, retrieve operations return a maximum limit of
items at a time. 

This behavior is called *pagination*. Pagination gives you the ability to
limit the size of the returned data and to retrieve a specified subset of a
large data set.  Pagination has two key concepts: limit and marker.

* *Limit* is the restriction on the maximum number of items for that type that
  can be returned.

* *Marker* is a reference to an object's ID and is in the list of paged
  results for a particular resource. Marker is the last item in the
  previous list returned.

To navigate the collection, you can set the ``limit`` and ``marker``
parameters in the URI. For example, ``?limit=10&marker=1234`` displays
the next 10 services after the service ``xyz`` in the paginated results.

If a marker beyond the end of a list is given, an empty list is returned.

For |service|, pagination applies only to operation listed in the following
table.

+---------+------------------------------+------------------------------------+
| Verb    | URI                          | Description                        |
+=========+==============================+====================================+
| **GET** | /v1.0/services               | Retrieves a list of all services.  |
+---------+------------------------------+------------------------------------+

For an example, see the :ref:`Retrieve all services <cdn-get-all-services>`
operation in the API reference.
