# Theming The Ext JS Classic Toolkit

This guide is the continuation of the [Ext JS Theming](./theming.html) guide and is focused on
the Theme API for the Ext JS Classic Toolkit, so please read that guide before proceeding. See
the [Theming The Ext JS Modern Toolkit](./modern_theming.html) guide for information about the
modern toolkit.

## Requirements

This guide assumes you have met all the Requirements described in the [Ext JS Theming](./theming.html)
guide. To recap:

 - Download [Sencha Cmd](http://www.sencha.com/products/sencha-cmd) version 6.5+
   - When using a non-JRE installer, download [Java JRE 1.8+](http://java.com/en/download/)
 - Download [Sencha Ext JS](http://www.sencha.com/products/extjs) version 6.5+

### Setup

This guide assumes you have a workspace, the custom `my-theme` and the `demo-app` generated as
described in the [Ext JS Theming](./theming.html) guide.

You should be able to `watch` the demo application using the following command (or run the
`sencha app build --development` command to compile your styles):

    $ sencha app watch --fashion

After running `sencha app watch` you can pull up your application using the URL:

    http://localhost:1841/demo-app/

The `--fashion` switch will instruct the browser to refresh the styling within the application
as you make changes to the application's theme - often in under a second! **Reminder:** This
Live Update feature is supported on modern browsers only (others will require a manual Reload
to see changes).

## Theming Components

As discussed in general in the previous [guide](./theming.html), the Theme API for components
consists of variables and mixins. The default appearance of a component is determined by its
variables, while custom appearances can be defined and named by calling the "UI mixin".

### Configuring Theme Variables

Each themeable Ext JS component has a list of variables that can be used to configure its 
appearance. Let's change the `font-family` of Panel Headers in `my-theme`. Create a 
file named `my-theme/sass/var/panel/Panel.scss` and add the following code:

    $panel-header-font-family: Times New Roman;

View your application now and you should see that the panel headers use "Times New Roman" 
font.  You can find the complete list of variables for each component in the "Theme Variables" 
section of the component's API documentation. For example, see [[ext:Ext.panel.Panel]] and
scroll to the section titled "Theme Variables"

### Using Theme Mixins

All components in the Ext JS Classic Toolkit have a `ui` config property, which defaults to
`"default"`. This config property can be configured on individual component instances to give
them a different appearance from other instances of the same type. This config is used within
the Neptune theme to create different types of [[ext:Ext.panel.Panel Panels]] and
[[ext:Ext.button.Button Buttons]]. For example, panels with the default `ui` have dark blue
headers and panels with the 'light' `ui` have light blue headers. Buttons use `ui`'s to give
toolbar buttons a different appearance from regular buttons.

The `theme-neutral` theme includes Theme Mixins (or UI Mixins) for many of the different Ext JS
components. You can call these mixins to generate a new `ui` for components. Available mixins
for each component are listed in the API documentation. For example, see [[ext:Ext.panel.Panel]]
and scroll down to the "Theme Mixins" section to see what parameters the Panel UI mixin accepts.
Let's use this mixin to create a custom Panel `ui`.

Create a file named `my-theme/sass/src/panel/Panel.scss` and add the following to it:

    @include extjs-panel-ui(
        $ui: 'highlight-framed',
        $ui-header-background-color: red,
        $ui-border-color: red,
        $ui-header-border-color: red,
        $ui-body-border-color: red,
        $ui-border-width: 5px,
        $ui-border-radius: 5px,
        $ui-header-color: white
    );

This mixin call creates a new Panel `ui` named `"highlight"` which has a red header
background, red bordering, 5px border, 5px border-radius, and white text. To use
this `ui`, configure a Panel with `'highlight'` as its `ui` property (along with
`frame: true`). Open `demo-app/app/view/main/List.js` and replace its contents with
the following:

    Ext.define('App.view.main.List', {
        extend: 'Ext.grid.Panel',
        xtype: 'mainlist',

        ui: 'highlight',
        frame: true,

        requires: [
            'App.store.Personnel'
        ],

        title: 'Personnel',

        store: {
            type: 'personnel'
        },

        columns: [
            { text: 'Name',  dataIndex: 'name' },
            { text: 'Email', dataIndex: 'email', flex: 1 },
            { text: 'Phone', dataIndex: 'phone', flex: 1 }
        ],

        listeners: {
            select: 'onItemSelected'
        }
    });

View your application in a web browser and you should see the red "highlight" Grid.

While UI mixins are a handy way to configure multiple appearances for a component, they 
should not be overused. Each call to a UI mixin generates additional CSS rules. Excessive 
calls to UI mixins can produce an overly large CSS file.

## Slicing Images for CSS3 effects in IE

In some themes, many components have rounded corners and linear gradient backgrounds. These
effects are simple to accomplish in modern browsers using CSS3.  However, Ext JS supports
IE8 and IE9 and neither of these browsers support these effects (or do so in a way that makes
combining the effects problematic).

Sencha Cmd closes this gap by rendering each component requiring these effects in a headless 
browser and slicing images from the corners and gradients for use as background images in the 
component markup in IE8/9.  When adding custom `ui`'s you'll need to include them in the 
slicing manifest used by Sencha Cmd so that the component decorated with the custom `ui` will
be sliced for use in IE8/9.

To do this, we need to tell Sencha Cmd which components and `ui`'s need slicing.  In order to 
create slices for the rounded corners of the "highlight" panel `ui` that you created earlier 
in the guide, edit the file named `my-theme/sass/example/custom.js` and add 
the following:

    Ext.theme.addManifest({
        xtype: 'panel',
        ui: 'highlight'
    });

**Note:** Multiple manifest entries may be added in the same `addManifest` call like:

    Ext.theme.addManifest({
        xtype: 'panel',
        ui: 'highlight'
    }, {
        xtype: 'button',
        ui: 'green'
    });

If you create an original component that requires slicing you'll need to add any applicable 
`ui` configs to the slicing manifest as demonstrated above.  You will also need to add 
config entries for the custom component using the `Ext.theme.addShortcuts()` call in 
`custom.js`.

The shortcut configs along with the `ui`'s passed to the manifest will be used in rendering 
the custom component for slicing.

For a more detailed description of how to use `Ext.theme.addShortcuts` and 
`Ext.theme.addManifest`, refer to the inline documentation descriptions for each method 
found in `my-theme/sass/example/render.js`.  You can refer to examples of `addShortcuts`
for the framework components within the `ext/classic/theme-base/sass/example/shortcuts.js` file.

## Modifying Image Assets
As an example of modifying an image asset let's change the info icon of the MessageBox
component. Save the following image as `my-theme/resources/images/shared/icon-info.png`.
This image asset will take precedence over the one used in the parent Crisp theme at 
`my-workspace/ext/classic/theme-crisp/resources/images/shared/icon-info.png`.

Now modify your test application to show a MessageBox that uses the custom icon. Add the 
following `tbar` config to the "highlight" Grid in your application's 
`demo-app/app/view/main/List.js` file:

    ...
    tbar: [{
        text: 'Show Message',
        handler: function() {
            Ext.Msg.show({
                title: 'Info',
                msg: 'Message Box with custom icon',
                buttons: Ext.MessageBox.OK,
                icon: Ext.MessageBox.INFO
            });
        }
    }]
    ...

Now, view the app in the browser. When you click the "Show Message" button you should see 
that the MessageBox contains a friendly face.

# Styling Your Application

Styling that is not shared between applications belongs in the application itself, not in 
the theme. Sencha Cmd provides an easy way to add application-level styling by allowing you
to organize your styles right alongside your JavaScript code.

## Styling Your Application's Views

To write CSS rules associated with an application view, you create an `.scss` file in the
same folder and with the same base name as the view. For example, to style the view
`App.view.main.Main`, located in `demo-app/app/view/main/Main.js`, you
would put that code in `demo-app/app/view/main/Main.scss`.

Let's style the content of the **Users** tab in the App application:

    .content-panel-body h2 {
        color: orange;
    }

Add the `content-panel-body` CSS class to the config of the **Users** panel in your 
application's Main.js file:

    ...
    title: 'Users',
    iconCls: 'fa-user',
    html: '<h2>Content appropriate for the current navigation.</h2>',
    bodyCls: 'content-panel-body'
    ...

View your application and you'll see that the `h2` element in the **Users** view is now 
orange. While the ability to add arbitrary CSS styles offers maximum flexibility, any
styling applied directly to elements owned by Ext JS components should be styled using
the Ext JS theming API whenever possible. Using the theming API safeguards your styling
against breaking markup changes in future versions of Ext JS.

## Additional Notes

### 'default' Component Images
Various components have images relating the the component's `"default"` `ui` (Buttons, 
Menus, etc.).  When you create a custom `ui` for one of these components you'll notice when 
the theme is compiled it warns that images for your theme were not found. 

    WARNING: @theme-background-image: Theme image not found:

While refreshing the theme or app, Sencha Cmd will be looking for images using the `ui` name 
in place of `"default"` in the image name.  For example, if you create a mixin `ui` with a 
name of `"admin"` for small Buttons, Sencha Cmd will warn that `"admin-small-arrow.png"` was 
not found.

The solution to this warning is to copy over any image assets with "default" in the file
name from the theme you're extending into the custom theme's `resources/images` directory.
You'll then rename those files and replace "default" with the name of your custom `ui`. In
the case of the `"admin"` button `ui` in your custom theme extending Neptune you would copy
the `"default"` images from the `ext/classic/theme-neptune/resources/images/button` folder
and paste them into `packages/local/my-theme/resources/images/button/`.  You'll 
then rename all `"default"` instances to `"admin"`.  For instance:

    $ mv default-small-arrow.png admin-small-arrow.png

### Ext.button.Button
Button `ui` images will need to be copied from the parent theme to the custom theme when 
creating a custom `ui`.  See the "'default' Component Images" section above for more detail.

Button scale can be configured as `small`, `medium`, or `large` with `small` being the 
default.  When creating custom UIs for buttons you'll need to provide a button mixin for 
each scale used in your application.

**Note:** The `extjs-button-ui` mixin should be avoided in favor styling buttons using 
the scale-specific mixins.

    @include extjs-button-small-ui(
        $ui: 'green',
        $background-color: green
    );

    @include extjs-button-medium-ui(
        $ui: 'green',
        $background-color: green
    );

    @include extjs-button-large-ui(
        $ui: 'green',
        $background-color: green
    );

The same applies when using the `-toollbar` button mixins. Each has a scale and should be
included separately in the `Button.scss` file in order to support all button scales.
Additionally, when working with the `-toolbar` button mixins you will need to add `-toolbar`
to the `ui` config of the button in your application. Below is an example mixin for a small 
toolbar button mixin:

    @include extjs-button-toolbar-small-ui(
        $ui: 'green',
        $background-color: green
    );

which would decorate a button configured in a toolbar like:

    xtype: 'toolbar',
    items: [{
        text: 'Toolbar Button',
        ui: 'green-toolbar'
    }]

### Ext.panel.Panel
Panels may be configured with `frame: true` and are `frame: false` by default.  So, by 
default if you have a `ui` config of `ui: 'highlight'` then the resulting `Panel.scss` 
would look like:

    @include extjs-panel-ui(
        $ui: 'highlight',
        $ui-header-background-color: red,
        $ui-border-color: red,
        $ui-header-border-color: red,
        $ui-body-border-color: red,
        $ui-border-width: 5px,
        $ui-border-radius: 5px
    );

However, this will only apply styling to non-framed panels.  In order to style panels 
configured with `frame: true` and `ui: 'highlight'` you will need to add `-framed` to the 
`$ui` name in the Panel.scss file.  Commonly both the framed and unframed ui versions will 
be represented in Panel.scss

    @include extjs-panel-ui(
        $ui: 'highlight',
        $ui-header-background-color: red,
        $ui-border-color: red,
        $ui-header-border-color: red,
        $ui-body-border-color: red,
        $ui-border-width: 5px,
        $ui-border-radius: 5px
    );

    @include extjs-panel-ui(
        $ui: 'highlight-framed',
        $ui-header-background-color: red,
        $ui-border-color: red,
        $ui-header-border-color: red,
        $ui-body-border-color: red,
        $ui-border-width: 5px,
        $ui-border-radius: 5px
    );

### Ext.menu.Menu
Menu `ui` images will need to be copied from the parent theme to the custom theme when 
creating a custom `ui`.  See the "'default' Component Images" section above for more detail.

### Ext.toolbar.Breadcrumb
Breadcrumb `ui` images will need to be copied from the parent theme to the custom theme 
when creating a custom `ui`.  See the "'default' Component Images" section above for more detail.

### Ext.tab.Tab
Tab `ui` images will need to be copied from the parent theme to the custom theme when 
creating a custom `ui`.  See the "'default' Component Images" section above for more detail.

When creating a tab `ui` be sure to include all applicable state vars you want to style 
including the `-active` tab states such as `$ui-color-active`, `$ui-background-color-active`, etc.

### Ext.tab.Bar
TabBar ui images will need to be copied from the parent theme to the custom theme when 
creating a custom `ui`.  See the "'default' Component Images" section above for more detail.

**Note:** When creating a TabBar `ui` with the `extjs-tab-bar-ui` mixin, you will need to 
create a corresponding `tab-ui` of the same name.

This will ensure that the tabs render properly in your theme. Not creating a matching 
tab theme may result in unpredictable tab rendering.

### Ext.toolbar.Toolbar
Toolbar `ui` images will need to be copied from the parent theme to the custom theme when 
creating a custom `ui`.  See the "'default' Component Images" section above for more detail.

## Upgrading from Ext JS 5.x
While most of the updates to themeing occurred behind the scenes between Ext JS 5 and 6,
there are a few changes to note when upgrading your theme.

Any variables defined in `sass/etc/all.scss` should be moved to `sass/var/all.scss`
(or a `.scss` file `@import`-ed by `sass/var/all.scss`).

(_recommended_) Remove `!default` from the end of variable declarations

(_recommended_) Relocate your custom theme folder from the root `packages/` folder in 
your application / workspace to `packages/local/`.
