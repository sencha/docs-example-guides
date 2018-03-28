# Containers

In this section, we're going to turn our panel into a [[modern:Ext.tab.Panel tabpanel]] and talk about containers! Containers are components 
designed to own and manage a collection of child components.

    @example:extjs-6.5.0-material-modern
    Ext.Viewport.add({
        xtype: 'tabpanel',
        items: [{
            title: 'Employee Directory',
            iconCls: 'x-fa fa-users'                
        },{
            title: 'About Sencha',
            iconCls: 'x-fa fa-info-circle'
        }]
    });

You may remember that our previous example had two configs, xtype and html.  You can see above that we've:

1. Turned our [[modern:Ext.Panel panel]] into a [[modern:Ext.tab.Panel tabpanel]] by updating the xtype value to tabpanel.

2. Replaced our placeholder html "hello world!" with an array of objects called "items".

We can easily add "items" to a container by using the items array. You can think of items as "children" of the component 
to which you're adding them. In this case, the `items` array contains two objects.  The configuration that will create 
our tabs.

**Hint:** You would normally set an `xtype` for each item, but some containers (including tabpanel) have default 
xtypes for their children. For tabpanel, the default child xtype is 'panel'.

In addition to adding our tabs as items of our tabpanel, we've also added a `title` and an `iconCls` for each which 
affects each tab as follows: 

### title

The title will be the text that appears on the tab itself.

### iconCls

The iconCls config is a convenient way to assign an icon based on your font classes. In this case, we're using Font 
Awesome iconography that comes packaged with the theme.

**Hint:** Take a look at the [[modern:Ext.tab.Tab tab class]] to see all of the configs you can use to customize your 
tab. You may notice that this class is marked as private. That doesn't mean you can't use the members of the class, just 
that you shouldn't manually create a tab itself.

## What's Next

Empty tab panels aren't very useful, so let's add a grid so that we can present some data!

### Deep Dive

For more information about containers, check out our [Component Overview](../core_concepts/components.html).

[Go to Next Section](./presenting_data.html)
