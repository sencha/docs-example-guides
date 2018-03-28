# Components

Let's get started with Ext JS by covering the basics of components within the Ext JS framework.

    @example:extjs-6.5.0-material-modern
    Ext.Viewport.add({
        xtype: 'panel',
        html: 'Hello World!'
    });

This above code example probably looks pretty familiar. Let's go ahead and review what these things mean.

As you can see from our example, we're adding an object to something called Viewport (stay tuned). That object contains 
the following properties:

* xtype

* html

The "xtype" property is special in that it indicates the type of component we want to create. There are many values we 
could use for "xtype" other than "panel", such as "button" or "grid", but a panel is a good starting point. 

The type of component we are creating determines what other properties we can place in this object. These other 
properties are called "config properties" (or simply "configs") and are used to configure the component we have 
created. The properties correspond to the attributes we might put on an HTML element.

## Configs

Let's talk about component configurations!  

Every component has a collection of settable configuration properties.  These things can range from "title", "hidden", 
"modal"... as we've seen above.  Often, components will have the most common configurations defaulted to the most 
common values, but almost everything you see is configurable in any number of ways.

In our example, the `html` config is pretty straight-forward.  The value of the `html` config is added as the main 
content of our component (in this case, a `panel`).

### XTypes

xtype is a convenient alias that replaces fully qualified component names. For instance, "xtype: 'panel'" replaces 
'Ext.Panel".  This allows you to quickly create and render components by xtype, without having to remember (and type!) 
the full component name.

**Hint:** You can find xtype values on all of the component documentation pages.  Here's the 
[[modern:Ext.Panel panel documentation]].  You'll find a component's xtype right next to its name.

You can even create your own components with their own xtypes, but we'll get to that later.

## Viewport

You may have noticed that we're adding our panel to something called `Ext.Viewport`. `Ext.Viewport` is a specialized 
container that automatically sizes itself to the size of the browser viewport and conveniently manages the sizing and 
positioning of components that are added to the viewport.

## What's Next

Now that we've talked about the nuts and bolts of the Ext JS components, let's add a component to our panel as we 
delve into Ext JS Containers.

### Deep Dive

For more information about configs, check out our [Class System Overview](../core_concepts/classes.html).

[Go to Next Section](./containers.html)
