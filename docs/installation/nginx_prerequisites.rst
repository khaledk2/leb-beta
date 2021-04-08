.. _nginx-installation-label:


NGINX Prerequisite Resources
^^^^^^^^^^^^^^^^

NGINX will act as a reverse-proxy, and load balancer for Local EnteroBase. It will serve requests to the website to all the servers it is installed on. This page guides you through the creation of the resources required to install and configure NGINX. It is important to have these resources ready before continuing with the installation process, especially if you choose the "Automatic Installation" option.


NGINX Resource Directory Structure
================
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
================

The "nginx.conf" file is the configuration file used by NGINX. It defines a number of features of the web server, most importantly the URL or IP address it receives requests from and the URL or IP address it forwards them to. You can learn more about the nuances of this file on the NGINX "Beginner's Guide" available at: `<http://nginx.org/en/docs/beginners_guide.html>`_. In order to make the task of creating this file a bit easier, we have provided a webpage which takes some inputs and generates the "nginx.conf" file for you. This webpage is available at: `<http://35.246.24.128:5569/local_enterobase/nginx_config>`_.
