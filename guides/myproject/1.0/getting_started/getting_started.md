# Getting Started 

Getting started with Ext JS 6 and Sencha Cmd 6 couldn't be easier.  With a single command, 
you'll have a fully functional "universal" starter application that can be run on a 
local web server. 

A "universal" application contains a core set of stores, models, and controllers,
while presenting two different sets of views by way of the two toolkits: Classic, and Modern.

The Classic toolkit contains the traditional pieces of the Ext JS codebase that supports 
legacy browsers, tablets, and touch screen laptops. The Modern toolkit contains a 
touch-friendly codebase that supports modern browsers, tablets, and phones.

Let's get started!

1. [Download and Install Sencha Cmd 6](http://www.sencha.com/products/sencha-cmd/)

2. [Download and unzip the Ext JS SDK](http://www.sencha.com/products/extjs/evaluate/)

2. Open your terminal or console window and issue these commands:  

		sencha -sdk /path/to/extjs/framework generate app AppName path/to/app
		cd /path/to/app
		sencha app watch

**Note:** For the purposes of this walkthrough, AppName will be MyApp and path/to/app 
will be ./MyApp.

That's it.  You've created an application and deployed a server.  Now navigate to
[http://localhost:1841](http://localhost:1841) or your native localhost.  You can now view
your newly generated Ext JS 6 application.  

Sencha Cmd is now monitoring your application for changes. You will see _"Waiting for
changes..."_, which is an indication that your application is up to date. As you make
changes and save files you will see other messages printing, but these will end shortly
with another _"Waiting for changes..."_ message. This cycle usually takes a few seconds,
so be sure to allow enough time between file saves and hitting Reload in your browser.

**Note:**  _If `sencha app watch` fails to pick up your changes for any reason, 
you can simply stop (CTRL + c) and restart app watch._

**Note:** _If you're curious about what the above steps entail, you may want to check out
our [Introduction to Sencha Cmd Guide](../../../../cmd/guides/intro_to_cmd.html)._

## Next Steps

As mentioned above, Universal applications are made up of three important areas:

 + Shared app area (most suitable for stores, models, and controllers).  This area can
 be found in the `app` folder in your application's root.
 + Classic app area (views and logic specific to the classic aspect of your application).  This
 area can be found in the `classic/src` folder in your application's root.
 + Modern app area (views and logic specific to the modern aspect of your application). This
 area can be found in the `modern/src` folder in your application's root.

It should be noted that this small application illustrates a huge number of features in Ext JS.  There
is not enough space to discuss everything in-depth, so we will do a small overview for the
pertinent bits. We'll make sure to point you to more in-depth information for each topic
when possible.

Let's begin by evaluating the Main classic view found in `MyApp/classic/src/view/main/`.

### Classic

The Main classic view will appear anytime someone is using a desktop browser or a tablet, unless
otherwise specified in your [build targets](../../../../cmd/guides/intro_to_cmd.html).

Using your favorite IDE or text editor, open `MyApp/classic/src/view/main/Main.js`. This is 
the main entry point for our classic application. It's also the container
that houses our tabpanel and its four tabs. Additionally, you'll see that the first tab
includes our grid class.

Let's walk through tabs.

#### Tabs 

[[ext:Ext.tab.Panel TabPanels]] can be used similarly to standard [[ext:Ext.panel.Panel Panel]] for layout purposes, but 
they also have special support for containing child Components (items).  These items are 
managed using a [[ext:Ext.layout.container.Card Card]] layout manager, and displayed as separate tabs.

[[ext:Ext.tab.Tab Tabs]] typically default to horizontally residing at the top of your item content.  However,
in this application, we have gotten a little clever with the tabs.

You may notice that our tabs don't look like traditional tabs.  That's because
we've created a custom UI for them.

##### UI Styling

Every component in the Ext JS framework has a `ui` configuration that defaults 
to `default`. This property can be changed to allow components in your 
application to have different styles.

Most Ext JS components have SASS @mixin's that allow you to quickly generate new UIs. These 
include: Ext.panel.Panel, Ext.button.Button, Ext.Toolbar, Ext.window.Window, and many more.

Let's open our tabpanel's custom UI and take a look at what's being done.  You can find your
tabpanel UI definitions here:

	`classic/sass/src/view/main/Main.scss`

As you can see, creating UIs is simple. Simply call the associated @mixin for the component 
for which you want to create a UI.

	@include extjs-tab-panel-ui(
		$ui: 'navigation'
	);

All of the variables within the @mixin can be modified in any way you like.  

You then attach the UI to your component like so:

    ui: 'navigation',

We'll discuss styling your application with SASS in greater detail below.  

##### Responsive

You may have also noticed that we added the [[ext:Ext.plugin.Responsive Responsive]] plugin 
to the tabPanel and the `tabConfig`.  

    // TabPanel	
    responsiveConfig: {
        tall: {
            headerPosition: 'top'
        },
        wide: {
            headerPosition: 'left'
        }
    },
	
    // Tab Config
    tabConfig: {
        plugins: 'responsive',
        responsiveConfig: {
            wide: {
                iconAlign: 'left',
                textAlign: 'left'
            },
            tall: {
                iconAlign: 'top',
                textAlign: 'center',
                width: 120
            }
        }
    }

This plugin allows us to set rules that modify the tabpanel and tab text/glyph positions based on the width
and height of the viewport. In this case, if you make the browser window less wide than
tall, the tabpanel will move to the top of the screen and the tab text and glyphs will reposition.

If the viewport is wider than tall, the tabs will appear on the left and adjust the tab text/glyph
positions appropriately.

You can read more about the responsive plugin and building your application for multiple environments 
[here](../application_architecture/developing_for_multiple_screens_and_environments.html).

You may notice that there's no hard-coded data in tabs 2, 3, and 4.  That's because we're binding
data from a ViewModel.

##### View Models and Data Binding

Together, [[ext:Ext.app.ViewModel View Models]] and 
[Data Binding](../../../../cmd/guides/application_architecture/view_models_data_binding.html)  
allow you to do more with less code and write in a much more declarative style.

A [[ext:Ext.app.ViewModel View Model]] is a class that manages a data object. It then allows components interested in this 
data to bind to it and be notified when it changes. The ViewModel, like [[ext:Ext.app.ViewController ViewController]], 
is owned by the view that references it.  

For the most part, any config that may be "set" with a setter method, can be bound to the data in the ViewModel.  For 
this example, we'll utilize `setHtml()` and `setTitle()`.

Let's take a look at the following lines:

    // View Model Declaration
    viewModel: 'main',

    // Binding to header's title
    header: {
        title: {
            bind: {
                text: '{name}'
            },
            flex: 0
        }
    },

    // Binding to tab's HTML config
    {
        title: 'Users',
        iconCls: 'fa-user',
        bind: {
            html: '{loremIpsum}'
        }
    }

You can see that data is bound from the universal ViewModel (`app/view/main/MainModel.js`) 
to the tabs and app title. The data in the ViewModel is set statically, but in most cases,
this would be generated via proxy.

Check out our [ViewModels and Data Binding Guide](../application_architecture/view_models_data_binding.html) 
for more information.

#### Grids

Next, let's look at the [[ext:Ext.grid.Panel]] by opening `MyApp/classic/src/view/main/List.js`.  
List.js contains the grid that loads within the first tab of your Main tabpanel.  With this minimal
amount of code, we've created a fully functional grid. By default, each [[ext:Ext.grid.column.Column column]] 
is sortable and will toggle between ASC and DESC sorting when you click on its header. Each column 
header is also re-orderable by default, and each gains a drop-down menu with options to 
hide and show columns. 

Not only that, but it's incredibly easy to configure each column independently.

Let's dissect a couple of the grid configs a little further:

##### Store

As you can see, we are setting [[ext:Ext.data.Store store]] to a type of personnel. If you look carefully,
you'll probably notice that there isn't a store definition anywhere in the classic
area.  That's because this store lives in the universal area, 
`app/store/Personnel.js`.  We have placed the store here so that the Classic grid AND the
Modern grid can share the same store and data.

In a real world situation, the above store would have a [[ext:Ext.data.proxy.Proxy proxy]] 
with a url property allowing the proxy to pull information from a server.  We are keeping the data
in-line in this example for the sake of visualization.  However, most situations would not
call for having in-line data.

##### Listeners

You'll also notice that the Listeners object contains a `select` event that calls 'onItemSelected'.
Again, you won't find a view controller with that logic in the Classic area.  You will find
`MainController.js` in the universal section because both Modern and Classic's grid share the `select` 
event and react to it similarly.

If you haven't already, let's open `app/view/main/MainController.js`.

You'll see some very basic logic:

    onItemSelected: function (sender, record) {
        Ext.Msg.confirm('Confirm', 'Are you sure?', 'onConfirm', this);
    },

In both our grid and the Modern toolkit's grid (more in a minute), we are handling
the `select` event.  The controller logic handles both components’ `select` events identically.

We'll talk more about universal controllers further down the page.

We've covered most of the meat and potatoes from the Classic toolkit.  Let's move on to 
the Modern toolkit.

### Modern

As with Classic, let's begin by reviewing `MyApp/modern/src/view/main/Main.js`.  
This is the main entry point to our Modern application.  In much the same fashion, you'll notice
Main is a container that houses our tabpanel, and its four tabs.  Additionally, you'll see the first tab 
includes our Modern Grid.

#### Tabs

Modern toolkit's tabpanels are a great way to allow the user to switch between several views that are all 
fullscreen. Each Component in the TabPanel gets its own Tab, which shows the Component 
when tapped. Tabs can be positioned at the top or the bottom of the TabPanel.

You'll see many similarities between this view and the Classic view.  For instance:

+ Shared ViewController
+ Shared ViewModel
+ Bound Configs

#### Modern Grid

The Modern Toolkit includes a lightweight grid that is optimized for touch devices. The Modern 
grid makes it easy to fetch, sort, filter, and edit large amounts of data on touch devices. 
It’s also simple to configure and customize any column using column renderers.

As with the Classic Toolkit's grid, you can see a shared universal store and a listeners
object that is capturing the `select` event.

### Universal 

We've touched on all of the code sitting within the universal section of our application.  That said,
you'll need to make sure you're careful and consistent when utilizing this space.  At this time,
you should avoid placing application views themselves in the universal section.  If you require or
make reference to a class that does not exist in one toolkit or the other, you'll encounter
errors when building your application.

This area should generally be reserved for things found in the core of both toolkits.

+ ViewControllers
+ ViewModels
+ Models
+ Stores

Going forward, we are working towards component parity so that sharing view terminology will be 
less of a concern in the future.

Lastly, you'll want to be sure that any events you're trying to utilize have the same parameters
and are triggered with the same intent across both toolkits.

### Change Themes

Now let's focus on the look and feel of the application.  The default theme (Triton) is generated 
with every new application unless told otherwise.  That said, it's incredibly easy to swap 
themes once your application has been created.

Let's try out the Ext JS Crisp theme.

All you need to do is open your app.json file in your application root and update the 
`theme` property from:

	"theme": "theme-neptune"

to:

	"theme": "theme-crisp"

Once watch has completed, refresh the page and you should see that your application
has gotten a face-lift.

### Styling Your Application

On most occasions, you'll need to customize the look of your application beyond the capacity
of a default theme.  Your application looks pretty good, but blue just isn't working.  Let's 
try and get those active tab colors to be more unique to our application.

_**Note:** The following steps will style the classic views within your application.  In 
the near future, Ext JS 6 will be improved to allow for theming the views of both 
toolkits within the same application._

You can easily and efficiently style your application by creating and modifying SCSS files.

SCSS (Sassy CSS) is a syntax of SASS, which allows you to add nested rules, variables and
mixins to your design code.  These new additions are then processed and converted to
traditional CSS files for your application's consumption.

To see a list of global SCSS variables, check out this page from our API docs:
[[ext:Global_CSS]]

Individual components also have specific SCSS variables for you to change.  For instance,
you can view specific Panel SCSS variables by visiting the Panel API page and scrolling to 
the “CSS Variables” section: [[ext:Ext.panel.Panel]]

If you open up your `classic/sass/src/view/main/` folder, you'll see a file called 
`Main.scss`.  These folders and files will need to be added manually as needed.  For 
each class in your application, Sencha Cmd checks for a corresponding SCSS file in
`sass/var/` for variables, and `sass/src/` for rules.

These files will be picked up by `sencha app watch` when you add them.   

Let's go ahead and look at our `Main.scss` file. 

As you can see, we have some specific SCSS rules set up for the main view.  The top panel is set
by the following line:

    $ui-header-background-color: $base-color,

You have a couple of options here in terms of the scope of your color change.  If you  
only want this one piece to not be blue, you can explicitly set it to a specific color like so:
    
    $ui-header-background-color: #87BD3E,

Once the change is picked up and processed by watch, you can refresh your page and see that 
your active tab color is now green (#87BD3E).  

However, if you want to replace blue for green across the entire application, you can change
the value of `$base-color`. In order to do this, create an SCSS file for your global 
rules in the following location:

	classic/sass/etc/all.scss // all.scss may contain any SASS / CSS rules
	
Once you've created your file, you can add a new `$base-color` declaration that will
override the app theme's `$base-color` value.  In this case, let's do the same green.

	$base-color: #87BD3E dynamic();

After your application is refreshed, you should now see that many components are that color
of green.  

## Wrap Up

Now you see how easy it is to get an application up and running using Ext JS and Sencha
Cmd.  Make sure to check out the API docs for all of the Components and classes that we
explored throughout this walkthrough. 
