=============================
Voicemails and audio messages
=============================

.. _axivox_admin: https://manage.axivox.com/

Managing voicemail is an important part of any business. A company needs to access their messages
with ease and stay on top of any missed calls. Recording audio messages, like thanking a caller for
reaching out, or directing them to the right extension, is also a great way to personalize the
business interaction, and set the tone with the customer.

This document will cover the configuration of both voicemail and audio message in the Axivox
administrative portal.

.. _axivox/global_language:

Set global language
===================

To start the *global language* should be set in the Axivox admin portal settings. Navigate to
`manage.axivox.com <axivox_admin_>`_. After logging into the portal go to :menuselection:`Settings
--> Global language (eg: voicemail messages,...)`. Set the language to
either: :guilabel:`Francais`, :guilabel:`English`, :guilabel:`Espanol`, or :guilabel:`Deutsch`.

Click :guilabel:`Save` and then :guilabel:`Apply changes` in the upper right of the screen to
implement the change into production.

.. _axivox/activate_voicemail:

Activate voicemail
==================

In order for a user to utilize voicemail in Axivox the voicemail feature needs to be turned on in
the Axivox administrative portal. To begin using voicemail with a user navigate to
`manage.axivox.com <axivox_admin_>`_. Log in with the appropriate administrator credentials. On the
left menu of the Axivox administrative panel, click into :guilabel:`Users`.

Click into the specific user that the voicemail should be activated in. Under the section marked
:guilabel:`Voicemail`, select the dropdown and click on :guilabel:`Yes`. :guilabel:`Save` the change
and :guilabel:`Apply changes` in the upper right of the screen.

Voicemail
=========

The next step is to set up the individual voicemail boxes on the Axivox administrative portal. To
access the portal visit `manage.axivox.com <axivox_admin_>`_ and login. Navigate to
:guilabel:`Voicemails` in the left menu. If the voicemail option was activated in the user profile
using this process :ref:`axivox/activate_voicemail`, then a voicemail will automatically be created
in this :menuselection:`Voicemails` section.

.. tip::
   It should be noted that some of the administrative portal language will be in French as Axivox is
   a Belgian company. The global language is still set to one of the four options as seen here:
   :ref:`axivox/global_language`

Manually create voicemail
-------------------------

To manually create a new voicemail box, click on :guilabel:`Add a voicemail` or to edit an existing
voicemail box click :guilabel:`Edit` to the far right of the existing voicemail box.

.. example::
   Suppose a sales or support team needs a general voicemail box. The voicemail would need to be
   created manually and attached to an incoming number.

The newly manually created voicemail box should be attached to an incoming number so that it can
receive messages. To do so, first, navigate to :guilabel:`Incoming numbers` in the left menu. Then
click :guilabel:`Edit` to the far right of the specific number that the voicemail should be linked
to.

Under :guilabel:`Destination type for voice call` click the dropdown and select
:guilabel:`Voicemail`. Then select the dropdown on the next line labeled :guilabel:`Voicemail`, and
select the manually create voicemail box. Enter a :guilabel:`Destination email address for Incoming
SMS` and click :guilabel:`Save`. :guilabel:`Apply changes` in the upper right side of the screen to
implement the change into production.

.. tip::
   Under the field labeled: :guilabel:`Destination email address for Incoming SMS` enter an email
   to which incoming text messages sent to the incoming number will be received. Some incoming
   numbers (US +1) in Axivox are capable of receiving text messages from individuals and automated
   numbers. Should this field be left empty then the default destination address will be used
   instead (as previously set here in the start of manually creating a voicemail. To determine
   whether an incoming number is capable of receiving SMS/text messages click on :guilabel:`Incoming
   numbers` in the left menu. Then check the :guilabel:`SMS compatible` column for the incoming
   number.

Notifications
-------------

Anytime a voicemail is received now on any of the automatically pre-configured or manually linked
voicemail boxes, an email will be sent to the user's email address as listed in the
:menuselection:`Voicemails` screen or in the user's Axivox profile. This can be accessed by
navigating to :guilabel:`Users` in the left menu and clicking on :guilabel:`Edit` next to the
specific user in question.

.. _axivox/vm_forwarding:

Forwarding to voicemail
=======================

There are also numerous forwarding settings for a user in Axivox. To access the *Forwardings*
`manage.axivox.com <axivox_admin_>`_ and login. Navigate to :guilabel:`Users` in the left menu.
Click into the specific user that the forwarding should be added onto. Then, navigate to the
:guilabel:`Forwardings` tab.

If the user is busy on another call or away from the phone, there is an option present is this tab
to :guilabel:`Send to voicemail as a last resort`.

.. image:: vm_audio_messages/forwardings.png
   :align: center
   :alt: Send to voicemail as a last resort options highlighted on the Forwardings tab of the user.

If the box is checked for :guilabel:`Send to voicemail as a last resort`, then when the forwarding
actions stated in each section are not successful then the caller will be routed to the voicemail
set on the particular user.

.. seealso::
   For more information on forwarding and transfers visit :ref:`axivox/forwardings_tab`.

Click :guilabel:`Save`. :guilabel:`Apply changes` in the upper right side of the screen to
implement the change into production.

Audio messages
==============

It's possible to add audio messages before a customer's call is even taken, to inform them about the
waiting time for delivers, the availability of a product or even other important promotional
messages.

To record an audio message in Axivox navigate to `manage.axivox.com <axivox_admin_>`_ and login.
Click on :guilabel:`Audio messages` nin the left menu and then on :guilabel:`Add a message`. Type in
a :guilabel:`Name` and click :guilabel:`Save`

Upon clicking :guilabel:`Save` the browser will redirect back to the main :guilabel:`Audio messages`
page. There are two different ways to actually make the audio message, either by recording the
message over the phone or by typing in text and selecting a computer generated speaker to read the
message.

Record audio message
--------------------

The first option available is to record a message over the phone by clicking on the orange button
labeled: :guilabel:`Record/Listen`. The message will be recorded via one of the extensions that is
associated with a user.

Under :guilabel:`Extension to user for message management` click the dropdown and select the
extension where Axivox should call to record the message. Then click :guilabel:`OK` to begin the
call.

.. note::
   The user must be active in the production database with :abbr:`VoIP (Voice over Internet
   Protocol)` configured. To configure :abbr:`VoIP (Voice over Internet Protocol)` for a user see
   this documentation::doc:`axivox_config`.

Upon connecting to the Axivox audio recorder management line a recorded French speaking operator
will provide the following options:
#. Press `1` to record a message.
#. Press `2` to listen to the current message.

Press either `1` OR `2` depending on whether there is already a message present in the system for
this particular audio message (press 2) or if a new audio message needs to be recorded (press 1).

Record the audio message after pressing `1`, then press `#` to end the recording. The French
speaking operator will return to the line presenting the first set of questions again:
#. Press `1` to record a message.
#. Press `2` to listen to the current message.

Press `#` to end the call.

Write audio message
-------------------

The second option to obtain an audio message is to type the message out and select a computerized
speaker to say the text. To do so, simply, navigate to the :guilabel:`Audio messages` page by
clicking on :guilabel:`Audio messages` in the left panel. Then select the blue button labeled:
:guilabel:`Text message` next to the corresponding audio message :guilabel:`Name` that the audio
message should be attached to.

Click the dropdown next to the field labeled :guilabel:`Voice` and select a :guilabel:`Voice` for
the :guilabel:`Text` to be read in. After the selection has been made, click :guilabel:`Generate` to
process the audio file. The text will be read in the language that it is written in the
:guilabel:`Text` field. Should the language differ in the :guilabel:`Voice` then an accent will be
used by the computerized speaker.

Finally when these steps are complete, click :guilabel:`Save` to save the audio message.

To implement the changes, click :guilabel:`Apply changes` in the upper right-side of the screen.

.. tip::
   To use a audio message associated with a dial plan menu element see this documentation
   :doc:`dial_plan_basics`, or :doc:`dial_plan_advanced`.

Music on-hold
=============

Axivox has the option to add custom hold music to the call whenever a caller is waiting for their
call to be answered. To add *hold music* on to the Axivox administrative portal, navigate to the
`manage.axivox.com <axivox_admin_>`_, and login. Click on :guilabel:`Music on hold` and a pop-up
will appear.

On the :menuselection:`Change the music on hold` pop-up, click on the :guilabel:`Browse...` button
to select the MP3 (MPEG Audio Layer 3) or WAV (Waveform Audio File Format ) file to be uploaded.

.. note::
   Only :abbr:`MP3 (MPEG Audio Layer 3)` or :abbr:`WAV (Waveform Audio File Format)` files can be
   uploaded to the Axivox administrative portal.

Once the file is selected, the :guilabel:`Progression` bar will show activity. When this activity
subsides, then the window can be closed, by clicking :guilabel:`Close`.

:guilabel:`Apply changes` in the upper right-side of the screen.
