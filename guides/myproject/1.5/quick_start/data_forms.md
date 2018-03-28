# Data Forms

Displaying data in a form is an excellent way to allow users to view and modify record values.  In this portion of the 
example, we're going to react to a row tap by displaying a form.  We will eventually populate this form with data 
from our record.

    @example:extjs-6.5.0-material-modern
    Ext.Viewport.add({
        xtype: 'tabpanel',
        items: [{
            title: 'Employee Directory',
            xtype: 'grid',
            iconCls: 'x-fa fa-users',
            listeners: {
                itemtap: function() {
                    Ext.Viewport.add({
                        xtype: 'formpanel',
                        title: 'Update Record',
                        floating: true,
                        centered: true,
                        width:300,
                        modal: true,
                        items: [{
                            xtype: 'textfield',
                            name: 'firstname',
                            label: 'First Name'
                        }, {
                            xtype: 'toolbar',
                            docked: 'bottom',
                            items: ['->', {
                                xtype: 'button',
                                text: 'Submit',
                                iconCls: 'x-fa fa-check',
                                handler: function() {
                                    this.up('formpanel').destroy();
                                }
                            }, {
                                xtype: 'button',
                                text: 'Cancel',
                                iconCls: 'x-fa fa-close',
                                handler: function() {
                                    this.up('formpanel').destroy();
                                }
                            }]
                        }]
                    });
                }
            },
            store: {
                data: [{
                    "firstName": "Jean",
                    "lastName": "Grey",
                    "officeLocation": "Lawrence, KS",
                    "phoneNumber": "(372) 792-6728"
                }, {
                    "firstName": "Philip",
                    "lastName": "Fry",
                    "officeLocation": "Lawrence, KS",
                    "phoneNumber": "(318) 224-8644"
                }, {
                    "firstName": "Peter",
                    "lastName": "Quill",
                    "officeLocation": "Redwood City, CA",
                    "phoneNumber": "(718) 480-8560"
                }]
            },
            columns: [{
                text: 'First Name',
                dataIndex: 'firstName',
                flex: 1
            }, {
                text: 'Last Name',
                dataIndex: 'lastName',
                flex: 1
            }, {
                text: 'Phone Number',
                dataIndex: 'phoneNumber',
                flex: 1
            }]
        }, {
            title: 'About Sencha',
            iconCls: 'x-fa fa-info-circle'
        }]
    });

In this example, we react to a row tap by displaying a form panel.  We've configured this form panel to be modal, 
centered, floating, and be 400px wide.

We've also given this form two items.  First, let's talk about the textfield.

## Fields, Values, and Labels

You'll likely see some very familiar words as you start working with form fields.  Take this code snippet from 
our example:

    items: [{
         xtype: 'textfield',
         name: 'firstname',
         label: 'First Name'
    }]

You may be more familiar with this in the following form:

    <label for="firstname">First Name</label>
    <input type="text" name="firstname">

As you can see, our textfield object bears strong resemblance to what you would see in the raw HTML element in 
its native form.

Now that we've talked about the form field, let's talk about the toolbar housing our buttons.

## Popup Forms & Toolbars

Toolbars are handy containers that can be docked within their respective containers.  In this example, our toolbar 
contains two buttons and is docked to the bottom of our form panel.  By default, items in a toolbar are in an "hbox" 
layout, which will arrange the components horizontally.

Layouts are a very powerful part of the Ext JS framework. They actively manage the positioning of items in a 
container.  In this case, as the toolbar has an "hbox" layout, items are stacked horizontally.  There are many other 
types of layouts, but we're just touching the surface in this guide.  

**Hint**: To learn more about using layouts in your application, see the [Layout Guide](../core_concepts/layouts.html).

You may also notice that our buttons contain a handler with a bit of code.  A button handler is just a shortcut 
configuration for a listener for the tap event.  In this case, our button handlers are set up to simply close the 
modal form when a button is tapped.  

You probably haven't see the "up" syntax yet.  What we're saying is that we want to start at whatever component we are 
scoped to (in this case, the button that was clicked) and travel "up" our component's hierarchy (think about 
"parents" and "children") until we find a component with an xtype of "formpanel".   Then, once we find the form panel, 
we use its destroy method to close the window.

**Note:** The button handlers aren't currently doing anything except closing the panel.  This is placeholder behavior
until we need to modify its behavior further.

## What's Next

Now that we have our form in place, let's bind our data to the form so that we can more easily view and change the data.

### Deep Dive

For more information about forms, check out our [Forms Overview](../components/forms.html).

[Go to Next Section](./data_binding.html)
