Upload Test
-----------------

The purpose of the upload test is to ensure that your Local EnteroBase has been correctly installed and configured.
The test consists of downloading and assembling 2 test short-read files and verifying their results. It will also
download and upload 100 files to check the connection speed to Central EnteroBase.

Prerequisites
==============

* Test token on hand, it was emailed by Central EnteroBase when registering your Local EnteroBase. You can also find it here: http://35.197.247.144:5569/local_enterobase/display_test_token
* Celery task scheduler and worker processes to be initialised. These are the background processes that will assemble the test short-read files and upload their results. They can be initialised using the Singularity container with the following commands:

  ::

    singularity run --app celery_beat $HOME/local_enterobase_home/local_enterobase/EGP.sif

  ::

    singularity run --app celery_worker $HOME/local_enterobase_home/local_enterobase/EGP.sif

  * Please modify the default path/name of the container if you have changed this during installation.

Running the Test
=================

Enter token, click "start test" and the test starts - fully automated feel free to monitor

Next step is where 100 test short read files (used for performing a download and upload speed test) are downloaded to perform assemblies on - estimated time 2 minutes depending on your geographical location

Next step is where 1 downloaded short read file is prepared and assembled. - estimated time 15 minutes
Resulting fastq file is uploaded to central enterobase where it is verified against a known result which sees if the assembly is correct

Also, the md5sum is extracted from each short read file and reuploaded along with the respective file back to central enterobase which verifies this checksum against the known checksum to ensure that files are not being changed during upload

On completion, a summary is displayed of the times taken to reupload each short read file, as well as the total and average times to reupload all files.

If the test fails at any step, this will be displayed with an appropriate error message and a "retry" button to reattempt the upload test.

TO BE UPDATED

.. figure:: ../images/incomplete_upload_test.png
   :align: center
   :alt: Incomplete Upload Test Form

   **Fig. 1 - Incomplete Upload Test Form**

TO BE UPDATED

.. figure:: ../images/incomplete_upload_test.png
  :align: center
  :alt: Completed Upload Test Form

  **Fig. 2 - Completed Upload Test Form**
