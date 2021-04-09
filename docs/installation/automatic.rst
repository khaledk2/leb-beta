Automatic Installation
----------------------

The automatic installation script can be downloaded using the following command:

``wget https://bitbucket.org/enterobase/local_enterobase/raw/104ce168cdae5a3ca1c2eccbb7334f4a3f0e60bb/installer/local_enterobase_installer.sh``

The script will automatically download, configure and run the Docker Image (Nginx), and Singularity image (PostgreSQL, Gunicorn and Local EnteroBase) and their dependencies packages.

During the installation the user will be asked to:

- Provide the filepath to the nginx.conf file downloaded when registering on Central EnteroBase
- Set a username and password for Local EnteroBase.

Then system components will be configured using the default parameters and should run without any issue.

NOTE: Fedora and CentOS 8 may require a system restart to complete the installation. The script will automatically reboot the server in this event, then restart the script automatically once signed back in. A restart occurs if:

- Docker is not installed and running for either distro 
- IF Fedora does not have the squashfs dependency already installed. 

The script has been tested on the following distros: Ubuntu 18.04, Ubuntu 20.04, Fedora 32, Fedora 33, CentOS 7, CentOS 8, Debian 9, and Debian 10.

The following figure shows the script workflow.

.. figure:: ../images/automatic_installation_script.png
   :width: 400
   :alt: Automatic installation workflow


