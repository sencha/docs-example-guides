# Data Binding

Binding for components is the process of connecting data to a component's configs. This allows changes in our data to 
automatically update the associated component's config properties. In some cases, these configs can be manipulated by 
the end-user, such as the value of a textfield. These properties are, by default, "two-way" bound such that these 
changes to the config property update the bound data.

Any component configuration can use binding as long as it has a setter method. In this case, we're binding our record's 
firstName field to our textfield's value (default for textfield binding).

    @example:extjs-6.5.0-material-modern
    Ext.Viewport.add({
        xtype: 'tabpanel',
        items: [{
            title: 'Employee Directory',
            xtype: 'grid',
            iconCls: 'x-fa fa-users',
            listeners: {
                itemtap: function(view, index, item, record) {
                    Ext.Viewport.add({
                        xtype: 'formpanel',
                        title: 'Update Record',
                        width: 300,
                        floating: true,
                        centered: true,
                        modal: true,
                        
                        record: record,
                        viewModel : {
                            data: {
                                employee: record
                            }
                        },
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

All of this binding is possible by virtue of our ViewModel.

A ViewModel is a class that manages a data object. It then allows those interested in this data to bind to it and react 
when it changes. The ViewModel is owned by the view that defines it. Because ViewModels are associated with a view, its 
child views simply "inherit" the data of their parent's ViewModel.

In the above example, our textfield's value is bound to the value passed from our selected record.  If you change the 
value in the form field, it will also change the value in the selected record, and the changes will be reflected in 
the row.

## What's Next

As you can see, our code is getting a little unruly. In the next section, we'll talk about organizing our application's 
code structure for readable and scalable applications.

Let's talk about Application Architecture!

### Deep Dive

For more information about data binding, check out our 
[Data Binding Overview](../application_architecture/view_models_data_binding.html).

[Go to Next Section](./getting_organized.html)
