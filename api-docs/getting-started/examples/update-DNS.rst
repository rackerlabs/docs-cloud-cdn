Updating your Domain Name System 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Look for the ``access_url`` in the ``links[]`` section in the response
in :ref:`Retrieve a created service <gsg-list-service>` for the service that
you created. Make sure that the ``status`` is ``deployed``.

Go to your DNS (Domain Name System) provider, and create a CNAME record
from your domain (``www.mywebsite.com``) to the ``access_url`` returned
(``www.mywebsite.com.cdn1.raxcdn.com``).

It may take some time for your DNS change to propagate across the
internet. Once this has happened (based on the TTL you have set with
your DNS provider), you will be able to access your website via the CDN
Edge.

For more information, see :how-to:`Change DNS to enable Rackspace
CDN <change-dns-to-enable-rackspace-cdn>`.
