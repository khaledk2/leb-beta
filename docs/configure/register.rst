-------------------
Local Enterobase Registration
-------------------

==============
Purpose
==============
In order to maintain quality control in the distribution of Enterobase to all of the institutions that wish to maintain one, each Local Enterobase instance must be approved by Central Enterobase. This approval process begins with registering your Local Enterobase instance. Once you have performed this registration, you will receive a test token which you need to save for later use (NOTE: this is used during the configuration once you are able to run assemblies, so please keep it safe). This token is used to test your Local Enterobase instance and feeds back the results to Central Enterobase before your instance is approved. The Warwick Enterobase team will review your request once the test results have been received. If at any point you forget where you saved your test token, you can find it at: `<http://35.246.24.128:5569/local_enterobase/display_test_token>`_. If this link returns an error, it either means you haven't submitted a Local Enterobase request or your Local Enterobase request has already been approved.

==============
Prerequisites
==============
* You must have an account with the beta test Central Enterobase, since this is a different server to the regular Central Enterobase (`<https://enterobase.warwick.ac.uk>`_), you must register a new account at: `<http://35.246.24.128:5569/auth/register>`_. (NOTE: this account will only exist for the duration of the beta test)
* You must be logged into the account that you would like the administrator of the Local Enterobase instance. This account will be regarded by the Warwick Enterobase team as the point of contact for the Local Enterobase instance. This login can be performed at: `<http://35.246.24.128:5569/auth/login>`_.
* You must know the URL or IP endpoint that the Local Enterobase instance will be exposed to.

==============
Registration Page
==============
Once the prerequisites have been completed you can now fill out the form at: `<http://35.246.24.128:5569/local_enterobase/register>`_.

.. figure:: ../images/local_enterobase_registration_screenshot.png
   :width: 300
   :alt: Local Enterobase registration page
   
   **Fig 1 Local Enterobase registration page**

The above image is a screenshot of the Local Enterobase registration page (NOTE: you must be logged in to view it). All fields within the form are required and can be described as follows:

1. **Local Enterobase Name**: The name you would like the Local Enterobase instance to be referred to as, for example: "Warick Beta Test Enterobase".
2. **External URL**: The URL or IP address that a user can connect to your Local Enterobase with (NOTE: you must have ownership of this URL), for example: "`<https://enterobase.warwick.ac.uk>`_".
3. **Description & Justification**: This is your opportunity to tell us why you would like to maintain your own Local Enterobase instance. You may want to include details about the institution that will be using it, how it will be used, and anything else you would like the Warwick Enterobase team to know.
4. **Central Enterobase Username of Local Enterobase Admin**: This field is just a double check to see if you want the currently logged in user to be the administrator (contact) of the Local Enterobase instance. If you input anything other than the currently logged in user's Central Enterobase username, you will be informed that you need to be logged in as that user (NOTE: you can only be the administrator for one Local Enterobase instance).
