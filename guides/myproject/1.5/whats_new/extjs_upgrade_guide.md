# Ext JS 6.5.0 Upgrade Guide

## Introduction

Ext JS 6.5 represents a major update to the Modern toolkit and does contain a few breaking 
changes and a number of API's have been deprecated. This guide will walk you through all 
you need to know to upgrade your Ext JS 6.2 application to version 6.5.

While the Classic toolkit does not contain any breaking changes there are some changes in 
the core that can impact Classic applications.

## Modern Toolkit

### Component

#### cls

The cls config of component was adjusted slightly and its relationship to the `addCls`, 
`removeCls`, `replaceCls`, and `toggleCls` method family has changed. The `cls` config no 
longer interacts with these other API's. It simply removes the previous class(es) and 
adds the new one(s). These other API's now directly delegate to the Element API and do 
not affect the `cls` config value.

#### draggable

Instead of instantiating the Ext.util.Draggable class, the draggable config now creates 
an `Ext.drag.Source` instance. This relationship is now a public whereas the details 
of how draggable was previously implemented were private. Even so, it is understood 
that many real-world applications would have had to dig beyond the public level and 
so this is viewed as a breaking change.

One important outcome of this change is that the drag event is no longer fired, but 
instead a `dragmove` event is fired. The signatures of other drag events are also 
different compared to those fired by `Ext.util.Draggable`.

#### painted

The signature for the painted event now conforms with the standard for component 
events by passing the component as the first argument.

    listeners: {
        painted: function (comp, element) {
        }
    }

#### resize / onResize

The resize event now matches the signature in the Classic toolkit:

    listeners: {
        resize: function (sender, width, height, oldWidth, oldHeight) {
            // was (element, info)
        }
    }

The onResize method is technically new but it can easily conflict with existing code that 
was wired to the resize event. Simply providing this method will now automatically set up 
the necessary resize monitoring. The signature also matches the Classic toolkit.

    onResize: function (width, height, oldWidth, oldHeight) {
        // resize event fires after this method is called
    }

### Ext.field.Text

#### placeHolder

This config was renamed to the proper case of `placeholder`. So `getPlaceHolder` and
`setPlaceHolder` and now also `getPlaceholder` and `setPlaceholder`, respectively.

### DataView

The internals of how dataviews create elements have changed considerably and this could 
impact CSS selectors and application code. In previous releases the DataView 
(already an Ext.Container) created a special type of child container to contain the 
actual data items. In 6.5 this extra level of nesting was removed. There is now only 
a pair of additional elements wrapping the data items (the inner for sizing and the 
outer for scrolling).

There are some configs that will help provide reliable selectors: 
[[modern:Ext.dataview.DataView#cfg-innerCls innerCls]] and 
[[modern:Ext.dataview.DataView#cfg-itemCls itemCls]]. Because dataviews (and lists and grids) 
can be nested inside each other, the innerCls can be very helpful for writing safe 
immediate child selectors:

    .my-inner-cls > .my-item-cls {

The API's to access to the contents of data view have been expanded to ensure that 
internal details like these do not affect applications going forward. For example, 
the [[modern:Ext.dataview.DataView#method-mapToRecord mapToRecord]] method can be 
called to convert all types of things (like events or elements) into the associate record.

#### useComponents

The `useComponents` config is replaced by `componentdataview` 
([[modern:Ext.dataview.Component]]). The config still works in some cases but code should 
be changed to create the desired type of dataview.

#### item\* events

Events like itemtap have been supplanted by childtap, and though the itemtap events are 
still supported they are deprecated. The new events allow for future-safe expansion and 
are more convenient in general.

    listeners: {
        itemtap: function (dataview, index, target, record, event) {
        },

        childtap: function (dataview, info) {
            if (info.record) { // and many other properties            
            }
        }
    }

The same childtap event will gain properties in derived classes, such as grids. This 
keeps the API clean and efficient instead of adding multiple families of events like 
`celltap`, `headertap`, `footertap`, `rowtap`, etc..

#### x-item-no-(tap/ripple/select)

These three class can be rendered by an itemTpl (or inside grid cells) and will adjust the 
response of the dataview to tap events.

#### selectable

The new [[modern:Ext.dataview.DataView#cfg-selectable selectable]] 
config replaces Ext.mixin.Selectable. The selectable config is used to configure an 
instance of [[modern:Ext.dataview.selection.Model]].

#### disableSelection

The [[modern:Ext.dataview.DataView#cfg-disableSelection disableSelection]] 
config has changed slightly such that it now only hides the selection state from 
the presentation.

### Component DataView

Even though [[modern:Ext.dataview.Component componentdataview]] is new to Ext JS 6.5, it 
is equivalent to a dataview that had set `useComponents:true`. The logic shared between 
the classes is in the Ext.dataview.Abstract base class.

#### defaultType

The defaultType now only applies to items added manually, not to rendered data items. To 
control the type of data items, use the xtype property of itemConfig.

### List

The [[modern:Ext.dataview.List]] class no longer extends `Ext.dataview.DataView`. Instead it extends 
`Ext.dataview.Component` which in turn extends `Ext.dataview.Abstract` so most of the 
results of the previous inheritance scheme are preserved. This would not include 
`instanceof`, naturally. The proper way to check this would be the `isDataView` property.

List inherits all of the same changes described above for DataView.

#### Positioned Items

Any (manually added) item that is positioned (has its left, top, right or bottom 
config set) will be rendered to the body element of the list and not inside the 
scrolling area. This is really helpful for things like floating action buttons but is 
still a change in behavior.

### Grid

Since Grid extends List, it also inherits the changes for List and DataView.

#### Columns

The [[modern:Ext.grid.HeaderGroup]] class is no longer necessary and has been removed. All 
columns can simply define a columns config and get child columns since the column 
component now extends [[modern:Ext.grid.HeaderContainer]].

#### columnresizing

This plugin is automatically included and no longer needs to be required or added to plugins.

### Pivot Grid

The Configurator's panelWrapper config has been removed. Instead set floated or 
docked on the panel config.

### Forms

#### Ext.form.Panel

The `updateRecord` method has been renamed to `fillRecord` due to an existing name conflict
with the record configuration on component.

The form panel class has some base functionality extracted out into a superclass. `Ext.field.Panel`
is the new base, which contains functionality for managing multiple fields and getting/setting
their value. The `Ext.form.Panel` class extends this by providing form submission logic. For those upgrading
existing applications, `Ext.form.Panel` has the same behavior, however the lighter-weight superclass
may be used if form submission functionality isn't required.

#### spinnerfield

The defaultValue config has been removed. Simply setting value will have essentially 
the same effect.

## Common

### ViewModels and Data Binding

#### Binding Algebra

There was a bug fix to the bind expression parser that could be viewed as a breaking 
change that has to do with the subtraction operator. Due to a bug in the regular 
expressions the following was treated as a single identifier:

    bind: '{foo-bar}'

This allowed "hyphenated names" to be given in some places. The expression parser now 
properly recognizes the above as a subtraction of bar from foo.

#### data

The behavior the set() and setData() methods has slightly changed as part of fixing some 
corner-case bugs. Instead of trying to describe these corner-cases, it is best to 
describe the expected behavior. To fully cover this area, consider a parent and child 
ViewModel:

    parent: {
        data: {
            x: 1
        }
    },
    child: {
        data: {
            y: 2
        }
    }

In this case the parent VM defined an "x" property and the child has added "y".

* set

    * child.set('x', 10);

        * Sets "x" in parent VM

    * child.set('y', 10);

        * Sets "y" in child VM

    * child.set('z', 10);

        * Creates new property "z" in child VM.

* setData

    * child.setData({ x: 10 });

    * child.setData({ y: 10 });

    * child.setData({ z: 10 });

        * All of these set (or create) a property in the child VM. If the parent VM has a 
        property by the same name (like "x") it is unaffected but now hidden.

* bind

    * child.bind('{x}').setValue(10);

        * Sets "x" in parent VM

    * child.bind('{y}').setValue(10);

        * Sets "y" in child VM

    * child.bind('{z}').setValue(10);

        * Creates new property "z" in child VM

To use an analogy, the data in a ViewModel is a lot like a JavaScript closure scope. The 
above arrangement would map to:

    function parent () {
        var x = 1;
        
        function child () {
            var y = 2;
        }
    }

The set method is like an assignment, so "child.set('x', 10)" is equivalent to assigning a
value to x in the child function:

    function parent () {
        var x = 1;
        
        function child () {
            var y = 2;
            x = 10;  // sets x in outer scope (parent)
        }
    }

The setData method, however, is like a var statement. So "child.setData({ x: 10 })" 
is equivalent to:

    function parent () {
        var x = 1;
        
        function child () {
            var y = 2;
            var x = 10;  // hides x from the outer scope
        }
    }

### Store

The `datachanged` event is now fired in conjunction with the `update` event to bring
this in line with other store events. `datachanged` can now act as a catch-all event.

### Charts and Draw

To better align the API's of the charts and draw packages with other framework 
components, there are a couple API changes that will affect all users.

* The highlight modifier's highlightStyle config has been renamed to style.

* The fx config of `Ext.draw.sprite.Sprite` has been renamed to animation.

### D3

The D3 library has been upgraded from version 3 to version 4 which carries with it 
breaking changes of its own. If you are using the components build on D3 then there are no 
changes to worry about, but if you are using D3 directly then upgrading will expose that 
code to D3's breaking changes. 

See [here](https://github.com/d3/d3/blob/master/CHANGES.md) for more information on 
these changes.

