System Configuration
--------------------

* The local administrator needs to:

  * Link an email account to act as the communication point for local enterobase. This includes the server (MAIL_SERVER), port (MAIL_PORT), username (MAIL_USERNAME), and password (MAIL_PASSWORD).

    * Additional settings are available for advanced configuration, this includes tls (MAIL_USE_TLS), ssl (MAIL_USE_SSL)
  * Configure the database server which includes uri( DATABSE SERVER URI), port (DATABASE PORT), username (DATABSE USER) and password (DATABSE PASSSWORD)
  * Register your installation with Warwick EnteroBase
  * Test uploading files to Warwick EnteroBase

.. figure:: ../images/configuration.png
   :alt: local Configuration  Form

   **Fig 1 Configuration Form**



* In case of using  "local_enterobase_installer.sh" bash script to install the system, then the script will configure the system with the default setting which should be fine for most of cases. 

* The local installation configuration file is saved in the user home folder ($HOME/.local_configuration_file.yml), you can edit it directly using any text editor (e.g. vim) or it can be alerted using "/update_system_configuration"  link from the web interface (it will be the default main web page if the database is not configured or not configured correctly in case of manual installation).

* After any system configuration change, you need to restart the application using the following commands:

  ::

    singularity instance  stop local_enterobase
    singularity instance start local_enterobase.sif local_enterobase

* If the local administrator has installed it using the provided bash file, it will create a bash script “restart_local_enterobase.sh” which can be used to restart the singularity container useing the following command:

  ::

    ./restart_local_enterobase.sh


Notes
=====

* It is needed to synchronize the local installation name with the registration form.
* In case of using the automatic installation, it is needed to get the server URL from the user input during the installation.

