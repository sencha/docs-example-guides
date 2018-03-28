# Handling Events

Events are a powerful part of the Ext JS Framework. Events notify us that something has happened in our application. This 
notification can be emitted by any number of actions.

    @example:extjs-6.5.0-material-modern
    Ext.Viewport.add({
         xtype: 'tabpanel',
         items: [{
             title: 'Employee Directory',
             xtype: 'grid',
             iconCls: 'x-fa fa-users',
             listeners: {
                 itemtap: function() {
                     console.log('item tap!');
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

In this case, we are detecting when a grid row is tapped.

Using the grid's 'listeners' property, we have configured the grid to listen for and react to the 'itemtap' event. The 
grid will fire this event whenever an item is tapped (and also many other events as well), but without a listener, nothing 
happens. The listeners object can also be used to handle additional [[modern:Ext.grid.Grid#events grid events]]. 

**Hint:** In this example, we respond to the itemtap event by logging a message to the console.

## What's Next

Now that we're reacting to a user's interactions with a row of data, we'll take it a step further and display a form 
that will eventually bind with our record data.

### Deep Dive

For more information about events, check out our [Events Overview](../core_concepts/events.html).

[Go to Next Section](./data_forms.html)
