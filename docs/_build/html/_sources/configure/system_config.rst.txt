System Configuration
---------------------

On entry to the webpage, the Local EnteroBase administrator is required to sign in with the system credentials set during
the installation phase. Then, the following webpages should display the following configuration steps that need to be completed:

General Configuration
=======================

* A name for your Local EnteroBase, to be displayed when using the website, must be inputted. It does not need to match the name used to register your Local EnteroBase.
* An image to be displayed as a logo in the website, that also identifies it in your browser's address bar, must be chosen. We provide functionalities for cropping and resizing if required.
* If required, a filepath to an accessible directory that stores data produced by Local EnteroBase, such as short-read assembly results, can be selected. A default file path is automatically
  filled in on the form that is created if currently non-existent.

  .. figure:: ../images/general_config.png
     :align: center
     :class: with-border
     :alt: General Configuration Form

     **Fig 1. General Configuration Form**

Database Selection and Configuration
======================================



Mail Server
===============

Note: The mail server functionality is currently unavailable for the beta test, feel free to skip this section.


Celery Messaging
=================

DESCRIBE CELERY

The entire form is filled by default that should correctly configure Celery with your Local EnteroBase. **please do not change these values unless you are an expert**.

.. figure:: ../images/celery_messaging.png
   :align: center
   :class: with-border
   :alt: Celery Messaging Configuration Form*

   **Fig 2. Celery Messaging Configuration Form**


**TO REMOVE**
* The local administrator needs to:

  * Link an email account to act as the communication point for local enterobase. This includes the server (MAIL_SERVER), port (MAIL_PORT), username (MAIL_USERNAME), and password (MAIL_PASSWORD).

    * Additional settings are available for advanced configuration, this includes tls (MAIL_USE_TLS), ssl (MAIL_USE_SSL)
  * Configure the database server which includes uri( DATABSE SERVER URI), port (DATABASE PORT), username (DATABSE USER) and password (DATABSE PASSSWORD)
  * Register your installation with Warwick EnteroBase
  * Test uploading files to Warwick EnteroBase



* In case of using "local_enterobase_installer.sh" bash script to install the system, then the script will configure the system with the default setting which should be fine for most of cases.

* The local installation configuration file is saved in the user home folder ($HOME/.local_configuration_file.yml), you can edit it directly using any text editor (e.g. vim) or it can be alerted using "/update_system_configuration"  link from the web interface (it will be the default main web page if the database is not configured or not configured correctly in case of manual installation).

* After any system configuration change, you need to restart the application using the following commands:

  ::

    singularity instance  stop local_enterobase
    singularity instance start local_enterobase.sif local_enterobase

* If the local administrator has installed it using the provided bash file, it will create a bash script “restart_local_enterobase.sh” which can be used to restart the singularity container useing the following command:

  ::

    ./restart_local_enterobase.sh

* In case of using the automatic installation, it is needed to get the server URL from the user input during the installation.
