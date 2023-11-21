:show-content:

=========
Reporting
=========

Main reports available
======================

Odoo includes **generic** and **dynamic** reports available for all countries, regardless of the
:doc:`localization package <../../finance/fiscal_localizations>` installed:

-  **Balance Sheet**
-  **Profit and Loss**
-  **Executive Summary**
-  **General Ledger**
-  **Aged Payable**
-  **Aged Receivable**
-  **Cash Flow Statement**
-  **Tax Report**

Reports can be **annotated, printed, exported to XLSX or PDF**, and **drilled down** to see details
(payments, invoices, journal items, etc.).

.. image:: reporting/reporting-annotate.png
   :alt: Annotate reports.

You can compare values across periods. Go to the :guilabel:`Comparison` menu, and select the time
periods you want to compare.

.. image:: reporting/reporting-comparison.png
   :alt: Comparison menu to compare time periods.

.. _reporting/balance-sheet:

Balance Sheet
-------------

The **Balance Sheet** shows a snapshot of the assets, liabilities and equity of your organisation at
a particular date.

.. image:: reporting/reporting-balance-sheet.png
   :alt: Balance sheet report of Odoo.

.. _reporting/profit-and-loss:

Profit and Loss
---------------

The **Profit and Loss** report (or **Income Statement**) shows your company's net income by
deducting expenses from revenue for the report period.

.. image:: reporting/reporting-profit-and-loss.png
   :alt: Profit and Loss report of Odoo

.. _reporting/executive-summary:

Executive Summary
-----------------

The **Executive Summary** allows for a quick look at all the important figures to run your company.

In basic terms, this is what each item in the following section reports:

- **Performance:**
    - **Gross profit margin:**
        The contribution of each individual sale made by your business **minus** any direct costs
        needed to make those sales (labour, materials, etc).
    - **Net profit margin:**
        The contribution of each individual sale made by your business **minus** any direct costs
        needed to make those sales *and* fixed overheads your company has (electricity, rent, taxes
        to be paid as a result of those sales, etc).
    - **Return on investment (p.a.):**
        The ratio of net profit made to the amount of assets the company used to make those profits.
- **Position:**
    - **Average debtor days:**
        The average number of days it takes your customers to (fully) pay you across all your
        customer invoices.
    - **Average creditor days:**
        The average number of days it takes you to (fully) pay your suppliers across all your bills.
    - **Short term cash forecast:**
        How much cash is expected in or out of your business in the next month, i.e., the balance of
        your **Sales account** for the month **minus** the balance of your **Purchases account** for
        the month.
    - **Current assets to liabilities:**
        Also referred to as **current ratio**, this is the ratio of current assets (assets that
        could be turned into cash within a year) to the current liabilities (liabilities that will
        be due in the next year). This is typically used to measure a company's ability to service
        its debt.

.. image:: reporting/reporting-executive-summary.png
   :alt: Executive summary report in Odoo.

.. _reporting/general-ledger:

General Ledger
--------------

The **General Ledger Report** shows all transactions from all accounts for a chosen date range. The
initial summary report shows each account's totals; from there, you can view a detailed transaction
report or any exceptions. This report helps check every transaction that occurred during a specific
period.

.. image:: reporting/reporting-general-ledger.png
   :alt: General Ledger report in Odoo.

.. _reporting/aged-payable:

Aged Payable
------------

Run the **Aged Payable Details** report to display information on individual bills, credit notes,
and overpayments owed by you, and how long these have gone unpaid.

.. image:: reporting/reporting-aged-payable.png
   :alt: Aged Payable report in Odoo.

.. _reporting/aged-receivable:

Aged Receivable
---------------

The **Aged Receivables** report shows the sales invoices that were awaiting payment during a
selected month and several months prior.

.. image:: reporting/reporting-aged-receivable.png
   :alt: Aged Receivable report in Odoo.

.. _reporting/cash-flow-statement:

Cash Flow Statement
-------------------

The **Cash Flow Statement** shows how changes in balance sheet accounts and income affect cash and
cash equivalents, and breaks the analysis down to operating, investing and financing activities.

.. image:: reporting/reporting-cash-flow-statement.png
   :alt: Cash Flow Statement report in Odoo.

.. _reporting/tax-report:

Tax Report
----------

This report allows you to see the **net** and **tax amounts** for all the taxes grouped by type
(sale/purchase).

.. image:: reporting/reporting-tax-report.png
   :alt: Tax report in Odoo.

.. toctree::
   :titlesonly:

   reporting/tax_returns
   reporting/analytic
   reporting/budget
   reporting/intrastat
   reporting/data_inalterability
   reporting/silverfin
   reporting/customize
   reporting/year_end
