# Getting Started 

In this guide we will be starting from scratch and creating an Ext JS 6.5 application using
the Modern Toolkit. This toolkit is designed for mobile devices and modern desktop browsers,
such as Chrome, Firefox, Edge, Safari and IE11. To target older IE browsers, see the section
titled **Classic Toolkit** below.

Starting with a minimal application (which Sencha Cmd generates), we will incrementally add functionality to this application following Sencha's recommended best practices. While one can use Ext JS as a pre-built JavaScript and CSS file, your real world applications will greatly benefit by starting on a scalable foundation of tools that can produce optimized builds for your end-users.

Let's get started!

## Prerequisites

1. [Download and Install Sencha Cmd 6.5.1](http://www.sencha.com/products/sencha-cmd/)
2. [Download the Ext JS 6.5 SDK](http://www.sencha.com/products/extjs/evaluate/)

We recommend extracting Ext JS in a fixed location in your "home" directory:

    C:\Users\Me\sencha-sdks    # Windows
    /Users/Me/sencha-sdks      # Mac OS X
    /home/me/sencha-sdks       # Linux

After unzipping Ext JS in this folder, you should see a sub-folder such as the following (on Windows):

    C:\Users\Myname\sencha-sdks\ext-6.5.1

Now that Sencha Cmd is installed and the Ext JS SDK is extracted, let's configure Sencha Cmd with this location. For example (on Windows):

    > sencha config --prop sencha.sdk.path=C:\Users\Me\sencha-sdks --save

With this setting saved, you can download later versions of Ext JS into this same folder and not need to repeat this last step.

## Initializing the Application

To create the application, open a terminal or command prompt and create an empty directory and "cd" into it:

    > md ~/myapp    # On Windows, replace "~" with "C:\Users\Me"
    > cd ~/myapp

From this directory, we run "sencha app init" to create the application on disk:

    > sencha app init --ext@6.5.1 --modern MyApp

This will produce a few lines of output as the application code is generated and the necessary pieces of Ext JS are copied into the current directory. The current directory should now contain:

    ext651/
    .gitignore
    app.js
    app.json
    build.xml
    index.html
    workspace.json

## Launching the Application

To build the application (to allow the browser to load it), run the following command from that same directory:

    > sencha app watch

You will see a few lines of information as Sencha Cmd builds the application, but there are two to take note of:

    ...
    [INF] Application available at http://localhost:1841
    …
    [INF] Waiting for changes...

While app watch is running, a basic web server is serving the application directory. Now we can load [http://localhost:1841](http://localhost:1841) in the browser and see the application.

Sencha Cmd is also monitoring your application directory for changes. Should you make changes to the styling or JavaScript code, Sencha Cmd will detect these changes and update the necessary build outputs to keep the application rendering correctly in the browser. As your changes are detected, Sencha Cmd will log a few lines of output and (in typically a couple seconds) end with "Waiting for changes…" to let you know everything is ready.

This means that to make changes to your application, you edit the code in your IDE or text editor and hit Save... and then just Reload in the browser.

You can stop app watch by pressing `CTRL+C`.

## Modifying the Application

The application we've just created is extremely minimal: it only displays a message box! Even so, it is helpful to look at the generated code. If you look in "index.html" you won't see any visual HTML content. This is because Ext JS is a "JavaScript-first" framework. That is to say, the user interface and its logic are all defined in JavaScript. The necessary styling is provided by the various included themes (such as Material).

While direct authoring of HTML is not necessary, you can of course add Ext JS to existing pages and create components inside hand-written HTML documents. Since this is not necessary to create applications in Ext JS, this guide will not explore that approach further.

Ext JS is a class-based, object-oriented framework. There are many hundreds of classes provided by Ext JS that you can use or extend to create your application. These classes range from non-visual classes that manage data and server communication to user interface components that provide powerful functionality. By creating your own classes based on these components, you can concentrate on making a compelling application.

The starting point of an Ext JS application is app.js (as specified in app.json). The generated app.js file looks something like this:

    Ext.application({
        name: 'MyApp',

        requires: [
            'Ext.MessageBox'
        ],

        launch: function () {
            Ext.Msg.alert('Hello Ext JS', 'Hello! Welcome to Ext JS.');
        }
    });

The [[ext:Ext#method!application Ext.application]] method informs Ext JS about your application. In this case, this is just a name and a launch method. We also describe the classes we are using in the application with "requires".

Once the required classes are loaded and the browser is ready, the launch method is called.
This is where the application performs its startup sequence. To get things started, let's define an application class and our main view.

### The Application Class

By default the Ext.application() method creates a basic [[ext:Ext.app.Application application]] instance, but most applications will need to customize this and provide their own top-level logic. For example, applications typically need to handle things like deep-linking and the browser's Forward and Back buttons (commonly called "routing"). While this guide will not address these issues, it is a best practice to have an Application class, so let's create a bare-bones version:

    ./app/Application.js

    Ext.define('MyApp.Application', {
        extend: 'Ext.app.Application',

        mainView: 'MyApp.view.main.Main'
    });

This application does not require special logic at launch, so we have replaced the launch method with the mainView config property. The inherited launch method will create an instance of this class.

Aside: Config properties are special properties declared by Ext JS classes that are similar to the attributes of HTML elements (such as "disabled" or "value"). These config properties (or just "configs") can be specified on the class body (as above) or passed in the "config object" which is the single argument to the constructor.

Now that we have an Application class, app.js should be changed to match:

    Ext.application({
        name: 'MyApp',
        extend: 'MyApp.Application',  // <<== added

        requires: [
            'MyApp.*'   // tell Cmd to include all app classes
        ]
    });

### The Main View

The class name we've chosen for the main view is "MyApp.view.main.Main", so by convention we will create the JavaScript file `'./app/view/main/Main.js'`. The "app" folder is where Sencha Cmd looks for application classes (as configured by app.json). Views are placed in "app/view". The reason for the "main" directory will become clear when we add a controller and styling to the view as these files will also be placed in this directory.

A common main view for many applications is a tab panel, so let's start by extending this class for our main view:

    ./app/view/main/Main.js

    Ext.define('MyApp.view.main.Main', {
        extend: 'Ext.tab.Panel',

        requires: [
            'Ext.Button'
        ],

        items: [{
            title: 'Home',
            html: '<h1 class="main-banner">Hello World!</h1>',
            items: [{
                xtype: 'button',
                text: 'Go'
            }]
        }, {
            title: 'Notifications'
        }, {
            title: 'Settings'
        }]
    });

A tab panel is a specialized [[ext:Ext.Container container]]. A container is simply a component that contains other components. These child components (typically called "items") are added to the container by assigning the "items" config. In the above, the tab panel extends the basic container class and adds a tab bar to enable the user to switch between its child items.

### Adding a Controller

We've added some content to the Home tab: some HTML and a button component. This is also why we added the "requires" for the [[ext:Ext.Button Ext.Button]] class. This allows us to use its "xtype" in the items of the Home tab. An "xtype" is a component alias much like the tag name of an HTML element.

This button, however, is rather inert. Clicks do nothing but ripple the button. To add logic, we need a handler method. With Ext JS we can write this handler directly in the view, but this is discouraged. Instead we put this code in a controller.

    ./app/view/main/MainController.js

    Ext.define('MyApp.view.main.MainController', {
        extend: 'Ext.app.ViewController',
        alias: 'controller.main',

        requires: [
            'Ext.MessageBox'
        ],

        onGo: function () {
            Ext.Msg.alert('Go', 'From main view controller');
        }
    });

This class extends [[ext:Ext.app.ViewController ViewController]] and is thus a controller suitable for controlling views. We've also assigned it the alias "controller.main". This alias allows us to easily associate the controller to our main view:

    Ext.define('MyApp.view.main.Main', {
        extend: 'Ext.tab.Panel',

        controller: 'main',   // <<== added
        ...

Now we can direct the Go button to the onGo [[ext:Ext.Button#method!handler handler]] in the controller:

        ...
        items: [{
            xtype: 'button',
            text: 'Go',
            handler: 'onGo'  // <<== added
        }]

This is very similar to how one would add an onclick attribute to a button HTML element. In this case, the method is located using the provided name and looking upwards (from the button) to find the controller.

### Using Data Binding

In many applications, large proportions of the code are concerned with responding to changes and reflecting these changes in appropriate components. For example, disabling a button if a certain input field is empty.

Ext JS applications can use "data binding" to automate these common tasks. Data binding allows an application to manage state data in objects called [[ext:Ext.app.ViewModel view models]] and then easily connect these data to component config properties.

Let's add a [[ext:Ext.field.Text textfield]] component and a viewModel and use the [[ext:Ext.Component#cfg!bind bind]] config to keep our components in sync:

    Ext.define('MyApp.view.main.Main', {
        extend: 'Ext.tab.Panel',
        controller: 'main',

        requires: [
            'Ext.Button',
            'Ext.field.Text'  // <<== added
        ],

        viewModel: {   // <<== added
            data: {
                userName: ''
            }
        },

        items: [{
            title: 'Home',
            html: '<h1 class="main-banner">Hello World!<h1>',
            items: [{
                xtype: 'textfield',  // <<== added
                label: 'User name',
                bind: '{userName}'
            }, {
                xtype: 'button',
                handler: 'onGo',
                bind: {             // <<== added
                    disabled: '{!userName}',
                    text: '{userName ? "Save: " + userName : "Save"}'
                }
            }]
        }, {
            title: 'Notifications'
        }, {
            title: 'Settings'
        }]
    });

There are several things going on here, so let's break this down step by step:

We've used the viewModel config to define a view model and added a "userName" string to its data object. This view model's data is now available to all of the components contained in the main view.

The "textfield" component wraps an HTML `input` element and allows the user to enter text. This component is configured with a bind config that binds its value to the userName property in the view model. Changes made by the user will be automatically reflected in the view model data. Likewise, if the view model data were changed, this text field's value would be updated. This is called two-way data binding.

When the value of the bind config is a string as with our text field, that string is understood to be the bind expression for the default config property. In the case of text fields that is the "value" config. When the bind config is given an object value as with our button, however, the key/value pairs of this object are the names of configs and their corresponding bind expressions. For our button we have bound the "disabled" and "text" configs.

The bind expression in the string '{!userName}' contains one replacement token (inside the "{}" pair) which is evaluated as you would expect in JavaScript. If the userName value from the view model is empty, the button will be disabled. The bind expression for the text property illustrates an even more flexible binding expression.

If you run the application with these changes you will see how the button's text and disabled state track whatever is typed into the text field. No explicit logic is required to keep these pieces synchronized.

View models have many more capabilities that can declutter the code you would otherwise have to write. See [ViewModels and Data Binding Guide](../application_architecture/view_models_data_binding.html) for more on this.

### Handling Events

While data binding can handle many common cases, applications need to handle some user interactions explicitly. As with HTML elements, Ext JS components fire events. Similar to the button handler shown previously, event handlers are typically attached to a component and provided by a controller. Events handlers are attached to components using "listeners":

    items: [{
        xtype: 'textfield',
        label: 'User name',
        bind: '{userName}',

        listeners: {   // <<== added
            action: 'onGo'
        }

The [[ext:Ext.field.Text#event!action action]] event is an event fired by the text field when the user presses ENTER. We direct this event to the same controller method as the button's handler. While this sharing of handlers is a convenient, it is important to note that it is not always appropriate to do this.

Method sharing is typically inappropriate if the controller method needs to process its arguments. So far the controller has not used its arguments and so there is no issue sharing the method like this. If the onGo method, however, were to need the [[ext:Ext.Button#cfg!handler arguments passed by the button]] then attaching it to the action event of the text field would cause problems since it provides different [[ext:Ext.field.Text#event!action arguments]].

## Using Grids

While Ext JS provides various useful components such as buttons, it is known for its many "super" components. The most popular of these is the Ext JS Grid. Grids are a simple way to display tabular data and allow your users to easily interact with and manipulate that data. Let's create a new view and add a grid for the Notifications tab:

        }, {
            title: 'Notifications',
            xtype: 'notifications'  // <<== add to main view
        }, {

Create the new view:

    ./app/view/notify/Notifications.js

    Ext.define('MyApp.view.notify.Notifications', {
        extend: 'Ext.Panel',
        xtype: 'notifications', // #1

        requires: [
            'Ext.grid.Grid',
            'Ext.grid.column.Date',
            'Ext.layout.Fit'
        ],

        layout: 'fit', // #2

        items: [{
            xtype: 'grid',

            store: {
                type: 'notifications' // we'll define this next
            },

            columns: [{
                xtype: 'datecolumn',
                text: 'Date',
                dataIndex: 'date'
            }, {
                text: 'Description',
                dataIndex: 'description',
                flex: 1
            }]
        }]
    });

This view has several new pieces to consider.

First is the "xtype" provided in the Ext.define() call which sets "notifications" as the component alias (or "xtype") for this view. This is what allows the main view to use "xtype" in its items and create an instance of the appropriate class.

Second, our view extends [[ext:Ext.Panel Ext.Panel]] (a type of container) and contains our grid as its single child item. We use the inherited "layout" config to size and position our child grid. In this case we use the "fit" layout. The fit layout will fill the container with the single child item.

This brings us to the grid. The two main configs required to display a grid are the "columns" it should display and the data "store" that holds its records.

The columns array holds one or more [[ext:Ext.grid.column.Column column]] components. Columns typically have a "text" config that indicates what to display in the column header and a "dataIndex" config to indicate the field from the record that should be displayed in the cells. In addition to these, the "width" config can be used to give a column a particular width or a "flex" config can be assigned to size columns proportionally based on the grid's width.

## Data Models and Stores

Managing data is a central aspect of most applications and Ext JS provides a robust data package to simplify this task. In an Ext JS application, data modeling is provided in two main classes: [[ext:Ext.data.Model Ext.data.Model]] and [[ext:Ext.data.Store Ext.data.Store]].

A "model" is a class that describes the fields and behaviors of some type of information used in the application. This is sometimes called an "entity" in other frameworks. Instances of a model class are called "records". Records have a "data" object that contains the values of its fields. Let's see what a notification model might look like:

    ./app/model/Notification.js

    Ext.define('MyApp.model.Notification', {
        extend: 'Ext.data.Model',

        fields: [{
            name: 'date',
            type: 'date'
        }]
    });

All models ultimately extend [[ext:Ext.data.Model Ext.data.Model]] and most define one or more "fields". The recommended naming convention for models is used here. Instead of "view" we use "model".

We have declared "date" to be a [[ext:Ext.data.field.Date date]] field. This ensures that values for this field become `Date` objects. The "description" field (used by the grid) is not declared so it will be stored in the record's data object in whatever form the server provides it. Declaring model [[ext:Ext.data.Model#cfg!fields fields]] is useful for knowing what data is present in a record but is also helpful for type conversion and validation.

Now that we have a model, we can define a [[ext:Ext.data.Store store]] to hold records of this type:

    ./app/store/Notifications.js

    Ext.define('MyApp.store.Notifications', {
        extend: 'Ext.data.Store',
        alias: 'store.notifications',

        model: 'MyApp.model.Notification',

        data: [
            {
                date: '2017-05-20T10:20:30Z',
                description: 'The first notification'
            }
        ]
    });

The alias of "store.notifications" allows the grid to use this type of store:

    store: {
        type: 'notifications'
    }

For the sake of simplicity in this example, we have defined inline data in the store. In real-world applications, either or both the model and store class would define the means by which these data will be transferred to and from the server. This is done using a [[ext:Ext.data.proxy.Proxy proxy]]. The proxy classes provided by Ext JS allow you to easily connect to a server providing JSON, REST, XML or other forms of data.

## Theming and Styling

So far we've looked at the structural and functional aspects of an Ext JS application. While these are essential, applications also have to have great aesthetics and Ext JS provides several themes to get your application off to a great start. The application's theme is specified in app.json, which has this default:

    "theme": "theme-material"

The value of the "theme" property is the name of the theme package. The Ext JS modern toolkit provides four standard themes from which you can choose:

  - **theme-material** (the default, based on Google's Material Design)
  - **theme-ios** (for iOS devices)
  - **theme-triton** (a clean, flat theme suited for desktop applications)
  - **theme-neptune** (a slight variation on theme-triton)

Applications can use these themes, set [[ext:Global_CSS theme variables]] or use a custom theme package that extends one of the default themes. Ext JS defines many global theme variables and components add additional theme variables to control their appearance. To set these variables, we need to add styling code to the application.

As Sencha Cmd compiles the JavaScript classes in your application, it also includes any styling  that you associate with these classes. Since theming is application-wide, this code is best associated with the Application class:

    ./app/Application.scss

    $base-color: #87BD3E;

The `$base-color` theme variable is perhaps the most important variable in the theme as it defines the starting point for most colors. It is strongly encouraged that style code be placed in .scss files that reside with the views to which they apply. For example, to write styles for the main view, add the desired styles to "./app/view/main/Main.scss".

### Styling Application Views

To address the challenge of managing CSS, which can quickly become a problem in even modest-sized applications, Ext JS applications should put view-specific styling in files in the same directory as their view. For example, to style the "main-banner" class we added to the `h1` tag, we would create this file:

    ./app/view/main/Main.scss

    .main-banner {
        font-style: italic;
    }

Notice the "main-" prefix. Using the view's name helps ensure these rules to not accidentally apply to other views. This can be split into two levels in some cases by using the cls config:

    Ext.define('MyApp.view.main.Main', {
        extend: 'Ext.tab.Panel',
        controller: 'main',

        cls: 'main',   // <<== added

        ...
        items: [{
            title: 'Home',
            cls: 'home',   // <<== added
            html: '<h1 class="banner">Hello World!<h1>',  // <<== changed

Now we can use the "main" and "home" classes and write nested rules to scope styles to the correct view:

    ./app/view/main/Main.scss

    .main {
        .home {
            h1.banner {
                font-style: italic;
            }
        }
    }

Nesting is often simpler to write and understand but can result in undesired matching. This is because the nested rules above will become this in the output CSS:

    .main .home h1.banner {
        font-style: italic;
    }

This will apply the main view's styles to all "h1.banner" elements in the home tab, even if they belongs to other descendant views. It is not generally recommended to mix nesting and prefixing in the same view.

To learn more about theming and styling, see the [Theming Guide](../core_concepts/theming.html).

## Classic Toolkit

If your application requires the browser support or some features unique to the classic toolkit, you can instead generate a classic application:

    > sencha app init --ext@6.5.1 --classic MyApp

While there are some API differences, all the concepts discussed previously apply to both toolkits. The majority of changes required would be class names. For example, Ext.grid.Grid is the grid component in the modern toolkit, while Ext.grid.Panel is the class name in the classic toolkit.

## Universal Applications

If you will need the classic toolkit for the desktop but modern for mobile devices, you can create a universal application.

    > sencha app init --ext@6.5.1 --universal MyApp

The major difference with a universal application is the use of build profiles to create different JavaScript and CSS bundles for the different target platforms. This change requires some adjustments to the way we organize the application code:

  - `./app` The common code folder. For example, for things like models, stores and some controllers.
  - `./resources` Folder for resources common to all builds.
  - `./classic/resources` For resources (like .png files) specific to the classic build.
  - `./classic/src` The folder for code specific to the classic build.
  - `./modern/resources` For resources (like .png files) specific to the modern build.
  - `./modern/src` The folder for code specific to the modern build.

## Wrap Up

Now you see how easy it is to get an application up and running using Ext JS and Sencha
Cmd.  Make sure to check out the API docs for all of the Components and classes that we
explored throughout this walkthrough. 

**Note:** _If you're curious about what the above steps entail, you may want to check out
our [Introduction to Sencha Cmd Guide](../../../../cmd/guides/intro_to_cmd.html)._

