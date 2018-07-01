# Introduction to Futures API

## The Problem

As you may know, when a dynamic web app (such as an Ext JS app) is loaded in the browser, the HTML is 
dynamically created as and when new views and components are needed. 

Ext JS also allows multiple instances of the same view to be rendered, so whenever
components are rendered to the page as HTML elements, all of the `id` properties
are dynamically generated.

Ext JS renders its components through customized `div` tags on the page, along
with wrapping standard HTML form inputs.

For example, columns from an Ext JS grid when rendered to the browser would have
HTML markup similar to this:

    ...
      <div class="x-gridcolumn x-component x-size-monitored x-paint-monitored x-resizable x-layout-box-item x-layout-hbox-item x-flexed x-stretched x-widthed" 
        id="ext-gridcolumn-1" data-componentid="ext-gridcolumn-1" 
        style="min-width: 40px; -webkit-box-flex: 1; flex: 1 1 0px;">
        <div class="x-title-el" id="ext-element-93">
          <div class="x-text-el" id="ext-element-94">Name</div>
        </div>
        ...
      </div>
      <div class="x-gridcolumn x-component x-size-monitored x-paint-monitored x-resizable x-layout-box-item x-layout-hbox-item x-flexed x-stretched x-widthed" 
        id="ext-gridcolumn-2" data-componentid="ext-gridcolumn-2" 
        style="min-width: 40px; -webkit-box-flex: 1; flex: 1 1 0px;">
        <div class="x-title-el">
          <div class="x-text-el" id="ext-element-99">Type</div>
        </div>
        ...
      </div>
    ...

In a standard testing tool, if we wanted to reference one of the grid's columns, we might
try to use the `id` of the element associated with the column, but in the example
above, you can see that the columns have an `id` similar to this:

    id="ext-gridcolumn-2"
    
This type of automated output makes it very difficult for a standard testing tool 
to reliably locate elements on the page, as identifiers will regularly change.

Other testing tools also do not have an awareness of the link between Ext JS Components
and the physical representation of that Component on the web page (the rendered HTML).

## Futures API

One of the powerful features of Sencha Test is its built-in awareness of Ext JS and ExtReact 
components, through the use of the Futures API.

The Futures API is a suite of JavaScript helper methods, that allow you to more
reliably (and easily) reference Ext JS and ExtReact components, and the items within those components, 
along with other Elements in the page.

For example, if we wanted to interact with a particular grid's row as part of a test,
we can use the following code:

    it('Should click on a row in the Assets grid', function() {
        ST.grid('assetgrid')
            .rowAt(2)
            .click();
    });
    
Using just a few simple lines of code, we are able to reference an Ext JS
grid through a particular locator (in this case, the grid's `xtype` is being used), 
and once we have a reference to it, there
are built-in methods for referencing the rows. Once we have the row, we
can simulate a user clicking on that part of the grid through the `.click()`
method.

We call all the methods in the above example **chainable methods**; this is where
we can append methods one after the other.

## Assertions

By using the Futures API, you don't usually need to make specific Jasmine assertions,
for example: 

    expect(something).toBe(something)

Instead, in the example shown in the previous section, just through the virtue of 
executing `ST.grid('assetgrid')`, if
the grid isn't located within the default timeout period (5 seconds), then
that failure will cause the associated test to fail with an error
indicating that a timeout occurred while waiting for the grid to be located.

Likewise, if there isn't a row at index `2` in the grid, then `.rowAt(2)` will
cause the test to fail, with an error indicating that the expected row
was not located.

## Handling Timing Issues

Due to the dynamic nature of frameworks like Ext JS, a
component might not have become fully rendered to the page at the point a
test is executed, or data for a grid may not have yet loaded.

The Futures API handles these timing issues for you. In the example below, if 
there is no grid matching the defined locator (`assetgrid`), then it will
wait for one to become available (within the default timeout period).

    it('Should click on a row in the Assets grid', function() {
        ST.grid('assetgrid')
            .rowAt(2)
            .click();
    });

The same logic applies for the rows within the grid. If the grid has to load 
data from a remote server, there could be a one second delay after the grid
is rendered on screen until data has been retrieved from the server and populated
within the grid. If there is no row in the grid when calling `.rowAt(2)`, 
the Futures API will wait for one to become available before proceeding to the
next action.

## Queuing Futures APIs
 
When you make use of separate `ST.` Future API calls in the same test, Sencha Test 
automatically queues and executes them in the order they're written in the test.

For example:

    it('Should click on a row in the Assets grid', function() {
        ST.grid('assetgrid')
            .rowAt(2)
            .click();
            
        ST.component('assetform')
            .visible();
    });
    
Sencha Test will queue each of the above actions, and execute them in the order shown
below. It will only move to the next action after the previous action is fulfilled.

1. Find a grid with a locator matching `assetgrid`
1. Reference the row at index `2`
1. Click on the row
1. Find a component with a locator matching `assetform`
1. Check the `assetform` is visible

Essentially the Futures API run synchronously one after the other, rather than
asynchronously where the APIs could run altogether, or in a random order.

## Failures and Timeouts

In the example shown in the previous section, if there wasn't a row located at index `2`, it would cause `.rowAt(2)`
to issue a timeout failure on that particular action. 

The `.click()` would therefore be skipped, along with all remaining actions in that test. Sencha Test would 
then move on to the next test in the test suite.

## Further Information

For more details on the inner workings of the Futures API, take a look at the [documentation for `ST.future.Element`](../../api/ST.future.Element.html).