======
Xendit
======

`Xendit <https://www.xendit.co>`_ is an Indonesian-based payment solution provider that covers
several Southeast Asian countries, allowing businesses to accept credit cards and several local
payment methods.

.. _payment_providers/xendit/configure_dashboard:

Configuration on Xendit Dashboard
=================================

#. Create a Xendit account if necessary and log in to the `Xendit Dashboard
   <https://dashboard.xendit.co>`_.
#. Check your account mode on the top left. Use the :guilabel:`Test Mode` to try the integration
   without charging your customers. Switch to :guilabel:`Live Mode` once you are ready to accept
   payments.

API key
-------

#. Go to `Configuration: Settings --> Developers: API Keys
   <https://dashboard.xendit.co/settings/developers#api-keys>`_ and click :guilabel:`Generate secret
   key`.
#. In the popup box, enter any :guilabel:`API key name`, select :guilabel:`Write` for
   the :guilabel:`Money-in Products` permission and :guilabel:`None` for all other permissions
   to keep your data secured, and click :guilabel:`Generate key`.
#. After confirming your password, your API key is displayed. Copy or download the key and **save
   this information securely**. It is the only time the API key can be viewed.

Webhook token and URL
---------------------

#. Go to `Configuration: Settings --> Developers: Webhooks
   <https://dashboard.xendit.co/settings/developers#webhooks>`_. Under :guilabel:`Webhook
   Verification Token`, click :guilabel:`View Webhook Verification Token` to generate it.
#. After confirming your password, your token is displayed. Save this information securely.
#. In the :guilabel:`Webhook URL` section, enter your Odoo database URL (e.g.,
   `https://example.odoo.com`) and click :guilabel:`Test and save` for each of the following fields:

   - :guilabel:`Unified Refunds: Refund request succeeded`
   - :guilabel:`Unified Refunds: Refund Request failed`
   - :guilabel:`Invoices: Invoices paid`

Optional 3DS
------------

Go to `Configuration: Payment Methods --> Cards: Settings
<https://dashboard.xendit.co/settings/payment-methods/cards-configuration#card-settings>`_ and
enable :guilabel:`Optional 3DS`.

Configuration on Odoo
=====================

#. :ref:`Navigate to the payment provider Xendit <payment_providers/add_new>` and change its state
   to :guilabel:`Enabled`.
#. Fill in the :guilabel:`Xendit API Key` and :guilabel:`Xendit Callback Token` fields with the
   information saved from the previous steps.
#. Configure the rest of the options to your liking.

.. seealso::
   :doc:`../payment_providers`
