# Locators

When a web application is loaded in the browser, there are two different
layers of items you can reference during a test:

1. Components (Ext JS / ExtReact)
1. Elements

**Components** are the physical Ext JS or ExtReact objects, such as a grid, or a combobox. When 
you have a reference to a component like a grid, you can easily reference its
properties and child items such as its title, rows, and docked items like toolbars and 
buttons.

**Elements** are the representation of those components in the browser - the HTML
markup you see in the page. When you have a reference to an element, there is no
real context about what that element represents. It's most likely just a `div` in
the page, so it's not easy to reference grid rows and toolbars from that layer. If no
Sencha framework is being used, you would only be working with the Elements layer.

In order to make use of the Futures API, you need to know how to locate 
components and elements.

## Types of Locators

Elements and Ext JS components can be referenced through different **locators**.

A locator is a type of selector, similar to a CSS selector, that tells Sencha 
Test how to reference a component or element. The Futures API supports the 
following different locator strategies for components and elements:

- Components:
  - Component Query
  - Composite Query
- Elements:
  - At-Path
  - XPath
  - DOM Query

For Ext JS and ExtReact apps, you will mostly make use of the Component Query or Composite locator, but
we will discuss each of these below, and show some example syntax.

## Components

In an Ext JS or ExtReact application, Component Query or Composite Query is usually
used.

### Component Query

This is the most commonly used locator strategy. It
is a feature provided by the Ext JS and ExtReact frameworks that can locate components of the 
application. Component Query syntax is similar in style to DOM Query.

Component Query is described in-depth [within the Ext JS documentation](http://docs.sencha.com/extjs/6.5.3/classic/Ext.ComponentQuery.html), 
but we'll cover some examples here:

#### Referencing by "xtype"

In Ext JS, `xtype` refers to the component's type. Each of the out-of-the-box
components in Ext JS has an `xtype`. When you browse the Ext JS documentation, 
when you look at the docs for [Grid](http://docs.sencha.com/extjs/6.5.3/classic/Ext.grid.Panel.html) 
or [ComboBox](http://docs.sencha.com/extjs/6.5.3/classic/Ext.form.field.ComboBox.html),
you'll notice the `xtype` of that component is listed at the top. Sometimes a 
component may have more than one `xtype` alias listed.

For example, the Grid has these possible `xtype` values:

    grid

or
    
    gridpanel

If there is more than one matching component (more than one grid), you need to make the locator
more specific, so it only matches one component.

Developers often set custom types for their own components within applications. For
example, if a developer has created a grid of users, they may decide to give
that grid an `xtype` of `usergrid`, or similar. So you can also reference custom
types that may have been specified by the development team:
  
    usergrid

#### Referencing by "id" or "itemId"

In general, it's bad practice for developers to set the `id` on Ext JS
components, as this causes issues when trying to create multiple instances
of that component on the page. `itemId` is much more commonly used, as this
doesn't cause such conflicts.

Using the following syntax enables you to reference a component by its
`id` or `itemId`:
  
    #userGrid
  
This can be combined with `xtype`, so in the case of the following example,
a grid that has an itemId of `userGrid` is returned:
  
    grid#userGrid

### Composite Query
    
You can combine Component Query and DOM Query in a "Composite Query" by using 
the `=>` to separate the two pieces.
    
For example:

    #myComponent => div.content

This locates the child `div` element with class `content` inside the component 
with an `id` or `itemId` of `myComponent`.

## Elements

If you have a web app that doesn't make use of a dynamic framework
like Ext JS, then Element selectors are very useful.

### At-Path

Locators that start with the `@` character are called "at-paths". The 
first token of an at-path is an element ID. Following the first token is 
a slash-delimited sequence of tag names and offsets, similar to XPath. 

For example:

    @some-div/span[2]

This identifies the 2nd "span" element that is an immediate child of 
the element with the id "some-div". 

The equivalent XPath expression would be:

    //[@id="some-div"]/span[2]

The primary advantages of at-paths over XPath are compactness and speed. 
This is because an at-path uses `getElementById` followed by a simple path 
based on tag names. Because at-paths are inherently based on IDs, they 
will be most useful in applications that assign meaningful IDs to their 
elements.

### XPath

XPath is probably the most powerful supported locator syntax. Sencha Test 
uses the [document.evaluate](http://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathEvaluator-evaluate) 
method of the browser, but also a [polyfill](https://github.com/google/wicked-good-xpath) 
when this method is not present.

In addition to attribute matching, XPath can also navigate upwards, 
unlike CSS selectors. 

For example:

    //[id="some-div"]/..

The above XPath selects the parent node of the node having ID of "some-div".

**Note:** Sencha Test requires that all XPath locators start with a slash 
character. Typically XPath locators will begin with "//" (as shown above) 
so that matches do not start at the document root.

Some useful resources on XPath:

- [DOM XPath Specification](http://www.w3.org/TR/DOM-Level-3-XPath/xpath.html)
- [XPath and CSS Selectors](http://ejohn.org/blog/xpath-css-selectors/)

### DOM Query

The DOM Query, or CSS Selector, is perhaps the most familiar locator syntax 
supported by Sencha Test. To differentiate DOM Query locators from the 
Component and Composite Queries (discussed above), a DOM Query starts 
with `>>` or `=>`.

The above paths would be approximated by the following DOM Query:

    >> #some-div > span:nth-child(2)

This is only approximately the same because nth-child() does not require 
the first child to also be a span.
