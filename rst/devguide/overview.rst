========
Overview
========

A content delivery network (CDN) is designed to improve the performance
of publicly distributed assets.  Assets can be anything from website
content, to web application components, to media like videos, ads, and
interactive experiences.  CDNs decrease the load time of these assets by
caching them on edge nodes, which are also called edge servers or point
of presence (PoP) servers.  Edge nodes are distributed around the globe,
and they cache content and serve it directly to customers, thus reducing
transit time to a customer's location. 

Rackspace CDN gives you the power to accelerate content on any public
resource at Rackspace. It provides a simple API and Control Panel
experience for you to manage your CDN-enabled domains and the origins
and assets associated with those domains. 

The Rackspace CDN architecture includes the following components:

-  A RESTful API

-  The ability to cache publicly accessible resources hosted on a Cloud
   Server instance, or a public Cloud Files container

-  A single global endpoint to access the API

-  Use of the Akamai Technologies content delivery network, which is one
   of the world's largest distributed computing platforms

In addition to this guide, you will find the *Rackspace CDN Getting
Started Guide*, which explains how to start using the API, at
http://docs.rackspace.com/.

Intended audience
-----------------

This document is intended for software developers who want to develop
applications that use the Rackspace CDN API. You should be familiar with
the following technologies:

-  RESTful web services

-  HTTP/1.1 conventions

-  JSON data serialization formats


API contract changes
--------------------

Rackspace notifies customers in release notes when and if the contract changes.

Pricing and service level
-------------------------

Your use of Rackspace CDN is billed according to the pricing schedule on the Rackspace CDN page at `www.rackspace.com <http://www.rackspace.com/cloud/cdn-content-delivery-network>`_.

The Service Level Agreement (SLA) for Rackspace CDN is available at `Rackspace CDN SLA <http://www.rackspace.com/information/legal/service-level-guarantee-rackspace-cdn>`_.