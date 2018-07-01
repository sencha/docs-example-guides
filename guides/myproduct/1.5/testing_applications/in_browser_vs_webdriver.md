# In-browser vs WebDriver Testing

## In-browser Testing

In Sencha Test 1.x, the specs and application code all ran together in the browser. Because of this, you could 
create Ext JS component instances directly within your specs by using the `Ext.create()` API, for example. 

You could then interact with the components and objects directly through use of the `Ext` namespace, as well as by using the Futures API.

While the same is still true for in-browser testing in Sencha Test 2.x, WebDriver tests require a different approach. 

## WebDriver Testing

Because the test and the application code do not execute together, the Futures API must be leveraged in order to communicate between the two. 

The `Ext` or application namespace cannot be referenced in the context of WebDriver tests, because it would 
be undefined (due to the tests running separately from the browser).

Instead of creating and manipulating Ext JS components directly within the spec, you would instead 
use the Futures API to locate the already existing components in your application.  You could then leverage 
the API to interact with any component or element.

In this way, WebDriver-based tests are geared towards functional testing of existing applications, as opposed to unit testing of arbitrary code.