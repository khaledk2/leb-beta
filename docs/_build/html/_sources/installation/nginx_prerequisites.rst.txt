.. _nginx-prerequiites-label:

NGINX Prerequisite Resources
----------------------------

NGINX acts as a reverse-proxy and load balancer for Local EnteroBase. It will serve requests from the website to all the servers it is installed on. This page guides you through the creation of the resources required to install and configure NGINX. It is important to have these resources ready before continuing with the installation process, especially if you choose the "Automatic Installation" option.

NGINX Resource Directory Structure
==================================

  ::

    nginx
	|-- nginx.conf
	|-- certs
	| |-- cert.pem
	| |-- key.pem
	|-- logs
	  |-- local_enteroBase_access.log
	  |-- local_enteroBase_error.log

"nginx.conf"
============

The "nginx.conf" file is the configuration file used by NGINX. It defines a number of features of the web server, most importantly the URL or IP address it receives requests from and the URL or IP address it forwards them to. You can learn more about the nuances of this file on the NGINX "Beginner's Guide", available at: `<http://nginx.org/en/docs/beginners_guide.html>`_. In order to make the task of creating this file a bit easier, we have provided a webpage which takes some inputs and generates the "nginx.conf" file for you. This webpage is available at: `<http://35.246.24.128:5569/local_enterobase/nginx_config>`_.

.. figure:: ../images/nginx_config_page.png
   :width: 600
   :align: center
   :alt: Local EnteroBase Registration Form

   **Fig. 1 - NGINX Configuration Form**

The above figure shows the form that is used to generate the "nginx.conf" file. All fields in the form are mandatory. However, most come with default values which you should not modify. The values that are unique to your installation are the "Web Server URL/IP" and "Local Enterobase Server URL/IP" values. Below are some short descriptions of the required variables:

* **Web Server URL/IP**: URL or IP address for the NGINX server hosting your local EnteroBase instance. This value usually represents the IP address of your server, which you can find by running the command: ``curl https://ipinfo.io/ip``.
* HTTP Port: Port number for HTTP access to your Local EnteroBase instance. The default value is 80.
* HTTPS Port: Port number for HTTPS access to your Local EnteroBase instance. The default value is 443.
* Worker Connections: The maximum number of parallel connections that the Local EnteroBase instance can handle. The default value is 1024.
* Send File Max Chunk (k): The maximum amount of data that can be sent with a single send_file() call in kilobytes. The default value is 1024.
* Client Max Body Size (M): The maximum upload file size that the Local EnteroBase instance can handle in megabytes. The default value is 4000.
* Keep Alive Timeout (s): How long the TCP connection between the client and the server stays open after an HTTP transaction has been completed in seconds. The default value is 1500.
* **Local EnteroBase Server URL/IP**: The URL or IP address of the server facilitating the assembly of short-reads. This value will be the same as the "Web Server URL/IP" value if you have installed them on the same server.
* Local EnteroBase Server Port: The port of the server facilitating the assembly of short-reads. The default value is 8000.

For more information on these values please visit the NGINX docs, available at: `<http://nginx.org/en/docs/http/ngx_http_core_module.html>`_.

"certs"
=======

A valid SSL certification is required in order to run Local EnteroBase using https. For the beta test, a self-signed certificate is sufficient. A self-signed certificate can be generated using the OpenSSL tutorial at: `<https://linuxize.com/post/creating-a-self-signed-ssl-certificate>`_. Make sure that you rename the generated files to match the filenames shown in figure 1. Alternatively, you can use the certificates provided in the Docker container by default.

"logs"
======

The files in the "logs" folder maintain logs output by NGINX. These files can initially be created as empty files using the following commands:

.. code-block:: bash

	  $ mkdir logs
	  $ touch local_enteroBase_access.log
	  $ touch local_enteroBase_error.log
