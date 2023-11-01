=========================
Amazon Connector features
=========================

The *Amazon Connector* synchronizes orders between Amazon and Odoo, which considerably reduces the
amount of time spent on the Amazon Seller Central dashboard.

Supported features
==================

The *Amazon Connector* is able to:

- Synchronize (Amazon to Odoo) all confirmed orders (both FBA and FBM), and their order items, which
  include:

  - product name, description, and quantity
  - shipping costs for the product
  - gift wrapping charges

- Create any missing partner related to an order in Odoo (contact types supported: contact and
  delivery).

- Notify Amazon of confirmed shipping in Odoo (FBM) to get paid.

- Support multiple seller accounts.

- Support multiple marketplaces per seller account.

+----------------------+----------------------------+-------------------------------------+
|                      | Fulfilled By Amazon (FBA)  | Fulfilled By Merchant (FBM)         |
+======================+============================+=====================================+
| **Orders**           | Synchronize shipped and    | Synchronize unshipped and canceled  |
|                      | canceled orders            | orders                              |
+----------------------+----------------------------+-------------------------------------+
| **Shipping**         | - Charges                  | - Charges                           |
|                      |                            | - Delivery created                  |
+----------------------+----------------------------+-------------------------------------+
| **Gift Wrapping**    | - Handled by Amazon        | - Gift wrapping charges             |
|                      |                            | - Gift message                      |
+----------------------+----------------------------+-------------------------------------+
| **Stock Management** | One stock move created     | Handled by the delivery             |
|                      | per sales order item       |                                     |
+----------------------+----------------------------+-------------------------------------+
| **Confirmation**     | Handled by Amazon          | Notify Amazon when confirming       |
|                      |                            | delivery                            |
+----------------------+----------------------------+-------------------------------------+

.. note::
   The connector is designed to synchronize the data of sales orders, as detailed above. Other
   actions, such as downloading monthly fees reports, handling disputes, or issuing refunds,
   **must** be managed from the *Amazon Seller Central*, as usual.

.. _amazon/supported-marketplaces:

Supported marketplaces
======================

The *Amazon Connector* supports all the current marketplaces.

If a marketplace is not listed in your Amazon marketplaces, it's possible to :ref:`add a new
marketplace <amazon/add-new-marketplace>`.

.. seealso::
   - :doc:`setup`
   - :doc:`manage`
