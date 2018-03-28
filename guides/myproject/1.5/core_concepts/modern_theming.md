# Ext JS Modern Toolkit Theming Guidelines

In this guide, we're going to walk through the changes to theming introduced with the modern toolkit in 
Ext JS 6.2.  There are a lot of exciting new changes that provide for easier theming, dynamic updating, 
and much more!  Along with these updates come some new concepts that you should be aware of.

Let's talk about the conventions and best practices for theming in the modern toolkit.

## Dynamic Variables

All variables are defined using the `dynamic()` indicator. This ensures that the last variable declaration wins 
and remains valid throughout the entire scope.  Additionally, variables may then derive from one another without 
concern for ordering.  

For example:

    $calendar-days-time-color: dynamic($color);

## File Naming

All non-rule-generating code are placed in the theme's `sass/var/` directory in a file matching the Component's 
class name. This is generally going to include all component variable and UI mixin declarations.  

Since all `var` files are included in the build regardless of whether or not the corresponding class is actually 
required, this allows variables to freely derive from any other variable. Including mixins in the `sass/var/` 
directory ensures that a derived theme can override those mixins before they are called by any code in the `sass/src/` 
directory.

All rule-generating code is located in the theme's `sass/src/` directory in a file matching the Component's 
class name.  This includes calls to UI mixins and rules not contained inside the body of a mixin.  

At build time, `src` files are only included if the corresponding Component is required. This ensures that 
only the rules needed are included in the CSS output.

## Base Styles vs. Configurable Styles

Layout-specific styles and styles related to the core functionality of a Component are placed in the
`theme-base/sass/src/` folder in a file matching the Component's class name. The properties set in these rules
are not configurable using variables, as changing them would likely break the functionality or layout of 
the Component. 

Examples of CSS properties that are generally not configurable are:

 * display
 * visibility
 * position
 * overflow
 * z-index

Configurable styles not related to the core functionality or layout of a component are controlled using 
variables. These variables are defined in an `scss` file matching the component's class name in 
the `theme-neptune/sass/var` directory.  The rules that use these variables are contained in a UI mixin in the 
same file. 

Examples of commonly configurable styles are:

 * background-color
 * color
 * padding
 * border-radius
 * font-size

The Neptune theme is the base for all other themes and contains the theming capabilities supported by the 
framework even though it may not utilize them all itself. 

Themes derived from `theme-neptune` do not typically define new UI mixins or create their own CSS rules. Instead,
they simply set the values of variables defined in `theme-neptune`.

## Variable Naming Conventions

Component variables begin with an xtype, and end with the CSS property name being styled, for example:

    $button-font-family: dynamic(helvetica);
    $button-color: dynamic(#fff);
    $button-background-color: dynamic(red);

If the component has various states such as hovered, focused, and pressed, the name of the state comes immediately 
after the xtype, but before the CSS property name:

    $button-hovered-background-color: dynamic(blue);

If the component has variables that control the styling of sub-elements, the name of the sub-element being styled 
are included after the xtype and state (if present).

For example, when styling the button's "badge" element:

    $button-badge-color: dynamic(#fff);
	$button-hovered-badge-color: dynamic(green);

If the "state" refers to a sub-element's state, it comes after that element's name. For example, if a tab has 
a close icon that has a separate hover state from the tab:

    $tab-close-icon-hovered-background-color: dynamic(red);

Components have separate variables for border-width, border-color, and border-style, and all three properties 
accept either a single value or a list of values so that 4 sides can be specified separately if needed:

	$button-border-color: dynamic(red yellow green blue);
	$button-border-width: dynamic(1px 3px);
	$button-border-style: dynamic(solid);

Variables use the following names to indicate component state:

 * "pressed" when the component is being pressed by the user or is in a pressed state
 * "pressing" if the component has a "pressing" state that is separate from "pressed"
 * "hovered" when the mouse pointer is over the element
 * "focused" when the element has focus
 * "disabled" when the component is disabled.

Since "focused" can sometimes be combined with other states components may provide variables that indicate a 
combination of states, for example: 

    $button-focused-pressed-border-color

## Normal and Big Modes

Each theme has two modes of sizing: normal and big. Big mode increases spacing and sizing to be more touch-screen 
friendly. Themes select whether or not to use big mode by inspecting `Ext.platformTags` in the 
theme's`overrides/init.js` and adding a CSS class name of `x-big` to the `<html>` element on the page. For example, the 
Triton theme only enables big mode when loaded on a phone, otherwise, it uses normal mode.

    Ext.theme.getDocCls = function() {
    	return Ext.platformTags.phone ? 'x-big' : '';
	};

Variables that set properties affecting visual size of a component, like font-size, line-height, and padding
have big counterparts. Big variables always have the `-big` suffix appended to the end:

    $button-padding: dynamic(1rem);
    $button-padding-big: dynamic(1.2rem);

CSS rules target big mode using the .x-big selector:
    
    .#{$prefix}button {
        padding: $padding;
    
        .#{$prefix}big & {
            padding: $padding-big;
        }
    }

## Component UIs

Most components have a UI mixin for generating multiple visual renditions of that component. These mixins are
named `[xtype]-ui`. For example `button-ui` or `panel-ui`.

UI mixins have a parameter for each of the component's global variables.  Additionally, the parameter names 
are the same as the global variable names.  The only exception is that the mixin parameters do not contain 
the xtype in their names. 

For example, a global variable named `$button-border-radius`, would correspond to a parameter of the `button-ui` mixin 
named `$border-radius`.

The parameters to the UI mixin default to `null` and do not produce any output if unspecified by the caller. This
means that when the mixin is invoked, it produces a set of styling that represents a delta from the default UI. This
minimizes the number of CSS rules required to create new UIs since the mixin automatically eliminates any `null`
values from the output.

The styling for the default UI is applied using CSS class names that do not contain a UI name.  For example, 
`x-button`, not `x-button-default` for example. This is the key to minimizing the number of rules required to create
additional UIs.  For instance, all buttons will have the `x-button` class in addition to one or more optional
`x-button-[ui]` classes. It allows the default UI to serve as a base set of styles for all other UIs.

To generate additional UIs, invoke the mixin passing only the parameters that are different from the default UI. 
For example, the following mixin call generates a UI named "action" that builds upon the default UI by changing the 
background-color to `red`, but inherits all other properties from the default UI via the cascade. The output from this 
UI invocation is minimal.  It only contains the rule or rules needed to set the background-color, nothing else.

    @include button-ui(
        $ui: 'action',
        $background-color: red
    );

## Derived UIs

Subclasses of Components that have UI mixins typically have their own UI mixin and a complete set of global 
variables for configuring that mixin.

Subclass variables that do not have different default values from the superclass variables will be `null`.
This ensures that they will inherit the proper values via the parent CSS class rather than  redefining a
redundant value.

Components use `classCls` set to `x-[xtype]` to accomplish this inheritance (See section 
below on CSS class names). 

An example of this pattern is the grid pagingtoolbar component that extends toolbar:

    // theme-neptune/sass/var/grid/plugin/PagingToolbar.scss
    $pagingtoolbar-background-color: dynamic(null);
    
    @mixin pagingtoolbar-ui(
        $ui: null,
        $xtype: pagingtoolbar,
        $background-color: null,
        $prev-icon: null
    ) {
        $ui-suffix: ui-suffix($ui);
    
        // Call base toolbar mixin.
        // Only produces output for non-null parameters
        @include toolbar-ui(
            $ui: $ui,
            $xtype: $xtype,
            $background-color: $background-color
        );
    
        // paging toolbar specific styles
        .#{$prefix}#{$xtype}#{$ui-suffix} {
            .#{$prefix}icon-prev {
                @include icon($prev-icon);
            }
        }
    }

    // theme-neptune/sass/src/grid/plugin/PagingToolbar.scss
    @include pagingtoolbar-ui(
        $background-color: $pagingtoolbar-background-color;
    );

## Configuring Theme UIs in Derived Themes

Additional UIs provided by a theme are typically not configurable via global variables or at least not
overly configurable. Instead, these UIs are wrapped in a mixin of their own, which can be overridden by
derived themes to change the parameters:

    @mixin button-action-ui() {
        @include button-ui(
            $ui: 'action',
            $background-color: red
        );
    }

Themes provide a single variable for each additional UI that defaults to "true" but can be overridden to "false" 
to disable generation of the UI. This variable will have the same name as the corresponding mixin:

    @if $button-action-ui {
        @include button-action-ui;
    }

## Composable UIs

UIs are generally composable. For example if two separate button renditions are required, a red "action" 
button, and a rounded red "action" button, simply create an "action" UI and "round" UI:

    // sass/var
    $button-action-ui: dynamic($enable-default-uis);
    $button-confirm-ui: dynamic($enable-default-uis);
    
    @mixin button-action-ui() {
        @include button-ui(
            $ui: 'action',
            $background-color: red
        );
    }
    
    @mixin button-round-ui() {
        @include button-ui(
            $ui: 'round',
            $border-radius: 10000px
        );
    }
    
    // sass/src
    @if $button-action-ui {
        @include button-action-ui
    }
    
    @if $button-round-ui {
        @include button-round-ui
    }

To compose UIs, simply use any number of UI names, space separated, in your component config:

    ui: 'action round'

If multiple UIs set the same properties, the winner is the last one in the cascade, i.e. the one whose mixin was 
invoked last. Composable UIs typically strive to limit their area of concern to separate aspects of styling
(colors, sizing, border-radius, etc), so that there is little ambiguity when combining them.

Using composable UIs ensures that the generated CSS code remains very DRY, by avoiding unnecessary duplication of 
CSS rules. In the example above, we avoid duplication of the background-color rules for every UI that may optionally 
need roundness.  Any UI can be combined with the "round" UI to add roundness.

## CSS Class Names

It is important to maintain consistency in naming CSS classes since they they play a major role in adding semantics 
and structure to the DOM elements that are generated by Components in the framework. This consistency of naming serves 
two purposes:

1. It improves the readability and maintainability of SASS code and reduces the chance for error.
2. For users who do not use the API, it provides a clear and understandable DOM structure for styling.

## Main Element and UI CSS Classes

Components have a class name of `x-[xtype]` on its main element. For example, a Text Field component will
have a CSS class name of `x-textfield`.

There are two possible ways for Components to set this main CSS class. They can either set `classCls` or `baseCls`
on the body of their class definition, though `classCls` is preferred. Setting either of these will add the CSS
class to the main element and use it as the prefix for UI-specific class names that are also added to the main
element. The `classCls` and `baseCls` configs only differ in their inheritability. `classCls` is inherited by
subclasses and is additional to the `classCls` of those subclasses, whereas `baseCls` is not. 

Additionally, when using `classCls` a UI-specific CSS class name will be added for each and every `classCls` in the 
class hierarchy. For example, an `Ext.field.Password` component with a "ui" set to `foo` would have the following 
UI classes:

 * x-passwordfield-foo
 * x-textfield-foo
 * x-field-foo

This pattern ensures that styling is correctly inherited through the class hierarchy and allows Components to 
only provide styling for the functionality that they add. For edge cases where inheriting styling is not desired 
Components may set `classClsRoot:true` to prevent inheritance of `classCls` from ancestors.

## Reference Element CSS Classes

Reference elements follow the pattern `x-[referencePrefix]-el`. For example the `bodyElement` reference element 
of a form field will have the CSS class `x-body-el`.  For consistency, element references will have the 
Element suffix on the JavaScript side. The `-el` suffix on the CSS class name helps to differentiate the reference 
element from a potential Component with an xtype of the same name.

## CSS Classes for Component Configuration and State

CSS class names that reflect Component configuration follow the pattern `x-[configName]-[configValue]`, and 
are placed on the Component's main element. For example a form field with a `labelAlign: 'left'` config 
has a CSS class name of `x-label-align-left` added to the main element.

CSS class names for boolean configs generally follow one of two patterns:

1. Truthiness causes a new class to be added. For example, a checkbox with a checked config would have an `x-checked` 
CSS class when the value is true, but would not have the class when false.

2. Falsiness causes a new class to be added. This is sometimes useful when the default value is `true`, and the component 
needs needs additional styling only in the falsey state. For example, the List component has an `x-no-row-lines` 
CSS class when `rowLines` is configured as `false`.

Likewise, class names that reflect Component state follow the pattern `x-[state]`, and are placed on the
Component's main element . 

For example, a button that is in pressed state would have the class `x-pressed` on its main element.

Setting Component state and configuration CSS classes on the main element, rather than on a reference element, allows 
the state or configuration to be scoped to the Component.  This is true even if the classes only affect the styling of 
a child element or elements. This also results in a more stable DOM structure as these class names do not change 
location even if the internal dom structure is modified.

## CSS Selectors

Since reference, config, and state CSS classes do not contain xtype info in their name, they must be used in combination 
with the Component's `classCls` or `baseCls` to avoid colliding with other Components that may have the same config or 
state class name. For example to style the pressed state of a button's main element, one would use the following 
selector:

    .x-button.x-pressed

UI mixins use UI-specific CSS class names in combination with reference, config, and state CSS classes. For 
example if the ui of a button is 'foo', one would style the pressed state as follows:

    .x-button-foo.x-pressed

## Child vs. Descendant Selectors

When styling a component's inner elements, descendant selectors such as `.x-foo .x-bar` should be preferred over direct 
child selectors like `.x-foo > .x-bar`. This allows for much more flexibility in the markup and allows it to 
tolerate more change, such as the insertion of a wrapping element in between x-foo and x-bar without potentially 
breaking the styling. 

The only exception to this rule is when there is the potential for nesting. For example, a panel might use a selector 
such as `.x-panel > .x-body-el` in order to only style its own body element, and not the body elements of other panels 
nested within it. In some cases, when there are a varying number of dom elements in between the container element and 
it's child, UI-specific class names are added to the child element.

An example of this is `Ext.Container`. It adds a UI-specific class for each `classCls` to its `innerElement` because 
there can be a varying number of DOM ancestors in between the `innerElement` and the element depending on whether or not 
the container has docked items.
