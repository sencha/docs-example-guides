# Presenting Data

One of the most powerful features of Ext JS is data-driven components, such as the grid. By connecting components to 
data sources, you can create dynamic applications that change as the data in your application changes.

You can feed data to Ext JS components in many different ways. One way is to simply inline the data:

    @example:extjs-6.5.0-material-modern
    Ext.Viewport.add({
        xtype: 'tabpanel',
        items: [{
            title: 'Employee Directory',
            xtype: 'grid',
            iconCls: 'x-fa fa-users',
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

As you can see in the above example, we've added a grid as our first tab.  The Ext JS grid is a powerhouse of 
functionality that can be created with very few lines of code.  It translates data into a grid containing rows and 
columns that have built-in sorting, along with a bevy of other plug-and-play functionality such as grouping, 
filtering, etc. 

## Stores

You may notice that our grid has a new config - 'store'. Ext JS stores are the things that house all of your data 
records.  Stores are powerful for data processing.They can easily sort, filter, and query the data stored in them.

In most cases, your store's data will come from an external source such as a database or REST API.  However, for our 
purposes, we're just hard-coding records onto our store's data config.

**Hint:** There are a variety of stores you can choose from.  These allow you to use different types of formatted data 
depending on your needs.

## Records

Records are individual entities composed of fields, much like you would structure records in a database table.  Records 
can contain many different fields that can each be cast as different data types (int, float, string, etc).  However, Ext 
JS generally casts the fields appropriately by default.

## Fields

In this example, our records contain four fields.  These fields are:

* firstName

* lastName

* phoneNumber

* officeLocation

In our grid, we have three columns configured with a `dataIndex`.  The dataIndex tells the column which record field is 
to be used for the displayed value of that column.

## What's Next

Now that we can see our data, let's explore how we can react to events when we tap or click our grid's rows.

### Deep Dive

For more information about data, check out our [Data Overview](../core_concepts/data_package.html).

[Go to Next Section](./handling_events.html)
