========
Unsplash
========

**Unsplash** is a recognized stock photography library 100% integrated with Odoo.

If your database is hosted on **Odoo Online** you can access Unsplash pictures without configuration.

If your database is hosted on **Odoo.sh or on-premise**, proceed as follows:

#. To **generate an Unsplash access key**, create or sign in to an Unsplash account on `Unsplash.com <https://unsplash.com/join>`_.

#. Access your `applications dashboard <https://unsplash.com/oauth/applications>`_, click
   :guilabel:`New Application`, select all checkboxes, and click :guilabel:`Accept terms`.

#. In the pop-up window that opens, enter your :guilabel:`Application Name`, starting with the
   prefix `Odoo:` (e.g., `Odoo: connection`), so Unsplash recognizes it as an Odoo instance. Then,
   add a :guilabel:`Description`, and click :guilabel:`Create application`.

#. On the application details page, scroll down to the :guilabel:`Keys` section and copy the
   :guilabel:`Access key`.

#. To **generate an Unsplash application ID**, go to your `applications dashboard <https://unsplash.com/oauth/applications>`_
   and click on the application you just created.

#. Copy the application ID number visible at the end of the page's URL:

   .. image:: unsplash/app-id-url.png
     :alt: Identify your app idd url.

7. In Odoo, go to :menuselection:`General Settings`, and enter your Unsplash :guilabel:`Access Key`
   and :guilabel:`Application ID`.

   .. image:: unsplash/add-your-keys.png
     :alt: Add your access key and application ID.

.. tip::
   You can also enter your keys when adding images via the media dialog:

   .. image:: unsplash/media-selector.png
      :alt: Paste your access key and application ID in the media selector.

.. warning::
   **As a non-Odoo Online user**, you are not able to register for a production Unsplash key and
   you are limited to your test key that has a restriction of 50 Unsplash requests per hour.
