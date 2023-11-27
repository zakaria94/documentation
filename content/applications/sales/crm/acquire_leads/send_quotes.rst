===============
Send quotations
===============

Once a qualified lead has been converted into an opportunity, the next step is to create and deliver
a quotation. This process can be easily handled through Odoo's *CRM* application.

Create a new quotation
======================

To create a new quotation, navigate to :menuselection:`Dashboard --> CRM --> Pipeline` and click on
any lead or opportunity to open it. Review the existing information and update and fields, if
necessary.

At the top of the record, click the :guilabel:`New Quotation` button.

.. image:: send_quotes/send-quotes-new-button.png
   :align: center
   :alt: Qualified lead form with New Quotation button emphasized.

Once this button is clicked, a :guilabel:`New Quotation` form appears. Confirm the information in
the top of the form, and update any missing or incorrect fields:

.. Section needs editing, specifically update/maintain tone for all.

- :guilabel:`Customer`: The company or contact this quotation was created for.
- :guilabel:`Referrer`: If this customer was referred by another customer or contact, select it from
  the drop-down menu.
- :guilabel:`Invoice Address`: Physical address where the invoice should be sent.
- :guilabel:`Delivery Address`: Physical address where any products should be delivered.
- :guilabel:`Quotation Template`: If applicable, select a pre-configured quotation template.
- :guilabel:`Expiration`: Date when this quotation is no longer valid.
- :guilabel:`Quotation Date`: Creation date of draft/sent orders, confirmation date of confirmed
  orders.
- :guilabel:`Recurring Plan`: If this quotation is for a recurring product or subscription, select
  the recurring plan configuration to be used.
- :guilabel:`Pricelist`: Select a pricelist to be applied to this order.
- :guilabel:`Payment Terms`: Select any applicable payment terms for this quotation.

.. image:: send_quotes/send-quotes-new-quotation.png
   :align: center
   :alt: Qualified lead form with New Quotation button emphasized.

Order lines
-----------

After updating the customer, payment, and deadline information on the new quotation, the
:guilabel:`Order Lines` can be updated with the appropriate product information.

On the :guilabel:`Order Lines` tab, click :guilabel:`Add a product`. Type the name of an item into
the :guilabel:`Product` field to search through the product catalog. Select a product from the
drop-down menu, or create a new one by selecting :guilabel:`Create` or :guilabel:`Create and Edit`.

After selecting a product, update the :guilabel:`Quantity` if necessary. Confirm the information in
the remaining fields. To remove the line from the quotation, click the :guilabel:`🗑️ (trash can)`
icon.

Continue adding additional products until the quotation is ready to send.

.. seealso::
   - `Quotation Templates </applications/sales/sales/send_quotations/quote_template/>`_
   - `Optional Products </applications/sales/sales/send_quotations/optional_products/>`_
   - `Quotation Deadlines </applications/sales/sales/send_quotations/deadline/>`_

Mark an opportunity won or lost
===============================

.. Now you will need to mark your opportunity as won or lost to move the process along.

.. If you mark them as won, they will move to your *Won* column in your Kanban view. If you however
.. mark them as *Lost* they will be archived.

.. note::
   While a *Lead* can be marked as *lost*, it **must** be converted to an *Opportunity* to be marked
   as *won*. An *Opportunity* can be won or lost.

