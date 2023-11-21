===========
Pricer tags
===========

Pricer electronic price tags allow you to display the information about your products on the
electronic displays. This allows you to adapt your products information dynamically and avoid
having to print price labels on paper whenever you change your products information.

Configuration
=============

Pricer setup prerequisites
--------------------------

The following steps need to be configured on Pricer side
before being able to use it with Odoo:

When you configure a Pricer account, make sure you get the access to send requests to their API.

Once you have configured your account and your stores,
you will need setup some variables for your Pricer database:

.. note::
   Odoo will send the following information to Pricer:
    - "itemId" : the internal id of your products
    - "itemName" : the name of your products
    - "price" : the price of your products including taxes, if any
    - "presentation": the template name used for Pricer tags display
    - "currency" : the currency of your Odoo company
    - "barcode" : the barcode associated to your products, if any

.. warning::
    The names for these variables must be **exactly the same** in your Pricer database

After you have created the variables with the names above,
you will need to configure a template which will be used
to display information on your Pricer tags.

.. note::
    In order to use Pricer with Odoo, make sure your template is named **"NORMAL"**


Finally when your account, your stores, your variables and your template are correctly configured
on Pricer, you can proceed to the Odoo setup.

Install the POS Pricer module in Odoo
-------------------------------------

To activate the POS Pricer module in Odoo, go to :guilabel:`Apps`, remove the :guilabel:`Apps` filter, and
search for **POS Pricer**. This module adds the necessary features for you to be able to use Pricer
electronic tags.

.. image:: pricer_tags/pos_pricer_in_apps.png
   :alt: Installing POS Pricer module from Apps

Once the POS Pricer module is installed, you will need to configure some Pricer stores in Odoo


Configure a Pricer Store in Point Of Sale
-----------------------------------------

.. image:: pricer_tags/pricer_stores_in_pos.png
   :alt: Open Pricer Stores from Point of Sale configuration

Go to :menuselection:`Point of Sale --> Configuration --> Pricer --> Pricer Stores` and click :guilabel:`New` or
select an existing pricelist.

.. note::
   Odoo will need the following information from Pricer to be able to communicate with your tags:
    - "Pricer Tenant Name" : the name of your company account in Pricer, usually followed by **"-country_code"**
    - "Pricer Login" : the login of a Pricer account
    - "Pricer Password" : the password for the Pricer account above
    - "Pricer Store ID": the id of a Pricer store as defined on your Pricer database

.. image:: pricer_tags/pricer_stores_setup.png
   :alt: Configuring a Pricer Store

.. warning::
    The account associated to your Pricer store must have access to send API requests to Pricer

Once you have configured at least one Pricer Store correctly, you can associate Pricer tags to your products in Odoo


Link your products to Pricer tags
---------------------------------

Go to :menuselection:`Point of Sale --> Products --> Products` and click :guilabel:`New` or
select an existing product.

.. warning::
    If you are creating a new product, make sure you configure and save it before associating
    any Pricer tags to it.

When your product has all the information you need, go to :menuselection:`Sales --> Pricer --> Pricer Store`
and select the Pricer store you configured in the previous step.

Once a product has a Pricer store associated to it, you will be able to link Pricer tags to it
by inputting their id's in the **Pricer tag ids** section.

It is recommended to use a barcode scanner for this.

.. image:: pricer_tags/product_tags_link.png
   :alt: Linking Pricer tags to products

.. tip::
   When setting up Pricer with Odoo for the first time, it is recommended to configure only
   one product first.

   Make sure you are able to display its information on a Pricer tag before configuring the rest of them.

   If you can display a product's information on a Pricer tag, your configuration is done correctly.

Now that you have a product associated to a Pricer tag, we can send its information to Pricer


Displaying your product information on Pricer tags
--------------------------------------------------

When you associate a product to a Pricer tag in Odoo, the link request will not be sent straight away.

Every 12 hours Odoo will check if you have linked any new Pricer tags or updated some products information
with associated Pricer tags.

If so, Odoo will send a request to Pricer to link new Pricer tags or update the displayed information.

The whole process is done automatically to keep your products information syncrhonized in Odoo and on displays.

However, if you want to manually force the request at a given moment, you can go to
:menuselection:`Point of Sale --> Configuration --> Pricer --> Pricer Stores`, select the Pricer Store
you want to update and click on :guilabel:`Update tags`

.. image:: pricer_tags/update_tags_manually.png
   :alt: Update Pricer tags manually

Once a request has been sent to Pricer, you can see its time and status in under **Last Update** and **Last Update Status** fields
The **Last Update** and **Last Update Status** fields also allow you to track the time and status of automatic updates every 12 hours.

.. note::
   The request will only be sent to Pricer for products which have one of these fields modified since the last request:
   - Product Name
   - Product Price
   - Product Customer Taxes
   - Product barcode
   - Product currency
   - Associated Pricer Store
   - Associated Pricer tags
   If the product wasn't modified for one of these fields since the last request sent to Pricer, no new request will be sent for it

.. warning::
    If a request sent to Pricer failed, Odoo will still consider that the product has been updated,
    so no retry request will be sent for that product

If the request has been processed and accepted by Pricer, the status field will show **"Update successfully sent to Pricer"**
Otherwise, an error message will be shown.

.. tip::
   If for some reason your update requst failed despite a correct configuration or you want to make sure all the products are linked, you
   can go to :menuselection:`Point of Sale --> Configuration --> Pricer --> Pricer Stores`, select the desired Pricer stores and click on
   :guilabel:`Update all tags` button, which is only visible in :ref:`Developer Mode (debug mode) <developer-mode>`.

   This will send a request to Pricer to link and update **all** products associated to the selected Pricer stores.

.. image:: pricer_tags/update_all_pricer_stores_button.png
    :alt: Update all Pricer tags
