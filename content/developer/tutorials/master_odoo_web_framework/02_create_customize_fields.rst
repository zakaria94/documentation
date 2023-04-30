======================================
Chapter 2: Create and Customize fields
======================================


Fields and views are among the most important concepts in the Odoo user interface. They are key to
many important user interactions, and should therefore work perfectly. In the context of the
JavaScript framework, fields are components specialized for visualizing/editing a specific field for
a given record. For example, a (Python) model may define a char field, which will be represented by
a field component `CharField`.

A field component is basically just a component registered in the `fields` :ref:`registry
<frontend/registries>`. The field component may define some additional static keys (metadata), such
as `displayName` or `supportedTypes`, and the most important one: `extractProps`, which prepare the
base props received by the `CharField`.

.. spoiler:: Solutions

   The solutions for each exercise of this chapter are hosted on the
   `official Odoo tutorials repository
   <https://github.com/odoo/tutorials/commits/{CURRENT_MAJOR_BRANCH}-solutions/awesome_fields>`_. It
   is recommended not to look at them before trying the exercises.


Example: a simple field
=======================

Let us discuss a simplified implementation of a `CharField`. First, here is the template:

.. code-block:: xml

   <t t-name="web.CharField" owl="1">
       <t t-if="props.readonly">
           <span t-esc="formattedValue" />
       </t>
       <t t-else="">
           <input
               class="o_input"
               t-att-type="props.isPassword ? 'password' : 'text'"
               t-att-placeholder="props.placeholder"
               t-on-change="updateValue"
           />
       </t>
   </t>

It features a readonly mode and an edit mode, which is an input with a few attributes. Now, here
is the JavaScript code:

.. code-block:: js

   class CharField extends Component {
       static template = "web.CharField";

       get formattedValue() {
           return formatChar(this.props.value, { isPassword: this.props.isPassword });
       }

       updateValue(ev) {
           let value = ev.target.value;
           if (this.props.shouldTrim) {
               value = value.trim();
           }
           this.props.update(value);
       }
   }

   const charField = {
       component: CharField,
       displayName: _lt("Text"),
       supportedTypes: ["char"],
       extractProps: ({ attrs, options }) => ({
           isPassword: archParseBoolean(attrs.password),
           autocomplete: attrs.autocomplete,
           placeholder: attrs.placeholder,
    }),
   };

   registry.category("fields").add("char", charField);

There are a few important things to notice:

- The `CharField` receives its (raw) value in props. It needs to format it before displaying it.
- It receives an `update` function in its props, which is used by the field to notify the owner of
  the state that the value of this field has been changed. Note that the field does not (and should
  not) maintain a local state with its value. Whenever the change has been applied, it will come
  back (possibly after an onchange) by the way of the props.
- It defines an `extractProps` function. This is a step that translates generic standard props,
  specific to a view, to specialized props, useful to the component. This allows the component to
  have a better API, and may make it so that it is reusable.

Fields have to be registered in the `fields` registry. Once it's done, they can be used in some
views (namely: `form`, `list`, `kanban`) by using the `widget` attribute.

.. example::

   .. code-block:: xml

      <field name="preview_moves" widget="account_resequence_widget"/>

.. _tutorials/master_odoo_web_framework/image_preview_field:

1. Define your own `char` field
===============================

- Take the code above and register it in the registry under another name: `awesome_char`.
- Modify the template to display a red border around the field value, so you can easily identify it
- Edit a form view to force Odoo to use your field: `widget="awesome_char"`. 
- Test it!

1. Use a field in a list view
=============================

- Use your field in a list view



1. An `image_preview` field
===========================

Each new order on the website will be created as an `awesome_tshirt.order`. This model has a
`image_url` field (of type `char`), which is currently only visible as a string. We want to be able
to see the image itself in the form view.

.. exercise::

   #. Create a new `ImagePreview` component and register it in the proper :ref:`registry
      <frontend/registries>`. Use the `CharField` component in your template. You can use `t-props
      <{OWL_PATH}/doc/reference/props.md#dynamic-props>`_ to pass props received by `ImagePreview`
      to `CharField`. Update the arch of the form view to use your new field by setting the `widget`
      attribute.
   #. Change the code of the `ImagePreview` component so that the image is displayed below the URL.
   #. When the field is readonly, only the image should be displayed and the URL should be hidden.

.. note::
   It is possible to solve this exercise by inheriting `CharField`, but the goal of this exercise is
   to create a field from scratch.

.. image:: 02_create_customize_fields/image_field.png
   :align: center
   :scale: 50%

.. seealso::

   `Code: CharField <{GITHUB_PATH}/addons/web/static/src/views/fields/char/char_field.js>`_

2. Improving the `image_preview` field
======================================

We want to improve the field of the previous task to help the staff recognize orders for which some
action should be done.

.. exercise::

   Display a warning "MISSING TSHIRT DESIGN" in red if there is no image URL specified on the order.

.. image:: 02_create_customize_fields/missing_image.png
   :align: center

3. Customizing a field component
================================

Let's see how to use inheritance to extend an existing component.

There is a `is_late`, readonly, boolean field on the order model. That would be useful information
to see on the list/kanban/view. Then, let us say that we want to add a red word "Late!" next to it
whenever it is set to `true`.

.. exercise::

   #. Create a new `LateOrderBoolean` field inheriting from `BooleanField`. The template of
      `LateOrderBoolean` can also :ref:`inherit <reference/qweb/template_inheritance>` from the
      `BooleanField` template.
   #. Use it in the list/kanban/form view.
   #. Modify it to add a red `Late` next to it, as requested.

.. image:: 02_create_customize_fields/late_field.png
   :align: center

.. seealso::
   - `Example: A field inheriting another
     <{GITHUB_PATH}/addons/account/static/src/components/account_type_selection>`_
   - :ref:`Documentation on xpath <reference/views/inheritance>`

