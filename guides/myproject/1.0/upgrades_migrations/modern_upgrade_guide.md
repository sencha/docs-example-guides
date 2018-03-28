# Upgrading from Touch 2.4.x to Ext JS Modern Toolkit

## Introduction

This guide walks through the most important changes and their potential impact on updating 
your Touch applications to the Ext JS modern toolkit.  There are many changes due to the 
modern toolkit sharing the core package, where Touch did not.  If you have used Ext JS 5+, 
you'll probably be familiar with most of the items in this guide.

If you are new to the Ext JS side of Sencha, you may want to review our notable additions 
in Ext JS 5 as many of these will apply to the modern toolkit in Ext JS 6.  In particular 
the additions and improvements to the core and charts packages are most likely relevant.

[What's New in Ext JS 5](http://docs.sencha.com/extjs/5.1/whats_new/5.0/whats_new.html)

[What's New in Ext JS 5.0.1](http://docs.sencha.com/extjs/5.1/whats_new/5.0.1/whats_new.html)

[What's New in Ext JS 5.1](http://docs.sencha.com/extjs/5.1/whats_new/5.1.0/whats_new.html)

## Sencha Cmd Upgrade Process

The first step in the upgrade process is to upgrade the `".sencha"` folder and other key parts
of your application. Run `sencha app upgrade` from your application root folder:

    sencha app upgrade ../path/to/ext6

Alternatively, you can generate a stock modern app and replace its `"app"` folder  with your
own:

    sencha -sdk path/to/ext6 generate app --modern YourAppName ./AppFolder

**Note:** Be sure to use your Touch application's App Name in place of `YourAppName` above.

## Browser Support

The following browsers are supported by the modern toolkit.  

### Desktop

 * IE11+
 * Firefox and Firefox ESR (Latest Versions)
 * Chrome (Latest Versions)
 * Safari 7+

### Mobile 

 * IE11+
 * Safari 7+
 * Android 4.0+ Chrome
 * Android 4.4+ Native

## Adding DOCTYPE and Meta Tags

We recommend the usage of the HTML5 doctype. We also recommend the X-UA-Compatible meta 
tag to ensure Internet Explorer does not activate "Compatibility Mode". The viewport
meta tag is necessary for mobile devices to prevent viewport zooming from interfering
with the framework's gesture recognition.

For example:

    <!DOCTYPE html>
    <html>
    <head>
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">

Omitting these tags may result in strange behavior and, potentially, a non-functioning
application.

## Distribution

There is now a Sencha Cmd package named "ext" which contains the framework.

The move to being a package means the build outputs are stored in a "build" folder. This 
folder is useful if you want to use Ext JS directly without Sencha Cmd.

The "packages" and "src" folders are used by Sencha Cmd applications to build only what 
your application requires.

## {theme}.js / {theme}.css

Themes may contain JavaScript overrides to tune default configs for some components. 
Generally, you'll need a script tag following "ext*.js" in order to include the JavaScript 
portion of a theme:

    build/modern/{theme}/{theme}(-debug).js

The `-debug` token is optional and, when present, selects the uncompressed JavaScript 
build of the theme overrides.

The compiled theme files are now present in the following folder off the root of the 
distribution:

    build/modern/{theme}/resources/{theme}-all(-debug).css

## Ext.ux

"User Extensions" are provided as a starting point in building useful components. They are 
often useable as-is, but are intended to serve as examples of how to go beyond the core 
framework. The "ux" content is basically the same as before but has been converted into an 
"ux" package. Add "ux" the "requires" array in `"app.json"`. If you are not using Sencha Cmd,
then you'll need to add the build outputs of the "ux" package found here:

    build/packages/ux/modern/ux(-debug).js
    build/packages/ux/modern/modern-neptune/resources/ux-all.css

The "ux" package only builds using the `theme-neptune` in the modern toolkit because it is
not sensitive to theme changes.

## Element

### Ext.dom.Helper

There is a minor change in DomHelper behavior with regards to generating HTML markup. For 
element attributes whose values are `undefined`, no attribute markup will be generated. When 
a valueless attribute is desired, use an empty string instead:

    el.createChild({
        tag: 'div',
        foo: '',
        bar: undefined
    });

The new DOM element will look like this: 

    <div foo=""></div>

### Ext.fly()

`Ext.dom.Fly` is now a separate class, and just like `Ext.dom.Element`, it should not be 
instantiated by calling the constructor. Always use `Ext.fly()` to retrieve a flyweight 
element instance. The major change in behavior for flyweight Elements is that you can no 
longer attach event listeners (addListener and removeListener raise errors in development 
mode). Always use `Ext.get()` to retrieve an Element instance if it will be used to attach 
event listeners. Using `Ext.get()` adds the Element to the internal Element cache which 
allows its listeners to be cleared upon destruction. While adding listeners to flyweight 
Elements was not previously recommended, it is now prohibited.

Another minor change to the behavior of `Ext.fly()` is that it will no longer allow text 
nodes to be wrapped, but will return `null` if a text node is passed. This was done for 
consistency with the behavior of `Ext.get()`.

### Element Selection Methods (select, query)

For better performance, we have changed the `select()` and `query()` methods to use 
`querySelector` or `querySelectorAll`, and have removed the `Ext.dom.Query` requirement. 
Developers who require the advanced selectors supported by `Ext.dom.Query` can use 
`Ext.dom.Query` directly.  You may also restore the old functionality of `Ext.dom.Element` 
`query()` and `select()` methods, using an override such as the this:

    Ext.define('Ext.ElementCompat', {
        override: 'Ext.dom.Element',
        requires: [ 'Ext.dom.Query' ],

        select: function(selector, composite) {
            var elements;

            if (typeof selector == "string") {
                elements = Ext.dom.Query.select(selector, this.dom);
            }
            else if (selector.length !== undefined) {
                elements = selector;
            }

            return composite ? new Ext.CompositeElement(elements)
                      : new Ext.CompositeElementLite(elements);
        }
    }, function(DQ) {
        Ext.query = function(selector, root, type, single) {
            return DQ.select(selector, root, type, single);
        };
    });

### Element Position Query

To provide better inspection of DOM element position, Ext JS allows querying the Left,
Right, Top, and Bottom of an element based on its local position and its absolute position.
Previously, `Element.getLeft()` would always return a local coordinate. In order to achieve
the same behavior, one will need to call `Element.getLeft(true)` to force the local
coordinate system. This also applies to `getRight`, `getTop`, and `getBottom`.

In Sencha Touch 2.x, the following `Ext.dom.Element` methods returned "local" coordinates
by default.  Local coordinates are relative to their `offsetParent`. In Ext JS 6, however,
these methods return "global" coordinates (relative to the page) by default:

 * getTop()
 * getRight()
 * getLeft()
 * getBottom()

Users may revert to using local coordinates by passing true as the first parameter to any
of these methods, for example: 
    
    myElement.getTop(true);
    
## Changes to platformConfig

To provide for more control over run-time configuration the `platformConfig` directive has
been overhauled to now work with `Ext.platformTags`. This is an object populated early in
the framework load process with various identifiers such as **phone**, **tablet**, **desktop**,
**ios** or **android** etc..

In Sencha Touch 2.x `platformConfig` was specified in the following syntax:

    platformConfig: [{
        platform: 'phone',
        theme: ['Windows'],
        itemHeight: 43
    },{
        theme: ['Cupertino'],
        itemHeight: 49
    }]

In Ext JS 6, `platformConfig` is now an object that uses expressions as keys. Whenever the
expression is true, those properties are applied. The expressions are implicitly based on
the properties of `Ext.platformTags`.

	platformConfig: {
		'phone && windows': {
			itemHeight: 43
		},
		ios: {
			itemHeight: 49
		}
	}

**Note:** The theme is not a tag available to `platformConfig`. If one wished to make the
theme (or other tag) available for `platformConfig` usage, it can be simply added using the
`tags` property in `"app.json"` (perhaps in a build profile):

	"builds": {
		"cupertino": {
			"toolkit": "modern",
			"theme": "theme-cupertino",

			"tags": "cupertino"  // added to platformTags for this build
		}
	}

Alternatively, applications can provide `Ext.beforeLoad()` which is given this object and
it is also valid to modify it if needed. Perhaps, to add a custom tag.

    <script type="text/javascript">
        var Ext = Ext || {}; // Ext namespace won't be defined yet...
        
        Ext.beforeLoad = function (tags) {
            // ... tags === Ext.platformTags 
            tags.custom = true;
        };
    </script>

## Theming

### iconCls / Pictos

The Pictos icon font is no longer included by default. It is now a separate package 
you'll need to require explicitly in `"app.json"` or `"package.json"` as appropriate:

	"requires": [
        "font-pictos"
    ]

Once required, you can use the following syntax for `iconCls` configs in order to use 
icons from the Pictos library:

	// pictos-{iconName} is used to set a named icon from the Pictos icon set
    iconCls: 'pictos pictos-home'

A similar requirement step and `iconCls` syntax will be used if you prefer to use icons 
from the new "font-awesome" package.

	"requires": [
		"font-awesome"
    ]

    // fa-{iconName} is used to set a named icon from the Font Awesome icon set
    iconCls: 'x-fa fa-home’

### Theming Upgrade

Creating custom themes in Touch is very different than how it's handled in Ext JS.  Any 
custom theme style rules that existed in your Touch Application will need to move into 
the appropriate folders.

See our [Theming Guide](../core_concepts/theming.html) for more information about theming Ext JS.

### Fashion

We are very excited to introduce our new theme compiler named Fashion. Fashion compiles
most Sass code (`.scss` files) but is in fact not Sass. It is an extended language with
additional features to improve use in tools like Sencha Inspector.

#### Dynamic Variables

When upgrading to Ext JS 6, the internal use of dynamic variables could impact how these 
variables are assigned in applications and custom themes. Although not necessary, it is 
recommended to change variable assignments to use `dynamic()`. In most cases, this will 
mean mechanically replacing `!default` (the approach taken in previous releases) with
`dynamic()`:

    // before:
    $base-color: green !default;

    // after:
    $base-color: dynamic(green);

This will make it more obvious if an error is generated based on the more restrictive 
nature of assignment to dynamic variables.

#### Compass Extensions

Compass functionality depending on Ruby code will be unavailable since Ruby is no longer 
being utilized. An equivalent will have to be created using JavaScript. This can be provided 
in many cases using `require()` to implement the missing functionality in JavaScript. The 
Sass code from Compass, however, is included in Fashion, so not all Compass functionality 
is impacted. Generally speaking, if you have not used any custom Compass functionality, 
you will most likely not need to make any changes.

See the [Fashion Guide](../../../cmd/6.x/fashion.html) for more information.

## Events

### Declarative Listeners

Previously, listeners declared on the class body would be merged at a property level with 
listener declarations on subclasses or instance configs. This could lead to surprising 
results should options like `delay` and `buffer` get merged.

Now, listeners declared on the class body will never be merged. Instead, listeners defined 
on subclasses, or in instance configs will be added to any existing listeners inherited 
from super classes and/or mixins. This enables listeners to be safely defined in a 
declarative manner.

In the following example all three listeners will be called:

    Ext.define('SuperButton', {
        extend: 'Ext.button.Button',

        listeners: {
            click: function() {
                console.log('button clicked (superclass handler)');
            }
        }
    });

    Ext.define('SubButton', {
        extend: 'SuperButton',

        listeners: {
            click: function() {
                console.log('button clicked (subclass handler)');
            }
        }
    });

    Ext.create('SubButton', {
        renderTo: Ext.getBody(),

        text: 'click me',

        listeners: {
            click: function() {
                console.log('button clicked (instance handler)');
            }
        }
    });

Users who were dependent upon the past behavior of declarative listeners that overrode 
their parent class's listeners will need to change their code to override the handler 
method instead.

### Updating "before" Event Listeners

Sencha Touch and Ext JS had different approaches to `before` and `after` events. In Sencha 
Touch, you might see code like this:

    listeners: {
        activeitemchange: 'onBeforeActiveItemChange',
        order: 'before'
    }

This listener would be called prior to the change of active item and could veto that 
change by returning false. In Ext JS, the above should be changed to:

    listeners: {
        beforeactiveitemchange: 'onBeforeActiveItemChange'
    }

This would also apply to many cases using onBefore directly:

    // Before:
    comp.onBefore('activeitemchange', 'onBeforeActiveItemChange', this);

    // After:
    comp.on('beforeactiveitemchange', 'onBeforeActiveItemChange', this);

The `after` event order and `onAfter` method, which is also deprecated, are similar but 
should function in much the same way as in Sencha Touch.

#### Details

In the core event system with Ext JS 6, the `order` option on listeners is deprecated 
and simply maps to a `priority` value to control the order of event listeners. While this 
preserves the ordering of listeners to an event, it does not have the expected result for 
`before` listeners in all cases.

This is particularly true when listening to events fired using 
[fireAction](http://docs.sencha.com/touch/2.4/2.4.1-apidocs/#!/api/Ext.mixin.Observable-method-fireAction) 
(the implementation that was behind [eventedConfigs](http://docs.sencha.com/touch/2.4/2.4.1-apidocs/#!/api/Ext.Evented)). 
In Sencha Touch, the one event ("activeitemchange" for example) would be fired to all 
"before" listeners. If none returned false, the action function would be called and then 
all remaining listeners would receive the event. To handle animations and the like, the 
event delivery would be suspended and resumed (typically by the action function).

With Ext JS 6, this is split into two events ("beforeactiveitemchange" and "activeitemchange") 
and the action function is called between the two events (if no "before" event listeners
returned false).

### Event listening 

Advanced listening features like listening directly on elements or components using 
wildcard and advanced selectors may not work the same.  Application level event handlers 
using controllers or viewControllers, however, will work the same.

## Scrolling

The `scrollable` config of `Ext.container` now configures an `Ext.util.Scroller` instead 
of an instance of `Ext.scroll.View`.

With many touch-enabled devices, special logic is needed to efficiently manage scrolling. 
To normalize all this device-specific behavior, we've added `Ext.scroll.Scroller`. An 
instance of this class is created by the framework when using configs like `autoScroll`, 
`overflowX` and `overflowY` configs, but it can now be more fully controlled using the new 
`scrollable` config.

This config can now be a config object for the Scroller. To retrieve the Scroller, you call 
`getScrollable()`. This object provides useful APIs like `scrollTo` and `scrollBy`, so you 
no longer need to worry about how the scrolling is managed on the current device.

The properties in a scrollable config object are transferred to configs of a `Ext.util.Scroller`.

Now you can use the preferable shorthand like so:

    scrollable: 'x'   // equivalent to 'horizontal'
    scrollable: 'y'   // equivalent to 'vertical'

## Data

The `Ext.data` namespace is perhaps the most impacted by the merge of Ext JS and Sencha
Touch.

### Ext.data.Model

The way to define models has changed to not require a config block, because they are
not instance level configurations:

    // Old
    Ext.define('Order', {
        extend: 'Ext.data.Model',
        config: {
            fields: ['id', {
                name: 'date',
                type: 'date'
            }],
            hasMany: 'OrderItem'
        }
    });

    // New
    Ext.define('Order', {
        extend: 'Ext.data.Model',
        fields: ['id', {
            name: 'date',
            type: 'date'
        }],
        hasMany: 'OrderItem'          
    });

The internals of `Ext.data.Model` have been heavily optimized to include support for 
calculated fields, better identity ("id" property) management, and undeclared fields.

This last item takes a bit of unpacking. Basically if the following are true for a field 
then that field no longer has to be listed in the fields array:

* Needs no conversion beyond deserialization (say from JSON)
* Has no default value
* Does not need to be validated (at the Model level)

#### Properties / Configs

* **data**: Undeclared model fields will remain intact where they were previously pruned 
in Touch. This allows Models to only define the fields that need to be processed in some 
way. The data object passed to the constructor simply becomes the `data` property and 
defaulting and conversions are applied in place.

* **raw**: Because of the changes to the data property, there is no longer a separate raw 
data property tracked on each record. Should your existing applications rely on this 
previously reader-generated property, you can approximate the old behavior during the 
transition with a simple override to copy the data before it is updated:

        Ext.define('App.overrides.data.Model', {
            override: 'Ext.data.Model',
            constructor: function (data) {
                this.raw = Ext.apply({}, data);
                this.callParent(arguments);
            }
        });

* **id / internalId**: When a record is created and no "id" is given, one will be 
generated. This is handled by the Model's `identifier` config. This is placed as `id` on 
the record (accessed using the `getId` method) as well as in the `data` object as the 
`idProperty`. Historically, the id would often be copied to the internalId. This is no 
longer the case. The `internalId` is a separately generated value that is unique across 
all records and should never be changed. The `id`, however, may be changed.

* **clientIdProperty:** `clientIdProperty` is now a config for writer that is used to 
rename "id" as it is sent to the server for create operations. If now present, the 
generated "id" will be sent. The server's response is used to send back the server-generated 
id as needed. The id sent to the server is read back using the existing `clientIdProperty` 
on Model. When using a Session, the "foreign key" fields of all associated records will be 
updated, if maintained within the same session.

* **modified:** `Ext.data.Model` previously returned an empty object for the modified 
property if no records had changed. Accessing the Model's `modified` property will now 
return `undefined` if no changed records have been appended. Changes such as these allow 
the Data package to remain as slim as possible.

* **useCache:** Sencha Touch gave users the ability to cache model instances by defining 
their models with the `useCache` config. This was replaced by `Ext.data.Session` to allow for better 
scope control over the cache.  Alternatively, developers can load records via 
ViewModel and share it in that manner.

Users should now utilize the model's "modified" methods to ascertain change. These include:

* **isModified**()

* **getModified**()

* **getChanges**()

* **belongsTo**: `belongsTo` can often be simplified using the `reference` config on field.

* **hasMany**: The typical use of `hasMany` is deprecated in favor of `reference` config 
on field. See below. Use of `hasMany` to describe child items that do not contain a
foreign key is still appropriate.

* **associations**: Same as above since this config is just an alternative way of 
expressing `belongsTo` and `hasMany`.

* association data will not be read via the model constructor, this will need to be parsed
by a reader:
    
        var results = MyModel.getProxy().getReader().read(rawData);

* **validations**: validations are supported but deprecated for creating validators associated 
with a single field. Instead, use the `validators` config object which is keyed by field name.

##### **Methods**

* **constructor**: To construct a record, you simply pass the data object. The second 
argument is the owning `Ext.data.Session` (see below).

* **drop**: There is now a `drop` method that marks the record to be removed, but does not 
save it immediately. 

### Ext.data.Store

There are several internal changes to stores in Ext JS 6. Many are inherited from Sencha 
Touch and others are to support chained stores.

#### Events

The `addrecords`, `removerecords` and `updaterecords` events now become `add`, `remove` and
`update` respectively. The `add` and `remove` events may be fired multiple times for a single
operation, an event will be fired for each contiguous block of records.

    // This will cause 2 remove events to be fired, one for each block of records
    var records = [0, 1, 4, 5, 6, 9, 10, 12].map(function(idx) {
        return store.getAt(idx);
    });
    // Fires 4 remove events:
    // 0..1
    // 4..6
    // 9..10
    // 12
    store.remove(records);

**datachanged event:** In some cases, previous Sencha Touch 2 releases did not always fire 
this event consistently. Ext JS now assures that this event is raised for all manual bulk 
load methods such as `loadData`, `add`, or `insert`. Note that this event is not raised 
initially when a store is instantiated with inline `data: [ ]`.

#### Added

**beginUpdate / endUpdate:** These methods can be called before making multiple changes to 
a store and after. These translate to new `beginupdate` and `endupdate` events as these 
transition an internal update counter from or back to 0. This allows views observing the 
store to defer expensive operations out to the `endupdate` event.

#### Changed

**getById / getByInternalId:** In Sencha Touch 2, only `getByInternalId` was a map lookup, 
and since `internalId` was not always the same as id, applications needed to call `getById`. 
In Sencha Touch 2, that was a linear search, but both are backed by maps.

**Note:** TreeStore's `getById` method will only search nodes that are expanded 
(all ancestor nodes are expanded: true -- isExpanded)

**destroy / destroyStore**: In Sencha Touch 2, the "destroy" method was used to send a 
remote request to the server to delete records. This conflicts with the common usage of 
"destroy" across the framework to mean to clean up resources. To bring this in line, the 
"destroy" method now cleans up a store. To send a delete request to the server, the "erase" 
method (same as model) should be used. "destroyStore" is deprecated.

#### Deprecated / Removed:

**"buffered" config:** The `buffered` config is supported for Ext.create and operator new, 
but is deprecated. It is recommended to create a buffered store using `type: 'buffered'`. 
If you are deriving a store from `Ext.data.Store`, the `buffered` config is not supported. 
Instead derive from `Ext.data.BufferedStore`. Here's an example of a grid store config:

    store: {
        type: 'buffered',  // was "buffered: true",
        ...
    }

**groupers:** Support for multiple grouping levels was never realized in Sencha Touch 2 
and groupers was really nothing more than extra sorters. This has been replaced by the 
`grouper` config and the `getGroupString` method that was previously configured on the 
store is now configured on the `grouper`. The internal structures are now much closer to 
being able to support nested groupers and this config will most likely be restored when 
that functionality is available.

### Ext.data.Proxy

`Ext.data.Operation` has now been split into four subclasses, one for each type of CRUD 
operation. These operation classes should be used in favor of `Ext.data.operation.Operation` 
directly.

#### Proxy

* **"destroy" / "erase"**: Similar to `model` & `store`, the `destroy()` method has been 
corrected to mean clean up any resources. To send a delete request to the server, the 
`erase` method should be used.

* "**doRequest**": Now takes a single argument, an `Ext.data.operation.Operation`. Callbacks 
should be attached to operation directly.

##### Proxy CRUD

One could previously pass a callback and scope into proxy CRUD methods. This has been 
removed. The callback from the proxy would return the operation where now one would use a 
callback on the operation which returns the results instead.

#### Writer

* **writeAllFields**: The default for this config was true and is now false to optimize 
data transfer. This config is used to tell the Writer to send all fields on an update 
even if those fields have not changed.

### Ext.data.Field

One of the biggest changes to fields is that the various field types are now defined as 
classes in a small class hierarchy `Ext.data.field.*`. Now you can write custom field 
types and use them in your Models by simply giving them an alias (for example, `data.field.foo`) 
and using that name as the type config on a field (for example, 'foo').

* **depends**: You can now declare the field names that a `convert` function uses to 
calculate its value and this field will automatically be updated whenever any of these 
fields are set.

* **calculate**: This new config allows you to write a simple function that produces the 
value of a field given the record's data object. Instead of declaring a `convert` function 
and the `depends` array, this text of this function is parsed to extract the field dependencies.

* **reference**: To make it simple to relate one Model with another, when a field contains 
the id of another record (a "foreign key"), you can add this config and simply give the 
name of the Model being referenced. This is enough to populate association data for both 
this Model and the referenced Model.

* **validators**: This config is typically used when deriving a custom field type, but this 
is an easy way to list the rules that describe a valid field value.

* **useNull**: This config is now named `allowNull`.

The ability to derive custom field types replaces the `Ext.data.Types` static class, which 
has been deprecated.

### Ext.data.Validations 

Has been replaced by `Ext.data.validator.*`. 

## Sessions (NEW)

The new Session class will help manage editing of multiple records and their associations. 
If you are manually saving records and stores and have to work out the proper sequence to 
save all of your edits, the Session class will likely be very helpful. Check out the API 
documentation on `Ext.data.Session` to determine if you might benefit from coordinated 
Model management.

## Schema (NEW)

Collecting and managing all of your Model definitions and their associations is now handled 
by the Schema class `Ext.data.schema.Schema`. The Schema class knows, for example, when one 
class declares an association with another and ensures that both classes are "decorated" 
with appropriate accessor methods - regardless of the order in which those classes are loaded.

## ModelManager (DEPRECATED)

The `Ext.data.ModelManager` class is deprecated. Its features have been replaced by 
`Ext.data.schema.Schema`.

## Associations

The way you declare associations has been streamlined. The old syntax is supported but, in 
many cases, field's new "reference" config makes the declaration much simpler. Further, 
Ext JS now supports "Many-To-Many" associations using the `ManyToMany` Model config.

## Ext.data.association.* (REPLACED)

The contents of this namespace have been replaced by Schema. Direct use of these classes 
in applications is rare and the configs that corresponded to these classes ("belongsTo", etc) 
are still supported though most deprecated.

## Ext.plugin.BufferedList 

We have removed `Ext.plugin.BufferedList`.  Please use `infinite: true` on list instead.

## mainView

Using `mainView` is the preferred way to launch your application.  While you can still utilize 
the launch method, it's more tool friendly to use `mainView`.

The `mainView` config can, however, conflict with a "Main" view listed in the `views` array:

    views: [
        'Main'   // generated getter conflicts with mainView config getter
    ]

To resolve this conflict, you can:

 - Switch the Main view to be created via the `mainView` config.
 - Rename the Main view.
 - Remove the "Main" entry in the `views` array (and check calls to `getMainView`).

## Viewport

Previously in Touch the Viewport was available at the time of `onReady`. ExtJS 6+ now has 
an event that fires when the Viewport is ready.

    Ext.on('viewportready', cb);

Using the `viewportready` event will allow users to access the viewport as soon as it is 
created from anywhere in there application.

## Removed Ext.DateExtras

The `Ext.DateExtras` singleton class has been removed.  Most of the methods found in 
`Ext.DateExtras` can be found in `Ext.Date` instead.

## Ext.data.plugin.Buffered has been removed

Use `Ext.data.BufferedStore`. At present, `Ext.data.BufferedStore` may not support Create, Write
and Delete operations. However, we are in process of making modern components accept BufferedStores.

## Legacy Package

We have created a legacy package that contains no longer supported code 
(like `Ext.device.*`, see below). The intent of the legacy package is to give users a chance 
to update their code before the code they may have used is completely removed.

### Ext.device.* API have been moved to legacy package

We have removed the Sencha Touch device API's from the modern toolkit, but they can still 
be utilized by requiring the legacy package.  While `Ext.device.*` can still be used, we 
recommend using native HTML5 API's or, for native packaged applications, Cordova or 
PhoneGap APIs are the preferred method of providing native device support.

## Ext.data.proxy.Sql has been removed

`Ext.data.proxy.Sql` was based on webSQL, which is no longer being developed.  Additionally, 
it's only supported in webkit browsers.  

## Charts Package

### Ext.draw.Component

`Ext.draw.Component` has changed to `Ext.draw.Container`.

## Instance IDs

As part of our performance optimization efforts in Ext JS 6, we have removed the overhead 
for handling identifiers with invalid characters from certain core areas. To help catch 
such ids before they fail, we have added checks in key places such as `Ext.get()` and the 
`Ext.Component` constructor. These checks use `Ext.validIdRe`, which is defined as:

    validIdRe: /^[a-z_][a-z0-9\-_]*$/i

In a nutshell, create ids that adhere to the above regex in order to future-proof your 
application.

## Ext.ComponentManager

`Ext.ComponentManager` is seldom used directly by applications, but its internals have been 
streamlined and it no longer provides a HashMap of components. Instead look at the methods 
this class provides to access the registered components.

## Ext.Container

`Ext.Container` API has been changed to be more consistent with `Ext.container.Container` API
in Classic toolkit. The changes include:

* When calling `add` method with multiple items to add, the return value will be an array
of `Ext.Component` instances that were added to the Container.
* `remove` method accepts three types of item selectors: an `Ext.Component` instance,
`itemId` of a child Component, or numeric index of the child Component in the `items`
collection.
* `remove` method will return the removed item instead of `this`.
* `removeAll` method will return an array of removed items instead of `this`.
* `removeAt` method will return the removed Component instead of `this`.
* `removeInnerAt` method will return the removed Component instead of `this`.

## Ext.mixin.Selectable (affects Ext.dataview.DataView, Ext.List, Ext.grid.Grid & subclasses)

The `getSelection` method now returns a single record, the most recently selected one. This can be
used for databinding:

    {
        xtype: 'formpanel',
        items: [{
            xtype: 'textfield',
            bind: '{theList.selection.name}'
        }]
    }

Use `getSelections` to return an `Ext.data.Model[]` that has all selected records.

## Forms

### Ext.field.Text (and subclasses)

The `change` event now fires immediately as the input changes, instead of when the field blurs. 
To have a delay to capture multiple change events in succession, use a buffer on the listener:

    listeners: {
        // Each time the change occurs, it will wait 500ms. If no other change has happened in
        // that period, the event will fire. Otherwise, if a change does happened, the timer will
        // be reset and the process will repeat
        buffer: 500, 
        change: function() {}
    }

### Ext.field.Checkbox

The `check` and `uncheck` events no longer pass the event object as it was only available under
some circumstances, the event was fired whether the change occurred via the UI or not.

### Ext.field.DatePicker, Ext.field.Select

This class no longer extends `Ext.field.Select`, the picker related functionality has been
abstracted into `Ext.field.Picker`, both of these classes now extend `Ext.field.Picker`.

### Ext.field.SingleSlider

This class has been introduced to assist with data binding. It is very similar to the superclass, 
`Ext.field.Slider`, however the `getValue` method and `value` binding always return a `Number`, not
a `Number[]`.

### Ext.field.Slider

The `change` event is now consistent with other form fields, the the signature is now:

    change: function(field, newValue, oldValue) {}

What was previously the `change` event is now named `dragchange`. 

A new `liveUpdate` config was added to determine when the `change` event fires, either real time
as the slider is modified, or when the drag is complete.

### Ext.field.Toggle

The type of `value` for this field is now a Boolean. It will still accept numeric values.

## Misc

### Ext.util.Draggable

To veto a drag, listen to the `beforedragstart` event and return false. In previous versions this would
be done in the `dragstart` event.

## Conclusion

As you can see, there are many new additions for users moving from Touch to the Modern 
toolkit.  As always, if you have questions regarding guide content, be sure to ask on the 
[community forums](https://www.sencha.com/forum/) or by submitting a Support ticket 
through the [Support Portal](https://support.sencha.com) 
([Sencha Support customer](http://www.sencha.com/support/) access only).

