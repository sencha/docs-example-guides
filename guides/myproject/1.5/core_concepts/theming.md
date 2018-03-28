# Theming Ext JS
The default themes available with Ext JS can be used out of the box to create clean, 
professional looking applications. You may wish to provide your own styling, however,
to match your personal design aesthetic or that of an existing enterprise design.

Historically, styling an application meant creating style sheets with rules to tweak or
decorate individual HTML elements used in the rendering of a component. Several issues 
arise with this approach. The first being that you're now burdened with styling across 
all supported browsers. Secondly, as the framework evolves the component's underlying
elements may change, leaving you with the unpleasant task of chasing the changes in your 
style rules. Styling components using the Ext JS Theming API solves these problems
for you.

Themes may be shared across any number of Ext JS applications in the workspace (a workspace
is a simple file-system structure defined by Sencha Cmd). Themes allow you to style once and
apply that styling over and over with confidence in the consistency of your applications'
look and feel.

This guide will list the requirements necessary for theming and cover the basics for creating
a custom theme. Since many of the details differ based on whether you are using the classic
or modern toolkit, this guide focuses on the common principals. The specifics are found in
these guides: [Theming The Ext JS Modern Toolkit](./theming_modern.html) and
[Theming The Ext JS Classic Toolkit](./classic_theming.html).

## Requirements

### Sencha Cmd 6.5+
[Sencha Cmd](http://www.sencha.com/products/sencha-cmd) is a command-line tool used to package
and deploy Ext JS applications. To build a theme in Ext JS 6.5, you must have Sencha Cmd 6.5
or higher installed on your computer. For more information about installing and getting started
with Sencha Cmd see [Introduction to Sencha Cmd](../../../../cmd/guides/intro_to_cmd.html).

### Java JRE
The [Java JRE](http://java.com/en/download/) is required to run Sencha Cmd. Whenever possible, we
recommend running the latest version of the JRE (version 1.8 as this is written). Version 1.7 or
newer, however, is required to run `sencha app watch`. This command is run within the application
directory and updates the compiled theme automatically as you modify the theme source. Sencha Cmd
has installers with the JRE included or as a stand-alone installer without the JRE. If you do not
already have a suitable JRE, we recommend using the installer with JRE if one is available for
your platform.

**Note:** Without Java JRE 1.7+ and `sencha app watch` you will need to manually rebuild your
application's styling after each change using `sencha app build --development`.

### Ext JS
Custom themes are based on default themes included with the Ext JS SDK.
[Download Ext JS](http://www.sencha.com/products/extjs) and extract the Ext JS 
development kit (SDK) to a location of your choosing. We recommend a folder in your home
directory called `sencha-sdks`.

## Building a Custom Theme
Once you have installed the above requirements, you can proceed to create your custom theme. A
theme is simply a specific type of Sencha Cmd package. All packages can contain JavaScript,
CSS styles and resources that will be incorporated into apps when Sencha Cmd builds them. As
we will see, theme packages take advantage of all of these types of assets.

### Create The Workspace
Workspaces are Sencha Cmd's way of connecting applications (as well as themes or other code
packages) with a shared copy of the Ext JS framework. If you only have one application to
build, Sencha Cmd can combine the workspace and application in a single directory.

For this tutorial we'll create a workspace so that the custom theme is accessible to multiple
applications. Run the following command from the directory where you want to create
your workspace (e.g., "my-workspace"):

    $ sencha workspace init
    $ sencha framework add ~/sencha-sdks/ext-6.5.0

On Windows, replace `~/sencha-sdks/` with `%USERPROFILE%\sencha-sdks\`. If you have chosen a
different path, then use the appropriate path here.

The `sencha workspace init` command will create the scaffolding for a Sencha workspace in the
current directory. The `sencha framework add` command copies the necessary files from the
Ext JS SDK into the workspace so that the theme and applications can find these dependencies.

This workspace is where your custom theme package will live. You will also create applications
here that will use your custom theme. After running the above commands, you will find these
files in your workspace directory:

 - **ext65/** - The Ext JS SDK (populated by `sencha framework add`).
 - **workspace.json** - The configuration descriptor for the workspace.
 - **.gitignore** - A starter file to keep your Git repository clean.

### Generate The Theme Package
Sencha Cmd streamlines the process of creating a custom theme by generating a theme package 
containing all the necessary files. Run the following command from the workspace directory
to generate your theme:

    $ sencha generate theme my-theme

This tells Sencha Cmd to generate a theme package named `my-theme` in the `packages/local`
directory of the workspace. Let's take a look at the default contents of the custom theme
folder:

 - **"package.json"** - This is the package definition file. It tells Sencha Cmd certain 
  things about the package like its name and dependencies (i.e., the packages it requires).
 - **"sass/"** - This directory contains all of your theme's Fashion source files. The source 
  files are divided into 4 main sections:
    - `sass/var/` - Variable definitions organized by class name.
       - `sass/var/all.scss` - Global variable settings.
    - `sass/src/` - Rules and UI mixin calls using variables defined in `sass/var`.
    - `sass/etc/` - Additional utility functions or mixins.
    - `sass/example` - Used Sencha Cmd to perform image slicing for IE8/9 (do not delete). **(Classic Only)**
 - **"resources/"** - Images and other static resources.
 - **"overrides/"** - JavaScript overrides to Ext JS component classes.

The files and folders in `sass/src` and `overrides` should be organized to match the component
class name that you are styling or overriding. For example, theme code related to
[[ext:Ext.panel.Panel]] should be placed in a file named `sass/src/panel/Panel.scss`. It is
important to place mixin calls and style rules in the appropriate file based on the associated
class so that Sencha Cmd can include only the code needed by the application in a build.

The same organization can be applied to `sass/var/`. Alternatively, you may choose to just use
the `sass/var/all.scss` file if you only have a small number of variables to set. Because setting
variables does not impact the size of the generated CSS, the choice between keeping all theme
variables in a single file or splitting across multiple files organized by class name is a matter
of personal preference or project guidelines.

### Configuring Theme Inheritance
All Sencha theme packages are part of a larger hierarchy of themes. Each theme package extends
a parent or base theme. The next step in creating your custom theme is to select which theme to
extend. Ext JS ships with several themes for each toolkit:

**Modern Toolkit**
 - `theme-material` - Material Design theme.
 - `theme-ios` - iOS Theme.
 - `theme-triton` - Modern flat, borderless theme.
 - `theme-neptune` - Modern borderless theme.

<img src="images/modern_theme_chart.png"/>

**Classic Toolkit**
 - `theme-triton` - Modern theme using font-icons. Extends "theme-neptune".
 - `theme-crisp` - Minimalistic Theme. Extends "theme-neptune".
 - `theme-crisp-touch` - Crisp-Based Touch Theme. Extends "theme-crisp".
 - `theme-neptune` - Modern borderless theme.
 - `theme-neptune-touch` - Neptune-Based Touch Theme. Extends "theme-neptune".
 - `theme-classic` - The classic blue Ext JS theme.
 - `theme-gray` - Gray theme. Extends "theme-classic".

<img src="images/theme_chart.png"/>

Which theme should your custom theme extend? For the modern toolkit, we recommend using
`theme-material` or `theme-triton`, while for the classic toolkit, we recommend using
`theme-triton`, `theme-crisp` or `theme-neptune` as the starting point for custom themes
(or perhaps `theme-neptune-touch` or `theme-crisp-touch` when theming for tablets). These
themes contain all the code necessary for creating an attractive theme out of the box.

The `theme-base` and (in classic) `theme-neutral` themes should be thought of as abstract
and should not be extended directly.

In this tutorial we will create a custom theme that extends `theme-triton`. The first step
is to configure your custom theme with the name of the theme it is extending. This is done
by changing the `extend` property in `packages/local/my-theme/package.json` from its default
value to the desired value:

    "extend": "theme-triton"

Your custom theme is now configured to use the Triton theme as a base. Your custom theme starts
off as identical to the default Triton theme. In the following steps you'll make your own changes 
to begin to differentiate your custom theme.

### Building The Theme

Building the theme creates a `build` directory in your theme package directory. Inside 
`my-theme/build/resources` you will find a file named `my-theme-all.css`. This file
contains all the style rules for all Ext JS components for your theme. The built theme's
files contain all the styles for every Ext JS component and is useful for applications
that _do not use Sencha Cmd_.

**Note:** _It is not necessary to build a theme when that theme is used in a Sencha Cmd
application_. When Sencha Cmd builds an application it incorporates the `.js` and `.scss`
files needed directly from the theme's sources.

## Generate A Test Application

To rapidly develop and test our custom theme we need to host it in an Ext JS application. The
application should be setup to use the modern or classic toolkit as appropriate for your needs.
To create the application, run these commands from the workspace directory:

    $ mkdir demo-app
    $ cd demo-app

    $ sencha app init --ext65 --modern App
      -- or --
    $ sencha app init --ext65 --classic App

### Configure The Application's Theme
To configure the test application to use your custom theme, find the line that sets `"theme"`
in `demo-app/app.json` and change it to be:

    "theme": "my-theme",

### Watch The Application

Sencha Cmd has now generated an application named `App` in this sub-directory. Going forward,
we'll be making changes to the theme and sample application. We'll want Sencha Cmd to detect
these changes and automatically compile them into the output CSS used by the application. To
accomplish this, run the following command:

    $ sencha app watch --fashion

Reminder: The `sencha app watch` command requires Java JRE 1.7 or higher. If you are unable
to run `sencha app watch` you'll need to run `sencha app build --development` after each
change to the theme. For brevity, we'll assume you are running `sencha app watch`.

After running `sencha app watch` you can load your application in the browser using the URL:

    http://localhost:1841/demo-app/

The `--fashion` switch will instruct the browser to refresh the styling within the application
as you make changes to the application's theme - often in under a second!

**Note:** Live updates using `--fashion` are supported on modern browsers only. Most changes
to styling in the theme will update near real time with no browser refresh required. However,
theme changes that modify a component's dimensions may require a manual browser refresh.

## The Theme API

Ext JS Classic and Modern toolkits have the same fundamental approach to their API: they define
variables to configure the default appearance of components and they provide mixins that can
generate custom appearances. These custom appearances are assigned names of your choice and
these names are applied to component instances using the `ui` config property. Due to this
relationship to the `ui` config, these mixins are often called "UI mixins" or "theme mixins".

The names of these variables differ by toolkit, but there are some common variables like
`$base-color` that apply to both. For the complete list of variables see [[ext:Global_CSS]].

In the Classic toolkit, the `ui` config is a single string (such as `"custom"`). This string
keys to the output of the mixin call where this name was specified. In the Modern toolkit, the
`ui` config is more like a CSS class. It can be a space-separated set of names. Each name maps
to the name passed to a mixin call, but the outcome of these calls is much more composable. For
more details on the `ui` config, please consult the appropriate toolkit theme guide and API
documentation.

### Configuring Theme Variables

Let's start by modifying the `$base-color` which is a value from which many Ext JS components'
colors are derived. Due to the use of `$base-color` through the default themes, making a global
change to `$base-color` will have an effect on most all components in the Ext JS library.

Create the file `packages/local/my-theme/sass/src/Component.scss` and add the following code:

    $base-color: #317040;

The value of `$base-color` must be a valid HTML color code; see the 
[HTML Color Codes](http://html-color-codes.info/) web page.

At this time you should see the green color we specified earlier as `$base-color`
applied to the components on the screen.

**Note:** Theme variables are all defined as dynamic and so the `dynamic()` declaration
is not needed to set them (as show above). If you want to define your own variables,
however, we recommend making them dynamic:

    $my-custom-color: dynamic(red);

### Theme JS Overrides
Sometimes a theme needs to change an aspect of a component that is only configurable via
JavaScript. This is easily accomplished by adding a JavaScript override to your theme package.
To demonstrate how this is done, let's change the [[ext:Ext.panel.Panel#cfg-titleAlign titleAlign]]
config of Panels in the custom theme. Create a new file named `my-theme/overrides/panel/Panel.js`
and add the following code:

    Ext.define('MyTheme.panel.Panel', {
        override: 'Ext.panel.Panel',
        titleAlign: 'center'
    });

When you view the application in the browser you'll notice that all Panel headers have 
centered titles. Although any Ext JS component config can be overridden in this manner, best
practice is to only use overrides to change configs that affect the visual appearance (and not the
functionality) of a component.

### Modifying Image Assets
All required image assets are inherited from the parent theme by default, but in some 
cases you may need to override an image. This can be easily done by placing the desired 
image in `my-theme/resources/images/` and giving it the same name as the image it 
is intended to override from the base theme.

In many modern themes like `theme-triton` there are few if any images. These themes use
vector font icons. Therefore the images you can supplant in this way is specific to your
choice of base theme.

### Adding Custom Utilities
If your theme requires functions or mixins that are not related to component styling 
(e.g. utilities), these should be placed in the theme's `my-theme/sass/etc`
directory.

You can organize files in this directory however you like, but the only file that Sencha Cmd
includes in the build is `my-theme/sass/etc/all.scss`. Any other files must be imported
(`@import`) by the `all.scss` file. For an example that follows this pattern see
`ext/classic/theme-base/sass/etc/`.

# Styling Your Application

Styling that is not shared between applications belongs in the application itself, not in 
the theme. Sencha Cmd provides an easy way to add application-level styling by allowing you
to organize your styles right alongside your JavaScript code.

## Styling Your Application's Views

To write CSS rules associated with an application view, you create an `.scss` file in the
same folder and with the same base name as the view. For example, to style the view
`App.view.main.Main`, you may can add `Main.scss` to that folder:

    demo-app/
       app/
          view/
             main/
                Main.js
                Main.scss
                MainController.js
                MainModel.js

While the ability to add arbitrary CSS styles offers maximum flexibility, it is best to avoid
directly styling elements owned by Ext JS components. Instead these should be styled using the
Ext JS Theming API whenever possible. Using the theming API safeguards your styling against
breaking markup changes in future versions of Ext JS.

## Changing Theme Variables In Your Application
The application acts as the final level in the theme hierarchy. As such, applications can
change theme variables.

Let's continue using the `demo-app` application created above and override the theme's
`$base-color` in the application. Create the `Application.scss` file:

    demo-app/
       app/
          Application.js
          Application.scss

The `Application.scss` file is an easy option for global settings since it matches with the
global nature of the `Application` class. And add the following to this file:

    $base-color: #724289;

View the application in a browser and you will see that the base color has changed to
purple.

## Theming In An Application

To do significant theme work in an application, you should create  a `sass` folder structure
in the same manner as a theme and inform Sencha Cmd that your styles apply to all namespaces
(not just the application). The code that would normally be in the theme's `sass` folder can
then be placed in the application's `sass` folder.

### The Sass Namespace
When Sencha Cmd builds your styles, it looks at all the JavaScript classes that are used in
the application. It then includes all `.scss` files that coincide with these classes. This
process uses the `sass.namespace` to align a class name (such as `Ext.button.Button`) with
files on disk for a package, theme or application.

For example, in a theme you might have the file `sass/var/button/Button.scss` as well as the
file `sass/src/button/Button.scss`. These files will be considered matches because the default
`sass.namespace` for a theme is `Ext`.

The default `sass.namespace` for an application, however, is its own namespace (`App`). This
means Sencha Cmd will not recognize `demo-app/sass/var/button/Button.scss` as a match for the
`Ext.button.Button` class. Instead that would match `App.button.Button`. To include files that
match all namespaces, you need to set `sass.namespace` to the empty string in `app.json`:

    "sass": {
        "namespace": ""
    }

Once this change is made, Sencha Cmd will match `demo-app/sass/var/Ext/button/Button.scss` and
`demo-app/sass/src/Ext/button/Button.scss` to `Ext.button.Button`.

This also means that if you want to use the `sass` folder to organize styles for your views,
you will need to use `App` sub-folders. For example `sass/src/App/view/main/Main.scss` is the
path that will match `App.view.main.Main`. While this was the pattern in previous releases, and
is still supported, placing view styles in `.scss` files that reside next to their `.js` file (as
descried previously) is a more maintainable structure going forward.

## Organization Of Generated Styles
Sencha Cmd combines the styling from your theme, your application and from any required packages
(see the [Sencha Cmd Packages guide](../../../../cmd/guides/cmd_packages/cmd_packages.html)) when
it compiles your application. It is important to understand the way Sencha Cmd combines these
files so that you know what you can use from your theme or required packages and when these things
will be available.

The structure of the `all.scss` file is this:

    +---------------------------------------+
    | inclusion flags                       |
    +-----------+-----------+---------------+
    |           |           | base          |
    |           | theme     +---------------+
    |           |           | derived       |
    |           +-----------+---------------+
    |           |                           |
    |    etc    | packages (dep order)      |
    |           |                           |
    |           +---------------------------+
    |           |                           |
    |           | application               |
    |           |                           |
    +-----------+---------------------------+
    |           |           | base          |
    |           | theme     +---------------+
    |           |           | derived       |
    |           +-----------+---------------+
    |           |                           |
    |    var    | packages (dep order)      |
    |           |                           |
    |           +---------------------------+
    |           |                           |
    |           | application               |
    |           |                           |
    +-----------+-----------+---------------+
    |           |           | base          |
    |           | theme     +---------------+
    |           |           | derived       |
    |           +-----------+---------------+
    |           |                           |
    |    src    | packages (dep order)      |
    |           |                           |
    |           +---------------------------+
    |           |                           |
    |           | application (*)           |
    |           |                           |
    +-----------+---------------------------+

        * - Includes application styles that are placed
            next to their corresponding .js files.

Inside the bands for `sass/var` and `sass/src`, the individual `.scss` files for a given 
theme, package and the application are always ordered to match the JavaScript class 
hierarchy. For example, if the `base` theme had `.scss` files for [[ext:Ext.Container]] 
and [[ext:Ext.Component]] in its `sass/var` folder, the file for `Ext.Component` would 
be included before the file for `Ext.Container` since it extends `Ext.Component`.

The goals and rationale for this structure are as follows:

 - In `sass/etc` are utilities and the like:
   - Utilities from base themes are available to derived themes.
   - Package utilities can use facilities provided by the current theme.
   - Application utilities are able to use their theme and any required packages.
 - In `sass/var`, the concerns are variable control and derived calculation.
   - Themes come first so that they set values for their variables.
   - Derived theme can change variables since they follow their base themes.
   - Package variables are introduced in their package dependency order.
   - Applications come last so that their vars will override themes and packages.
 - For `sass/src` this order yields the proper cascade of rules so that:
   - Derived theme rules win over rules from their base theme(s).
   - Application rules cascade in last so that they always have the final authority.

### Inclusion Flags
The inclusion flag variables are a set of read-only variables defined to be `true` or `false`
for each JavaScript class that may be included. The value of this variable is `true` if that
class is being included in the application build. The variables are created dynamically by
Sencha Cmd with a prefix of `$include-` followed by the full class name with its parts 
separated by `-` instead of `.` and all in lowercase. For example, if the build uses 
[[ext:Ext.Img]], you can test for true within a custom mixin:

    @if $include-ext-img {
        // styling contingent upon the presence of Ext.Img in the app
    }

**Note:** Through most of the guide we advocate for the use of `sencha app watch` to build 
your application incrementally as changes are made to both the application and the custom 
theme. However, the `$include-` variables are all set to `true` in development (which is 
the environment `sencha app watch` operates within). In order to test your theme's use of 
`$include-` variable checks you'll need to build your application for testing or production:

    $ sencha app build --testing
    $ sencha app build --production

## Sharing A Theme Between Applications
It's easy to share the theme you've just built with a second application. Simply navigate 
to the workspace directory and run the following command (note: if you're following along
using the steps above and have `sencha app watch` running you'll first need to end it using
`Ctrl+C`):

    $ mkdir another-app
    $ cd another-app
    
    $ sencha app init --ext65 --modern (or --classic) AnotherApp

This tells Sencha Cmd to generate an app in the `another-app` directory named `AnotherApp`
and to use the same Ext JS SDK as the first app you created.

The next step is to tell the app to use the custom theme. Edit `another-app/app.json`
and change the theme to:

    "theme": "my-theme",

To ensure changes to the app and theme are picked up as you make them again change your 
working directory to the application directory and run:

    $ sencha app watch --fashion

When you view the `another-app/index.html` page in your browser you will now see a
starter app that uses the same custom theme as `App`.

# Next Steps

That covers the general concepts and common practices for all Ext JS themes. For specifics on
each toolkit, see these guides for [Theming The Ext JS Modern Toolkit](./theming_modern.html) and
[Theming The Ext JS Classic Toolkit](./classic_theming.html).
