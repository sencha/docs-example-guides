# Using Carousels

[[modern:Ext.carousel.Carousel Carousels]] are a great way to allow users
to swipe through multiple full screen pages.

A Carousel shows only one of its pages at a time, but allows you to browse through other
pages using a swipe gesture. You can think of a Carousel as a single active item, with the
rest of the items stretching away left and right. Indicator dots visualize how many
available screens are available to swipe through, as shown in the following image:

<img src="images/carousel.jpg"/>

Carousels can be oriented either horizontally or vertically and are easy to configure -
they just work like any other Container component. The following code sample shows how to
set up a simple horizontal Carousel:

    @example:extjs-6.2.0-material-modern
    Ext.create('Ext.Carousel', {
        fullscreen: true,

        defaults: {
            styleHtmlContent: true
        },

        items: [
            {
                html : 'Item 1',
                style: 'background-color: #5E99CC'
            },
            {
                html : 'Item 2',
                style: 'background-color: #759E60'
            },
            {
                html : 'Item 3'
            }
        ]
    });

Swiping your finger left and right over the carousel swaps between the two items defined
above. It also updates the indicator icon to let you know which page you are currently on.
We can also make Carousels orient themselves vertically, as shown in the following code
sample:

    @example:extjs-6.2.0-material-modern
    Ext.create('Ext.Carousel', {
        fullscreen: true,
        direction: 'vertical',

        defaults: {
            styleHtmlContent: true
        },

        items: [
            {
                html : 'Item 1',
                style: 'background-color: #759E60'
            },
            {
                html : 'Item 2',
                style: 'background-color: #5E99CC'
            }
        ]
    });

You can place any component into a Carousel, for example the following code places a list
and a form into a horizontal carousel:

    @example:extjs-6.2.0-material-modern
    Ext.create('Ext.Carousel', {
        fullscreen: true,

        items: [
            {
                xtype: 'list',

                items: {
                    xtype: 'toolbar',
                    docked: 'top',
                    title: 'Roster'
                },

                store: {
                    fields: ['name'],
                    data: [
                        {name: 'Jon'},
                        {name: 'Sansa'},
                        {name: 'Arya'},
                        {name: 'Robb'},
                        {name: 'Bran'},
                        {name: 'Rickon'}
                    ]
                },

                itemTpl: '{name}'
            },
            {
                xtype: 'fieldset',
                items: [
                    {
                        xtype: 'toolbar',
                        docked: 'top',
                        title: 'Login'
                    },
                    {
                        xtype: 'textfield',
                        label: 'Name'
                    },
                    {
                        xtype: 'passwordfield',
                        label: 'Password'
                    }
                ]
            }
        ]
    });
