Automatic Installation
----------------------

The automatic installation script can be downloaded using the following command:

``wget https://bitbucket.org/enterobase/local_enterobase/raw/104ce168cdae5a3ca1c2eccbb7334f4a3f0e60bb/installer/local_enterobase_installer.sh``

The script will automatically download, configure and run the Docker Image (NGINX), and Singularity image (PostgreSQL, Gunicorn and Local EnteroBase) and their dependencies packages.

During the installation the user will be asked to:

- Provide the filepath to the nginx.conf file downloaded when registering on Central EnteroBase
- Set a username and password for Local EnteroBase.

Then system components will be configured using the default parameters and should run without any issue.

**Important**

The automatic installation does not currently include downloading and configuring usearch and MiniKraken2 with your Local EnteroBase. For the beta test, we do not expect this to be an issue as they are not used in the assemblies performed by the current version of Local EnteroBase.

However, we would like your version to match that for a manual installation if possible. Please perform the following steps to accomplish this. If you have any problems or questions, please contact us.

1. Download usearch and the MiniKraken2 database for EToKi to function correctly.

  * usearch software - You may need to submit a free licence request, where you should receive an email which contains a download link.
  * MiniKraken2 database - You can download it from their website: https://ccb.jhu.edu/software/kraken2/index.shtml?t=downloads
  * A suggested command is "wget" to download the software.

  * ** For the beta test ** you can use the following commands to download usearch:

    ::

      cd $HOME/local_enterobase_home/EToKi_externals
      wget https://www.drive5.com/downloads/usearch11.0.667_i86linux32.gz
      chmod 755 usearch11.0.667_i86linux32.gz
      gzip -d usearch11.0.667_i86linux32.gz

  * ** For the beta test ** you can use the following commands to download MiniKraken2:

    ::

      wget https://github.com/DerrickWood/kraken2/archive/v2.0.8-beta.tar.gz
      tar xf v2.0.8-beta.tar.gz
      mv kraken2-2.0.8-beta minikraken2

2. Save usearch and MiniKraken2 to the same folder e.g. $HOME/local_enterobase_home/EToKi_externals (default).

3. Configure EToKi.

  * If the name EToKi_externals has been changed, replace its occurrence in the following command by the new name.
  * If the storage location for configure.ini has been changed, replace its path in the following command by its location.
  * If the Kraken database has a different directory name other than the default "minikraken2" upon installation, you can leave it unchanged or change it to this/another appropriate name and replace its occurrence in the following command accordingly.
  * If the default installation directory was changed previously for EGP.sif and/or EToki_Externals, replace them in the following command with the correct installation directory.
  * If the pulled image name "EGP.sif" was changed previously, replace it in the following command with your chosen name.

    ::

      singularity run -B $HOME/local_enterobase_home/EToKi/configure.ini:/code/EToKi/modules/configure.ini -B $HOME/local_enterobase_home/EToKi_externals:/code/EToKi/local_externals --app run_etoki $HOME/local_enterobase_home/local_enterobase/EGP.sif configure --usearch /code/EToKi/local_externals/usearch11.0.667_i86linux32 --link_krakenDB /code/EToKi/local_externals/minikraken2/

    * Here is a brief explanation on what some flags being used mean:

      * -B: Used to bind a directory on the local system to one inside the container to allow data to be read and written simultaneously since Singularity images are read-only otherwise.

        * Here, the EToKi configuration file and the local externals folder storing usearch and minikraken2 are bound to enable updating the configuration paths and internally access usearch and minkraken2 respectively.

      * --app: Runs a specific script defined by the image.

        * Here, the 'run_etoki' script is called to pass in commands leading to the execution of EToKi functions, in this case it is cp_configure.

      * --usearch: Used to pass the locally downloaded usearch file to the container.

        * As /code/EToKi/local_externals is bound by the local externals folder, the internal container path that usearch is saved to can be used.

      * --link_krakenDB: Used to pass the locally downloaded Kraken database to the container.

        * As /code/EToKi/local_externals is bound by the local externals folder, the internal container path that the database directory is saved to can be used.

**Notes**

* Automatic installation has only been tested on newly created VMs that have not previously installed Singularity, Docker, PostgreSQL or Redis on them. As a result, you may experience issues during installation if your system has previously installed any of the previous softwares. Please contact us if you experience any issues.

* Fedora and CentOS 8 may require a system restart to complete the installation. The script will automatically reboot the server in this event, then restart the script automatically once signed back in. A restart occurs if:

  * Docker is not installed and running for either distribution.
  * Fedora does not have the squashfs dependency already installed.

* The script has been tested on the following distributions: Ubuntu 18.04, Ubuntu 20.04, Fedora 32, Fedora 33, CentOS 7, CentOS 8, Debian 9, and Debian 10.

The following figure shows the script workflow.

.. figure:: ../images/automatic_installation_script.png
   :width: 400
   :alt: Automatic installation workflow
