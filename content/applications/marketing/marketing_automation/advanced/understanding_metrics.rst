================
Campaign metrics
================

Campaign metrics are detailed statistics and analytics used to measure the success and effectiveness
of a marketing campaign. When marketing activities are triggered in the workflow of a campaign
detail form, real-time metrics populate the various activity blocks to which they are related.

Activity analytics
==================

In the :guilabel:`Workflow` section of a campaign detail form, where the various campaign activities
are located, a collection of useful data can be found on every individual activity block.

.. image:: understanding_metrics/activity-analytics-block-sample.png
   :align: center
   :alt: An activity block in the workflow section with useful analytical data in Odoo.

To the left of the activity block, the configured trigger time is displayed. If it's corresponding
to an amount of time after the workflow has begun, it is displayed as a simple amount of time
(either :guilabel:`Hours`, :guilabel:`Days`, :guilabel:`Weeks`, or :guilabel:`Months`).

.. note::
   If the trigger time is dependent on another activity or triggering action (e.g. :guilabel:`Mail:
   Replied`, etc.) the time is displayed, along with the necessary action for that activity to be
   activated (e.g. *Replied after*...).

   .. image:: understanding_metrics/replied-after-activity-time-trigger.png
      :align: center
      :alt: Time trigger display when dependent on another activity in Odoo Marketing Automation.

In the activity block, a representative icon displays the type of activity the block. An
:guilabel:`✉️ (envelope)` icon means the activity is an email. Three tiny, interlocking
:guilabel:`⚙️ (gear)` icons means the activity is an internal action. And, a small, basic
:guilabel:`📱 (mobile)` icon means the activity is an SMS.

.. tip::
   The name of activity type can also be found in smaller font beneath the activity title.

Beside the activity icon, at the top of the activity block, is the title of the activity. To the
right of the activity title, there are :guilabel:`Edit` and :guilabel:`Delete` buttons.

Click :guilabel:`Edit` to open the :guilabel:`Open: Activities` pop-up form for that specific
activity, in which that activity can be modified. Click the :guilabel:`Delete` button to completely
delete that specific activity from the workflow.

Activity graph tab
------------------

By default, in every activity block, the :guilabel:`graph` tab of the activity block is selected
(represented by a :guilabel:`pie chart` icon), displaying related metrics as a simple line graph.
The success metrics are represented in `green` and the rejected metrics are represented in `red`.

A numerical representation of both (:guilabel:`Success` and :guilabel:`Rejected`) is presented to
the right of the line graph, as well.

.. tip::
   Hovering over any point in the line graph of the activity block reveals a notated breakdown of
   data for that specific date.

Beneath the graph in the activity block, *if* the activity type is *Email* or *SMS*, there is a line
of accessible data figures that are directly related to the campaign activity. These detailed
statistics provide a bird's eye view of the following metrics: :guilabel:`Sent` (numerical),
:guilabel:`Clicked` (percentage), :guilabel:`Replied` (percentage), and :guilabel:`Bounced`
(percentage).

.. tip::
   Clicking any of those stats on the :guilabel:`DETAILS` line, beneath the line graph, reveals a
   separate page containing every specific record for that particular data point.

Activity filter tab
-------------------

Next to the :guilabel:`graph` tab on the activity block, there's the option to open a
:guilabel:`filter` tab (represented by a :guilabel:`filter/funnel` icon).

.. image:: understanding_metrics/activity-filter-tab.png
   :align: center
   :alt: What a campaign activity filter tab looks like in Odoo Marketing Automation.

Clicking the :guilabel:`filter` tab on an activity block, reveals what the specific filters are for
that particular campaign activity, and how many records in the database match that specific
criteria.

.. tip::
   Clicking on the :guilabel:`records` link beneath the displayed filter reveals a separate pop-up
   window containing a list of all the records that match that specific campaign activity rule(s).

Link tracker
============

Odoo tracks all URLs used in marketing campaigns. To access and analyze those URLs, navigate to
:menuselection:`Marketing Automation app --> Reporting --> Link Tracker`. Doing so reveals a
:guilabel:`Link Statistics` page, wherein all campaign-related URLs can be analyzed.

.. image:: understanding_metrics/campaign-link-tracker.png
   :align: center
   :alt: What a campaign activity filter tab looks like in Odoo Marketing Automation.

The default view on the :guilabel:`Link Statistics` page is the :guilabel:`Bar Chart` view, but
there are different view options available in the upper-left corner. There is the option to view the
statistics as a :guilabel:`Line Chart` or :guilabel:`Pie Chart`.

Beside that, there is also the option to view the statistics as :guilabel:`Stacked`, and the data
can be put into :guilabel:`Descending` or :guilabel:`Ascending` order.

To the far-left of the view options, there is the :guilabel:`Measures` drop-down menu. When clicked,
the options to view the :guilabel:`Number of Clicks` or total :guilabel:`Count` are available. And,
to the right of the :guilabel:`Measures` drop-down menu, there's the ability to add any data to a
spreadsheet by clicking the :guilabel:`Insert in Spreadsheet` button.

Also, in the upper-right corner of the :guilabel:`Link Statistics` page, to the far-right of the
search bar, there are additional view options to choose from: the default :guilabel:`Graph` view,
the :guilabel:`Pivot` table view, and the :guilabel:`List` view.

Traces
======

Odoo tracks all activities used in every marketing campaign. The data related to these activities
can be accessed and analyzed in the :guilabel:`Traces` page, which can be found by navigating to
:menuselection:`Marketing Automation app --> Reporting --> Traces`.

.. image:: understanding_metrics/traces-page-marketing-automation.png
   :align: center
   :alt: The Traces page in the Odoo Marketing Automation application.

The default view on the :guilabel:`Traces` page is the :guilabel:`Bar Chart` view, but there are
different view options available in the upper-left corner. There is the option to view the
statistics as a :guilabel:`Line Chart` or :guilabel:`Pie Chart`.

At the top of the graph, there's a color key, informing the user which activities have been
:guilabel:`Processed`, :guilabel:`Scheduled`, and :guilabel:`Rejected`. There's also an outline
indicator to inform users of the :guilabel:`Sum` of certain activities, as well.

Beside the various view option in the upper-left corner of the :guilabel:`Traces` page, there is
also the option to view the statistics as :guilabel:`Stacked`, and the data can be put into
:guilabel:`Descending` or :guilabel:`Ascending` order.

To the far-left of the view options, there is the :guilabel:`Measures` drop-down menu. When clicked,
the options to view the :guilabel:`Document ID` or total :guilabel:`Count` are available. And,
to the right of the :guilabel:`Measures` drop-down menu, there's the ability to add any data to a
spreadsheet by clicking the :guilabel:`Insert in Spreadsheet` button.

Also, in the upper-right corner of the :guilabel:`Link Statistics` page, to the far-right of the
search bar, there are additional view options to choose from: the default :guilabel:`Graph` view,
the :guilabel:`Pivot` table view, and the :guilabel:`List` view.

Participants
============

Odoo tracks all participants related to every marketing campaign. The data related to these
participants can be accessed and analyzed in the :guilabel:`Participants` page, which can be found
by navigating to :menuselection:`Marketing Automation app --> Reporting --> Participants`.

.. image:: understanding_metrics/participants-page-marketing-automation.png
   :align: center
   :alt: The Participants page in the Odoo Marketing Automation application.

The default view on the :guilabel:`Participants` page is the :guilabel:`Pie Chart` view, but there are
different view options available in the upper-left corner. There is the option to view the
statistics as a :guilabel:`Line Chart` or :guilabel:`Bar Chart`.

At the top of the graph, there's a color key that describes the type of participiants found in the
graph.

To the far-left of the view options, there is the :guilabel:`Measures` drop-down menu. When clicked,
the options to view the :guilabel:`Record ID` or total :guilabel:`Count` are available. And, to the
right of the :guilabel:`Measures` drop-down menu, there's the ability to add any data to a
spreadsheet by clicking the :guilabel:`Insert in Spreadsheet` button.

Also, in the upper-right corner of the :guilabel:`Link Statistics` page, to the far-right of the
search bar, there are additional view options to choose from: the default :guilabel:`Graph` view,
the :guilabel:`Pivot` table view, and the :guilabel:`List` view.
