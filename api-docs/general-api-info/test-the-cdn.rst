.. _test-the-cdn:

============
Test the CDN
============

Because the Akamai server requires that you use a CNAME for the site to
access Akamai, we recommend that you use a test domain to validate
end-to-end CDN functionality with Akamai. For example, if the goal is to
enable ``www.example.com`` with Akamai, you might create a test hostname
such as ``test-www.example.com``, use the CNAME to access the same
partner endpoint as the ``www.example.com``, and create a copy of the
policy via the API so that it uses the same origin.