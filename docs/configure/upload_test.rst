Upload Test
-----------------

The purpose of the upload test is to ensure that your Local EnteroBase has been correctly installed and configured.
The test consists of downloading and assembling 2 test short-read files and verifying their results. It will also
download and upload 100 files to check the connection speed to Central EnteroBase.

Prerequisites
==============

* Test token emailed by Central EnteroBase when registering your Local EnteroBase. You can also find it
`here <http://35.197.247.144:5569/local_enterobase/display_test_token>`_

* Celery task scheduler and worker processes to be initialised. These are the background processes that will
asemble the test short-read files and upload their results. They can be initialised using the Singularity container
with the following commands:

  ::

    singularity run --app celery_beat $HOME/local_enterobase_home/local_enterobase/EGP.sif

  ::

    singularity run --app celery_worker $HOME/local_enterobase_home/local_enterobase/EGP.sif

  * Please modify the default path/name of the container if you have changed this during installation.

TO BE UPDATED
.. figure:: ../images/incomplete_upload_test.png
   :align: center
   :alt: Incomplete Upload Test Form

   **Fig 1. Incomplete Upload Test Form**

 TO BE UPDATED
 .. figure:: ../images/incomplete_upload_test.png
    :align: center
    :alt: Incomplete Upload Test Form

    **Fig 2. Completed Upload Test Form**
