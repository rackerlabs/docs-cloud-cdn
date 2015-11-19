.. _gsg-using-curl:

Sending API requests by using cURL
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

cURL is a command-line tool that is available in UNIX® system-based
environments and Apple Mac OS X® systems, and can be downloaded for
Microsoft Windows® to interact with the REST interfaces. For more
information about cURL, visit http://curl.haxx.se/.

cURL enables you to transmit and receive HTTP requests and responses
from the command line or from within a shell script. As a result, you
can work with the REST API directly without using one of the client
APIs.

The following cURL command-line options are used in this guide to run
the examples.

**Table:  cURL command-line options**

+--------------------------------------+--------------------------------------+
| Option                               | Description                          |
+======================================+======================================+
| ``-d``                               | Sends the specified data in a        |
|                                      | **POST** request to the HTTP server. |
|                                      | Use this option to send a JSON       |
|                                      | request body to the server.          |
+--------------------------------------+--------------------------------------+
| ``-H``                               | Specifies an extra HTTP header in    |
|                                      | the request. You can specify any     |
|                                      | number of extra headers. Precede     |
|                                      | each header with the ``-H`` option.  |
|                                      |                                      |
|                                      | Common headers in Rackspace API      |
|                                      | requests are as follows:             |
|                                      |                                      |
|                                      |                                      |
|                                      |                                      |
|                                      | -  ``Content-Type``. Required for    |
|                                      |    operations with a request body.   |
|                                      |                                      |
|                                      |    Specifies the format of the       |
|                                      |    request body. The syntax for the  |
|                                      |    ``Content-Type`` header is as     |
|                                      |    follows:                          |
|                                      |                                      |
|                                      |    .. code::                         |
|                                      |                                      |
|                                      |        Content-Type: application/for |
|                                      | mat                                  |
|                                      |                                      |
|                                      |    ``format`` is ``json``.           |
|                                      |                                      |
|                                      | -  ``X-Auth-Project-Id``. Optional.  |
|                                      |    Specifies the project ID, which   |
|                                      |    can be your account number or     |
|                                      |    another value.                    |
|                                      |                                      |
|                                      | -  ``Accept``. Optional.             |
|                                      |                                      |
|                                      |    Specifies the format of the       |
|                                      |    response body. The syntax for the |
|                                      |    ``Accept`` header is as follows:  |
|                                      |                                      |
|                                      |    .. code::                         |
|                                      |                                      |
|                                      |        Accept: application/format    |
|                                      |                                      |
|                                      |    ``format`` is ``json``. The       |
|                                      |    default is ``json``.              |
|                                      |                                      |
|                                      | -  ``X-Auth-Token``. Required.       |
|                                      |    Specifies the authentication      |
|                                      |    token.                            |
|                                      |                                      |
|                                      |                                      |
+--------------------------------------+--------------------------------------+
| ``-i``                               | Includes the HTTP header in the      |
|                                      | output.                              |
+--------------------------------------+--------------------------------------+
| ``-s``                               | Silent or quiet mode. Does not show  |
|                                      | progress or error messages. Makes    |
|                                      | cURL mute.                           |
|                                      |                                      |
|                                      | **Note:** \ If your cURL command is  |
|                                      | not generating any output, try       |
|                                      | replacing the ``-s`` option with     |
|                                      | ``-i``.                              |
+--------------------------------------+--------------------------------------+
| ``-T``                               | Transfers the specified local file   |
|                                      | to the remote URL.                   |
+--------------------------------------+--------------------------------------+
| ``-X``                               | Specifies the request method to use  |
|                                      | when communicating with the HTTP     |
|                                      | server. The specified request is     |
|                                      | used instead of the default method,  |
|                                      | which is **GET**.                    |
+--------------------------------------+--------------------------------------+



..  note:: 
    About json.tool
    For commands that return a response, you can append the following code
    to the command to call json.tool to pretty-print output:

.. code::  

    | python -m json.tool

To use json.tool, import the json module. For information about
json.tool, see `json — JSON encoder and
decoder <http://docs.python.org/2/library/json.html>`__.

If you do not want to pretty-print JSON output, omit this code.
