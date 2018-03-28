# Getting Organized

Ext JS encourages users to utilize a structured application architecture. In our example, we're using an MVC 
(Model/View/Controller) approach. This helps us keep our application's data, logic, and views described within 
separate silos.

    Ext.define('Employees', {
        extend: 'Ext.data.Store',
        alias: 'store.employees',
    
        data: [{
            "firstName": "Jean",
            "lastName": "Grey",
            "officeLocation": "Lawrence, KS",
            "phoneNumber": "(372) 792-6728"
        }, {
            "firstName": "Phillip",
            "lastName": "Fry",
            "officeLocation": "Lawrence, KS",
            "phoneNumber": "(318) 224-8644"
        }, {
            "firstName": "Peter",
            "lastName": "Quill",
            "officeLocation": "Redwood City, CA",
            "phoneNumber": "(718) 480-8560"
        }]
    });
    
    Ext.define('PopupForm', {
        extend: 'Ext.form.Panel',
        xtype: 'popupform',
        controller: 'popupform',
    
        title: 'Update Record',
    
        width: 300,
        floating: true,
        centered: true,
        modal: true,
    
        items: [{
            xtype: 'textfield',
            name: 'firstname',
            label: 'First Name',
            bind: '{employee.firstName}'
    
        }, {
            xtype: 'toolbar',
            docked: 'bottom',
            items: ['->', {
                xtype: 'button',
                text: 'Submit',
                iconCls: 'x-fa fa-check',
                handler: 'submitUpdate'
            }, {
                xtype: 'button',
                text: 'Cancel',
                iconCls: 'x-fa fa-close',
                handler: 'cancelUpdate'
            }]
        }]
    });
    
    Ext.define('PopupFormController', {
        extend: 'Ext.app.ViewController',
        alias: 'controller.popupform',
        
        cancelUpdate: function () {
            var view = this.getView();
            
            view.destroy();
        },
        
        submitUpdate: function(me) {
            var view = this.getView();
            
            view.destroy();
        }
    });
    
    
    Ext.define('MyListViewController', {
        extend: 'Ext.app.ViewController',
        alias: 'controller.listview',
        
        onPopupForm: function (view, index, item, record) {
            Ext.Viewport.add({
                xtype: 'popupform',
                width: 400,
                record: record,
                viewModel : {
                    data: {
                        employee: record
                    }
                }
            });
        }
    });
    
    Ext.application({
        name: 'Fiddle',
    
        launch: function() {
    
            Ext.Viewport.add({
                xtype: 'tabpanel',
                controller: 'listview',
                
                items: [{
                    title: 'Employee Directory',
                    xtype: 'grid',
                    iconCls: 'x-fa fa-users',
                    listeners: {
                        itemtap: 'onPopupForm'
                    },
                    store: {
                        type: 'employees'
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
    
        }
    });

[View the Example](https://fiddle.sencha.com/#fiddle/1dma)

## MVC

In an MVC architecture, most classes are either Models, Views, or Controllers. The user interacts with Views, which may 
display data held in Models. Those interactions are monitored by a Controller, which then responds to the interactions 
by updating the View and Model, as necessary.

The goal of MVC is to clearly define the responsibilities for each class in the application. Because every class has 
clearly defined responsibilities, they become decoupled from the larger environment. This makes the app easier to 
test and maintain, and its code more reusable.

## Classes and Inheritance

We have switched from simply creating components to defining new classes of components using the Ext.define method. These 
classes inherit the bulk of their functionality by virtue of their "extend" property which specifies their desired base 
class. The class we choose to extend is the same as we had previously been creating.

As you can see, we're using extend in our class definitions.  This is a method of creating your own class that inherits 
all of the methods, properties, and config options from the class you're extending.

All Ext JS components inherit attributes from the Component class. That means that Component has certain abilities that 
are passed down to all visual components in the Ext JS framework.

As an example, TabPanel gets to use all of the abilities from Component, Container, and itself because TabPanel extends 
Container, and Container extends Component. This is called the inheritance chain. It's not something that you have to 
fully understand, but it's important to recognize its existence since it gives your visual components all of the 
superpowers that exist in its hierarchy.

## What's Next

In the next section, we'll add more functionality and real-world data, so that our application is ready for realistic 
use cases.

### Deep Dive

For more information about application architecture, check out our 
[Application Architecture Overview](../application_architecture/application_architecture.html).

[Go to Next Section](./bringing_it_together.html)
