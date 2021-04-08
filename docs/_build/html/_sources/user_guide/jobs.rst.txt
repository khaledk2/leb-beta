Viewing Jobs
------------

This webpage allows you to view current jobs

All the current user's jobs are listed here with some metadata (which can be Completed, Failed, UPLOADED, Upload Failed, Received, Processing).

Refresh the page to update - callbacks to be implemented in the future.
No sorting on the page currently - can be implemented in the future.

When job is finished and successful, can upload to warwick EB if you want and download

Upload - submits the fasta, fastq and metadata of the results
Download - downloads the fasta, fastq and metadata to local storage (default download directory of the web browser)







DEFINE JOBS
* This option allows the user to check his assembly jobs status

.. figure:: ../images/job_status.png
   :align: center
   :alt: Job status

   **Fig. 1 - Jobs Status dialog**

Notes
^^^^^

* We should modify this table to include batch jobs rather than single strain job
* A link for each batch should be provided so the user can check the status of each strain
* The previous link will open other dialog which allow the user to:
    * check the status of the assembly,
    * alert metadata,
    * provide new read files in case of the assembly job failed due to read files
    * submit the strains metadata along with read files to Warwick EnteroBase.
* The previous functions are not implemented yet
