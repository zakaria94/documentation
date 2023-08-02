========================
Managing users in Axivox
========================

Managing Axivox :abbr:`VoIP (Voice over Internet Protocol)` users is an important part of setting up
:abbr:`VoIP (Voice over Internet Protocol)` in an Odoo database. Each Axivox user has a unique name,
phone number and/or extension, and a voicemail, so they can be reached in a variety of convenient
ways. Axivox users are organized in a simple and straightforward way in the Axivox console so that
an administrator can manage users quickly and easily.

.. note::
   This documentation will cover how to configure everything through a provider called Axivox, and
   depending on the chosen VoIP provider the processes to manage users may be different.

Overview
========

Begin at the Axivox management console by navigating to `https://manage.axivox.com
<https://manage.axivox.com>`_. Log in with the appropriate administrator credentials.

.. note::
   Actions in the Axivox management console need to be double-saved in order for the changes to take
   effect. To save any changes click :guilabel:`Save` in the individualized changes screen and then
   to implement the changes click the :guilabel:`Apply Changes` button in the upper right corner of
   the console.

.. _axivox/incoming_number:

Incoming numbers
----------------

Incoming numbers are all the numbers a company is paying to use to receive calls to. Click on
 :menuselection:`Incoming numbers` in the left menu on the Axivox management console. Listed are all
 the incoming numbers along with their :guilabel:`Destination` and SMS information. The
 :guilabel:`Destination` determines the action that will be taken or the path that the caller will
 follow when dialing said numbers.

 To edit the :guilabel:`Destination` click on the :guilabel:`Edit` button on the far right of the
 incoming number line. On the *edit page* the :guilabel:`Destination type for voice call` can be
 changed.

The options are as follows:

- :guilabel:`Not configured`
- :guilabel:`Extension`
- :guilabel:`Dial plan`
- :guilabel:`Voicemail`
- :guilabel:`Hang up`
- :guilabel:`Conference`

Depending on the section made in the first dropdown (:guilabel:`Destination type for voice call`) a
second dropdown will be populated with further configuration options. Additionally there may be more
fields revealed based on the first selection.

Be sure to :guilabel:`Save` the changes and :guilabel:`Apply changes` to implement any changes.

New users
=========

Every employee that will be using :abbr:`VoIP (Voice over Internet Protocol)` at the company will
need a Axivox *user* associated with them. To view existing *users* in the Axivox management console
click on :guilabel:`Users` in the menu on the left of the console. Every *user* has a
:guilabel:`Number`, :guilabel:`Name`, option for a :guilabel:`Voicemail`, and an
:guilabel:`Outgoing number` specified.

To create a new user in the Axivox console, click on :guilabel:`Add a user`. The following tabs are
available for configuring the new user:

- :guilabel:`General`: Basics, including the extension of the user are set.
- :guilabel:`Forwardings`: Internal forwards on nno answer or busy signals.
- :guilabel:`Follow me`: External forward configuration.
- :guilabel:`Keys`: Set hot-keys within the :abbr:`VoIP (Voice over Internet Protocol)` system.
- :guilabel:`SIP Identifiers`: :abbr:`SIP (Session Initiation Protocol)` username and password for
  external configuration.
- :guilabel:`Permissions`: Set access rights for users in the Axivox management console.

General tab
-----------

Under the :guilabel:`Extension` field, input an extension that is unique to the user. This will be
the number that internal users will dial in order to reach a specific employee. In the
:guilabel:`Name` field input the employee name.

Following inputting the :guilabel:`Name` add fill out the :guilabel:`Email address of the user`
field. A valid email address for the employee should be added in here, where the user receives
business emails.

Next, is the :guilabel:`GSM number`, this field is for an alternative number that the user can be
reached at. Be sure to included the country code.

.. note::
   A country code is a locator code that will allow for access to the desired country's phone
   system. The country code is dialed first prior to the target number. Each country in the world
   has its own specific country code. For a list of comprehensive country codes we recommend
   visiting `https://countrycode.org <https://countrycode.org>`_.

.. image:: manage_users/general-tab.png
   :align: center
   :alt: General tab layout in the Axivox management console.

Under the :guilabel:`GSM number` field is the option to set a :guilabel:`Voicemail`. Either select
:guilabel:`Yes` or :guilabel:`No` from the dropdown. Next, there is a field for
:guilabel:`Directory` in which the administrator has the option to leave it blank by making no
changes or selecting :guilabel:`Default` from the dropdown. The :guilabel:`Directory` is used in the
*digital receptionist* feature of a dial-plan.

There are two separate options with selection boxes on the bottom of the :menuselection:`General
tab`. The first option is :guilabel:`This user can receive multiple calls at the same time`, by
selecting this option users will be able to receive calls when on another call. The second option
(:guilabel:`This user must log-in to call`) is to make it mandatory for the user to log in.

.. note::
   If a company uses physical VoIP phones on desks and wanted their employees to be able to log in
   from any phone or desk in the office, then make the selection for :guilabel:`This user must
   log-in to call`.

Remember to :guilabel:`Save` any changes made and :guilabel:`Apply changes`.

.. _axivox/forwardings_tab:

Forwardings tab
---------------

Under the :menuselection:`Forwardings tab` a company can decide what happens if someone calls a
users and the call isn't answered. For example, under :guilabel:`Forwarding on no answer`, when the
button for :guilabel:`Add a destination` is selected the option to add a specific user or phone
number is revealed. After entering the :guilabel:`Destination` a specific *time frame* can be made by
sliding the :guilabel:`seconds bar` to the desired ring time. Additional :guilabel:`Destinations`
can be added on with different ring times.

.. note::
   Ring times can be staggered so that the call is forwarded to another user after the first user
   doesn't pick up the call. The option to :guilabel:`Send to voicemail as a last resort` is
   available to the administrator should the :guilabel:`Destinations` not pick up.

Moving on, under the :menuselection:`Forwarding on busy` an administrator can :guilabel:`Add a
destination` by setting the same parameters a :guilabel:`Destination` (user) and *time frame* should
the original user's :abbr:`VoIP (Voice over Internet Protocol)` extension or incoming number be
busy.

.. image:: manage_users/forwardings-tab.png
   :align: center
   :alt: Manage forwarding calls to different users or phone numbers in the Forwardings tab.

Remember to :guilabel:`Save` any changes made and :guilabel:`Apply changes`.

Follow Me tab
-------------

When the :guilabel:`Follow Me` option is selected on the ::menuselection:`Follow Me` tab no
:menuselection:`Forwardings` can be made. When the :guilabel:`Follow Me` option is selected the
:guilabel:`Add a destination` button can be selected to add users or a destination phone number on
to the original user's account, so that these added numbers ring when a call is
received. After entering the :guilabel:`Destination` a specific *time frame* can be made by sliding
the :guilabel:`seconds bar` to the desired ring time. Additional :guilabel:`Destinations` can be
added on with different ring times.

.. note::
   The original user's :abbr:`VoIP (Voice over Internet Protocol)` number will not ring with this
   option selected. Ring times can also be staggered so that the call is forwarded to another user
   after the first user doesn't pick up the call.

.. image:: manage_users/follow-me-tab.png
   :align: center
   :alt: Ring destinations like different users or phone numbers from the Follow Me tab.

.. important::
   The Odoo mobile app or another :abbr:`SIP (Session Initiation Protocol)` mobile client, allows
   for simultaneous ringing of the user's extension or incoming number. For more information visit
   the :doc:`VoIP Mobile Integrations <../devices_integrations>` documentation.

Remember to :guilabel:`Save` any changes made and :guilabel:`Apply changes`.

Keys tab
--------

Under the :menuselection:`Keys tab` speed dial actions for the user can be configured. Some more
advanced options are available. The following options are available to set to numerical values
`1-20`.

The following actions can be set on each number:

- :guilabel:`Not configured`: The default action which is nothing.
- :guilabel:`Busy lamp fields (BLF)`: This action will show the status of other users' phones
  connected to the Axivox phone system. This is primarily used on a desk-phone.
- :guilabel:`Quick Call`: This action will allow for a speed-dial of an external number.
- :guilabel:`Line`: This action will allow the user to call another user.
- :guilabel:`Switch`: This action will allow the user to switch between calls from a desk-phone.
- :guilabel:`Pickup`: This action will allow the user to pick up an incoming call from a desk-phone.

Make the necessary changes within the :menuselection:`Keys tab`. Remember to :guilabel:`Save` any
changes made and :guilabel:`Apply changes`.

.. important::
    Many of the above options have secondary options available to link a user or external phone
    number and must be filled out in conjunction with the initial action.

.. note::
   The :guilabel:`Number of keys` can be changed simply by entering in the numerical value in the
   :guilabel:`Number of keys` field at the top of the :menuselection:`Keys tab` page.

SIP Identifiers tab
-------------------

SIP stands for Session Initiation Protocol telephony, it allows one to make and receive calls
through an internet connection. The :menuselection:`SIP Identifiers tab` contains credentials needed
to configure Axivox users in Odoo and/or a :abbr:`SIP (Session Initiation Protocol)` mobile client.

.. seealso::
   Some more great documentation can be utilized here: :doc:`Use VoIP services in Odoo with Axivox
   <axivox_config>` | :doc:`Axivox Mobile Integrations <../devices_integrations>`.

The :abbr:`SIP (Session Initiation Protocol)` username is the user's :guilabel:`Extension` in the
:menuselection:`General tab`. The :guilabel:`Domain` is assigned to the company by the Axivox
representative. The next value after :guilabel:`Domain` is the :guilabel:`SIP Password`, this value
is unique for every Axivox user. This value is used to sign-in to Axivox on Odoo and for any mobile
:abbr:`SIP (Session Initiation Protocol)` clients.

.. image:: manage_users/sip-identifiers-tab.png
   :align: center
   :alt: Important credentials used for external configurations of Axivox VoIP.

The last field/value that is listed on the :menuselection:`SIP Identifiers tab` is the
:guilabel:`Address of the proxy server`. This value is generally always: `pabx.axivox.com`, but is
subject to change by Axivox so be sure to check the :menuselection:`SIP Identifiers tab` for the
most accurate value.

Remember to :guilabel:`Save` any changes made and :guilabel:`Apply changes`.

Permissions tab
---------------

The following permissions can be granted to Axivox users for portal access:

- User portal access
- User management
- Administrator access
- Phone management
- User group management
- Phone number management
- Dial plan management
- Pickup group management
- Switch management
- Conference management
- Queue management
- Voicemail management
- Audio messages management
- Music on hold management
- Directory management
- Call list
- Connected user list
- Global settings
- Apply changes button
- Invoice download
- Invoice details
- Blacklist management
- Conference participant management

To access credentials for the Axivox user portal navigate to the top of the
:menuselection:`Permissions tab`. Copy the :guilabel:`Username` and enter a :guilabel:`Password` for
the individual user. There is a minimum of 8 characters for a user password.

.. note::
   These are the same permissions granted to the Axivox administrator that are listed in the left
   menu in the Axivox management console. Should a selection state :guilabel:`No` or :guilabel:`No
   access` then the menu option will not populate for the user.

Remember to :guilabel:`Save` any changes made and :guilabel:`Apply changes`.

Upon finishing setting up a new user, an :ref:`axivox/incoming_number` can be linked.

.. _axivox/user_groups:

User groups
===========

A user group is a grouping of Axivox users that can be linked to a *Queue* for call center
functionality.

To begin using user groups navigate to `https://manage.axivox.com <https://manage.axivox.com>`_. Log
in with the appropriate administrator credentials. On the left menu of the Axivox administrative
panel, click into :guilabel:`User Groups`.

To add a User Group, click :guilabel:`Add a group`. Name the group, by entering text into the
:guilabel:`Name` field. Add a member to the group by typing the first few letters of the user's name
into the :guilabel:`Members` field. The user will populate in a dropdown below the field, click on
the user and they will be added onto the user group. Repeat this process to add more users to the
group.

Remember to :guilabel:`Save` any changes made and :guilabel:`Apply changes`.
