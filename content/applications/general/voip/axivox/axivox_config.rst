=====================================
Use VoIP services in Odoo with Axivox
=====================================

Introduction
============

Odoo VoIP (Voice over Internet Protocol) can be set up to work together with `Axivox
<https://www.axivox.com/>`_. In that case, an :doc:`Asterisk server <../asterisk>` is not necessary as
the infrastructure is hosted and managed by Axivox.

To use this service, `contact Axivox <https://www.axivox.com/contact/>`_ to open an account. Before
doing so, verify that Axivox covers your area and the areas you wish to call.

Configuration
=============

To configure Axivox on Odoo, first, go to the :menuselection:`Apps` app and search for the `VoIP`
module. Then install the *VoIP Module*.

Next, go to :menuselection:`Settings --> General Settings --> Integrations`, and fill out the
:guilabel:`Asterisk (VoIP)` field:

- :guilabel:`PBX Server IP` or :guilabel:`OnSIP Domain`: Set the domain created by Axivox for your
   account (e.g., `yourcompany.axivox.com`)
- :guilabel:`WebSocket`: Type in `wss://pabx.axivox.com:3443`
- :guilabel:`VoIP Environment`: Set as :guilabel:`Production`

.. image:: axivox_config/voip-configuration.png
   :align: center
   :alt: Integration of Axivox as VoIP provider in an Odoo database.

.. tip::
   Access the domain on the Axivox administrative panel. Navigate to `https://manage.axivox.com/
   <https://manage.axivox.com/>`_. After logging into the portal go to :menuselection:`Users -->
   Edit (next to any user) --> SIP Identifiers tab --> Domain`.

Configure the VOIP user in the Odoo's user
------------------------------------------

Next, the user will be configured on Odoo. This process must take place for every Axivox/Odoo user
using VoIP. To start, go to :menuselection:`Settings --> Users & Companies --> Users`, then open the
user's form to configure :abbr:`VoIP (Voice over Internet Protocol)`. Under the
:guilabel:`Preferences` tab, fill out the section :guilabel:`PBX Configuration`:

- :guilabel:`VoIP (SIP) Login/Username` / :guilabel:`Browser's Extension Number` = (Axivox)
  :guilabel:`SIP username`
- :guilabel:`OnSIP Auth Username` = (Axivox) :guilabel:`SIP username`
- :guilabel:`SIP Password / VoIP Secret` = (Axivox) :guilabel:`SIP Password`

.. image:: axivox_config/odoo-user.png
   :align: center
   :alt: Integration of Axivox user in the Odoo user preference.

.. tip::
   Access the domain on the Axivox administrative panel. Navigate to `https://manage.axivox.com/
   <https://manage.axivox.com/>`_. After logging into the portal go to :menuselection:`Users -->
   Edit (next to the user) --> SIP Identifiers tab --> SIP username / SIP password`.

   .. image:: axivox_config/manager-sip.png
      :align: center
      :alt: SIP credentials in the Axivox manager.
