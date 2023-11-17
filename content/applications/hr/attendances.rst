===========
Attendances
===========

Odoo's *Attendances* application functions as a time clock. Employees are able to check in and out
of work, either in the database, or using a dedicated device in kiosk mode. Managers can quickly see
who is available at any given time, and create reports to see everyone's hours, and gain insights on
which employees working overtime, or checking out earlier than expected.

Access Rights
=============

It is important to understand how the different access rights affect what user's can access in the
*Attendances* application.

Every user in the database is always able to access their own information on the dashboard, and can
check in and out directly from the database. Access to all the other features are determined by
access rights.

To see what access rights a user has, navigate to :menuselection:`Settings application --> Users &
Companies: Users`, and click on the user. The :guilabel:`Access Rights` tab is visible by default.
Scroll down to the :guilabel:`Human Resources` section to see the setting. For the
:guilabel:`Attendances` field, the options are either to leave the field blank, or select
:guilabel:`Administrator`.

If the :guilabel:`Administrator` option is selected, the user has full access to the entire
*Attendances* application, with no restrictions. They can view all employee attendance records,
enter kiosk mode, access all reporting metrics, and make modifications to the settings.

If left blank, the user can only view their own information on the *Attendances* application
dashboard, and can view their own personal attendance records under the reporting feature. Everyone
else's attendance records will be hidden from view on the report. There is no access to either the
kiosk mode or the configuration menu.

Approvers
---------

The only other scenario where different information may be accessible in the *Attendances*
application is for approvers, who are typically managers (but this is not necessary). If a user does
*not* have administrative rights for the *Attendances* application, but they are set as an
attendance approver for an employee, that user will be able to view the attendance records for that
employee. This applies to all employee's that the user is listed as the attendance approver.

To see who the attendance approver is for an employee, navigate to the :menuselection:`Employees
application` and click on the specific employee. Click on the :guilabel:`Work Information` tab, and
scroll to the :guilabel:`Approvers` section, and check the :guilabel:`Attendance` field. The person
selected will be able to view that employees' attendance records both on the *Attendances*
application dashboard, as well as in the attendance reports.


Configuration
=============

There are very few configurations needed in the *Attendances* application. Determining how employees
check in and out, defining how the kiosks function, and determining how extra hours are computed are
all set in the Configuration menu. Navigate to :menuselection:`Attendances --> Configuration` to
access the configuration menu.

Modes
-----

- :guilabel:`Kiosk Mode`: Using the drop-down menu, select how an employee checks in when using a
  kiosk. Options are :guilabel:`Barcode/RFID`, :guilabel:`Barcode/RFID and Manual Selection`, or
  :guilabel:`Manual Selection`.

  .. important::
     The *Barcode* application **does not** need to be installed in order to use one of the
     Barcode/RFID settings.

- :guilabel:`Attendances from Backend`: Activate this selection to allow employees to check in and
  out directly from the Odoo database. If this is not activated, employees must use a kiosk to check
  in and out of work.

.. _attendances/kiosk-settings:

Kiosk Settings
--------------

This section only needs to be configured if employees use kiosks for checking in and out. If kiosks
are *not* being used, modifying any of these fields will **not** adversely affect the functionality
of the Attendances application.

- :guilabel:`Barcode Source`: This setting appears if either of the two Barcode/RFID selections were
  configured for the :guilabel:`Kiosk Mode` setting. Select how barcodes are scanned at the kiosk,
  either with a dedicated barcode :guilabel:`Scanner`, or the device's :guilabel:`Front Camera`, or
  :guilabel:`Back Camera`.
- :guilabel:`Employee PIN Identification`: Activate this option if employees should use a unique PIN
  number to check in. PIN numbers are configured on each individual employee record. Refer to the
  :doc:`../hr/employees/new_employee` documentation for more information on setting up PIN
  numbers.
- :guilabel:`Display Time`: Set the duration (in seconds) the check in and out confirmation screen
  remains on the kiosk before going back to the main check in screen.
- :guilabel:`Attendance Kiosk Url`: Odoo generates a unique web address (url) for use with the
  kiosk(s). When setting up a kiosk device, click the :guilabel:`Copy` button at the end of the url
  to copy the link. Kiosks work by navigating to this unique web address, and presenting the
  Attendances application check-in screen.

  .. important::
     These kiosk urls are **not** secured with any type of access code. Anyone who has the url can
     access the check in kiosk webpage. If necessary, such as a security breach, generate a new url
     by clicking :guilabel:`Generate a new Kiosk Mode URL`, located beneath the link, and update the
     kiosk(s) accordingly.

Extra Hours
-----------

- :guilabel:`Count of Extra Hours`: Enable this box to allow employees to log extra hours beyond
  their set working hours (sometimes referred to as *overtime*). Activating this selection displays
  the following settings as well. If this is not activated, no other configurations appear.

  - :guilabel:`Start From`: The current date is automatically entered in this field. If desired,
    click on this field and use the calendar selector to modify the start date that extra hours can
    be logged.
  - :guilabel:`Tolerance Time In Favor Of Company`: Enter the amount of time, in minutes, that will
    *not* count towards an employee's overtime. When an employee checks out, and the extra time
    logged is within the specified minutes, the extra time will *not* be counted as overtime for the
    employee.
  - :guilabel:`Tolerance Time In Favor Of Employee`: Enter the amount of time, in minutes, that an
    employee is given, that will not adversely affect their attendance if they log less time than
    their working hours. When an employee checks out, and the total time logged for the day is less
    than their specified working hours, but within this grace period, they will not be penalized for
    their reduced hours.
  - :guilabel:`Display Extra Hours`: Activate this box to display the extra hours logged by the
    employee on both the kiosk and the user's profile.

    .. example::
       A company sets both of the :guilabel:`Tolerance` fields to `15` minutes, and the working
       hours for the entire company is set from 9:00 AM to 5:00 PM. If an employee checks in at 9:00
       AM, and checks out at 5:14 PM, the extra 14 minutes are *not* counted towards their overtime.
       If an employee checks in at 9:05 AM, and checks out at 4:55 PM, even though they logged a total
       of 10 minutes less than their full shift, they will not be penalized for this discrepancy.


Check in and out via the database
=================================

Odoo's *Attendances* application allows employee's who are logged into the database to check in and
out, without needing to go into the *Attendances* application, or use a kiosk. For some smaller
companies, this feature may be particularly useful.

A user can check in and out on the main database dashboard, as well as in any application. In the
upper right corner of the top main menu, which is always visible regardless of what application the
user is in, a :guilabel:`red circle` or :guilabel:`green circle` is visible. Click on the colored
circle to reveal the attendance widget, enabling the user to check in and/or out.

Check in
--------

If the attendance widget circle is red, this indicates the user is not currently checked in. Click
the :guilabel:`red circle` and the attendance widget appears, displaying a green :guilabel:`Check
in ->` button.

If the user has not checked in and out already during the current work day, this button is the only
visible item in the widget. If the user has previously checked in and out, a :guilabel:`Total today`
field appears above the button, and the total amount of time that has been logged for the day
appears beneath that field, in an :guilabel:`XX:XX` (hours:minutes) format.

Click the :guilabel:`Check in ->` button to check in. The red circle in the top menu changes to
green, and the widget changes appearance as well. The widget updates to reflect that the user has
checked in, by changing the green :guilabel:`Check in ->` button to a yellow :guilabel:`Check out
->` button.

Click the :guilabel:`green circle` in the top main menu to close the attendance widget.

Check out
---------

If the user is checking out for the first time, :guilabel:`Since XX:XX (AM/PM)` appears at the top
of the widget, with the time the user checked in populating the time field. Beneath that line,
:guilabel:`XX:XX` is displayed, indicating the hours and minutes that have elapsed since checking
in. As time passes, this value is updated to reflect the hours and minutes that have passed since
the user checked in.

If the user has previously checked in and out, additional fields are presented. A :guilabel:`Before
XX:XX (AM/PM)` field appears in addition to the :guilabel:`Since XX:XX (AM/PM)` field. The time
displayed in both of these fields are populated with the most recent check in time, and will match.
Beneath the :guilabel:`Before XX:XX (AM/PM)` field, the previously logged hours are displayed, in an
:guilabel:`XX:XX` (hours:minutes) format.

In addition, beneath both of these fields, a :guilabel:`Total today` field appears. This field is
the sum of both the :guilabel:`Before XX:XX (AM/PM)` and :guilabel:`Since XX:XX (AM/PM)` fields, and
is the total time that will be logged for the employee, if they were to log out at that moment.

As time passes, both the :guilabel:`Since XX:XX (AM/PM)` and :guilabel:`Total today` fields are
updated live. To check out, click the yellow :guilabel:`Check out ->` button. The attendance widget
updates again, displaying the :guilabel:`Total today` field with the logged time, and the yellow
:guilabel:`Check out ->` button changes to a green :guilabel:`Check in ->` button.

.. tip::
   There is no limit to the amount of times a user can check in and check out. Users are able to
   check in and out without any time elapsing (a value of 00:00). Each time an employee logs in and
   out, the information is stored and appears on the dashboard, including check ins and check outs
   with no time value.

Kiosk Mode
==========

Some companies may opt to use a dedicated device (a laptop or desktop PC, a tablet, or a mobile
phone) for employees to log in and out from. Kiosk mode is used for these scenarios.

.. important::
   If users check in and out using either a badge or an RFID, then an accessible device in kiosk
   mode must be available in order to log in using these two methods.

There are two ways that kiosk mode can be activated:

#. Navigate to the :guilabel:`Attendances` application, and click :guilabel:`Kiosk Mode` in the top
   menu. The device then goes into kiosk mode.
#. Navigate to the :menuselection:`Attendances application --> Configuration`. In the
   :guilabel:`Kiosk Settings` section, click :guilabel:`Copy` next to the link beneath the
   :guilabel:`Attendance Kiosk Url` field. Paste this url into a web browser and navigate to it.
   This link navigates to the same url as the :guilabel:`Kioks Mode` button.

As a security measure, once a device is in kiosk mode, it is not possible to exit kiosk mode and go
back into the database without singing back in. To exit kiosk mode, click :guilabel:`Go to Backend`
in the lower right corner of the screen. This logs the user out of the database, and returns to the
main log in screen. This prevents anyone from accessing the database, adding another layer of
security.

Badge
-----

To check in or out using a badge, tap the :guilabel:`Tap to scan` image on the center of the kiosk.
Then, scan the barcode on the badge using the method configured in the :ref:`kiosk settings
<attendances/kiosk-settings>` section of the configuration menu. Options are a dedicated barcode
scanning device, or the kiosk's front or back camera. Once the barcode is scanned, the employee
is checked in or out, and a :ref:`confirmation message <attendances/confirmation>` appears with all
the check in or check out information.

RFID
----

To check in or out using an RFID key fob, simply scan the fob with an RFID reader. Once scanned, the
employee is then either checked in or checked out, and a :ref:`confirmation message
<attendances/confirmation>` appears with all the check in or check out information.

Manually
---------

For user's who either do not have a scannable badge or an RFID fob, or simply do not have them when
checking in our out, users can manually check in and out at a kiosk. Tap the :guilabel:`Identify
Manually` button on the kiosk, and a screen with all the employees that can be checked in or out
appears. This is the same view as in the *Employees* application dashboard. Tap on the person, and
they are either checked in or checked out, and a :ref:`confirmation message
<attendances/confirmation>` appears.

When a large number of employees appear in the list, making scrolling inefficient, there are two
ways to quickly find a specific person:

- :guilabel:`Search...`: Tap on the :guilabel:`Search...` field and enter the person's name. As the
  name is typed in, the matching results are displayed on the screen.
- :guilabel:`Department`: To quickly filter the presented employees, tap on a department to display
  only those employees that are part of that department. The :guilabel:`Departments` are listed on
  the left side of the screen, and the number at the end of each department indicates how many
  employees are part of the department, and will be displayed when selected.

PIN number
~~~~~~~~~~

If the :guilabel:`Employee PIN Identification` option was activated in the :ref:`kiosk settings
<attendances/kiosk-settings>` section of the configuration menu, the employee is prompted to enter a
PIN number when manually checking in or out.

After the employee is selected, a number pad appears, and an :guilabel:`(Employee) Want to check
(in or out)? Please enter your PIN to (check in or out)` message appears above the numbers. Tap in
the PIN number using the number pad, then tap :guilabel:`OK` when done. The employee is then checked
in or out, and the :ref:`confirmation message <attendances/confirmation>` appears.

.. _attendances/confirmation:

Confirmation message
--------------------

When an employee checks in or out, a confirmation message appears with all the check in or check out
information. When checking in, a welcome message appears, as well as the date and time of check in.
An :guilabel:`Hours Previously Today: XX:XX` field also appears, displaying any time already logged
for that employee for the day. If no time has already been logged, the value displayed is `00:00`.
Beneath the message is an :guilabel:`OK` button. To exit the screen before the preset time, tap the
:guilabel:`OK` button.

When checking out, the message displays a goodbye message, with the date and time of check out, and
the total hours logged for the day. Beneath the message is a :guilabel:`Goodbye` button. To exit the
screen before the preset time, tap the :guilabel:`Goodbye` button.

Overview
========



Reporting
=========











.. seealso::
   `Odoo Tutorials: Attendances <https://www.odoo.com/slides/slide/attendances-684>`_


.. toctree::
   :titlesonly:

  attendances/hardware
