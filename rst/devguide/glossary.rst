========
Glossary
========

Caching rule
    A caching rule provides you with fine-grained control over the
    time-to-live (TTL) of an object. When the TTL expires for an object,
    the edge node pulls the object from the origin again.

Content delivery network
    A content delivery network (CDN) is a system of multiple computers
    that contains copies of data stored at various network nodes. A CDN
    is designed to improve performance of publicly distributed
    assets. Assets can be anything from website content, to web
    application components, to media such as videos, ads, and
    interactive experiences.  CDNs decrease the load time of these
    assets by caching them on edge nodes, also called edge servers or
    point of presence (PoPs) servers.  Edge nodes are distributed around
    the globe, so requests travel to a local location to get assets
    rather than to and from a data center based far from the end user. 

Domain
    A domain represents the domain name through which visitors retrieve
    content. The underlying site might be served through a CDN. A
    service can have multiple domains. The CDN provider provides users
    with a Canonical Name (CName) to specify for their domain name as an
    alias.

Edge node
    CDN providers have many points of presence (PoP) servers around the
    world. These servers are known as edge nodes. These edge nodes cache
    the content and serve it directly to customers, thus reducing
    transit time to a customer's location.

Edge server
    An edge server is the same as an edge node.

Flavor
    A flavor is a mapping configuration to a CDN provider that enables
    you to decide which CDN features that you want your service to use.
    In the request and response examples for Rackspace CDN, the flavor
    is referred to with the ``flavor_id`` parameter. For this release of
    Rackspace CDN, the ``flavor_id`` value is ``cdn``. The ``cdn``
    flavor enables your service content to be delivered across the
    network using the Rackspace CDN partner, Akamai. In the future,
    Rackspace might offer other flavors.

JSON Pointer
    A JSON Pointer defines a syntax for identifying a specific value
    within a JSON document. A restricted JSON pointer is a Unicode
    string containing a sequence of exactly one reference token,
    prefixed by a '/' (%x2F) character. Each reference token is a
    sequence of unreserved and/or percent-encoded characters.

Origin
    An origin is an address (IP or domain) from which the CDN provider
    pulls content. A service can have multiple origins.

Point of presence
    A point of presence (PoP) is the point at which two or more
    different networks or communication devices build a connection with
    each other. PoP mainly refers to an access point, location, or
    facility that connects to and helps other devices establish a
    connection with the Internet.

Purge
    Purging removes content from the edge nodes thus invalidating the
    content so that the content can be refreshed from your origin
    servers.

Restriction
    A restriction enables you to define rules about who can or cannot
    access content from the cache. Examples of a restriction are
    allowing requests only from certain domains, geographies, or IP
    addresses.

Service
    A service represents an application that has its content cached to
    the edge nodes.

Status
    The status indicates the current state of a service. The time it
    takes for a service configuration to be distributed to a CDN
    provider cache can vary.

