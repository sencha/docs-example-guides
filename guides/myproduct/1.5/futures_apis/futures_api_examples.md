# Futures API Examples

This guide aims to provide some examples of how the Futures API can be used, and should help illustrate
how powerful and flexible they are when testing your web applications.

## Ext JS and ExtReact Examples

### Reveal Row in a Grid

How to use the `.reveal()` API to scroll to (reveal) a particular row in a grid.

    // URL: http://examples.sencha.com/extjs/6.5.3/examples/kitchensink/?classic#big-data-grid

    describe('Grid row reveal', function() {
        it('should scroll to a row in the grid', function() {
            ST.grid('big-data-grid')
                .rowAt(50)
                .reveal();
        });
    });

### Getting Grid Row's Record

How to get a grid row's underlying record from the Store, and assert one of the values is correct.

    // URL: http://examples.sencha.com/extjs/6.5.3/examples/kitchensink/?classic#array-grid

    describe('Grid data check', function() {
        it('should contain correct data in the row', function() {
            ST.grid('[title="Basic Grid"]')
                .rowAt(3)
                .getRecord()
                .and(function(row) {
                    // Option 1:
                    expect(row.data.record.price).toEqual(89.96);
                    
                    // Option 2:
                    expect(this.future.data.record.price).toEqual(89.96);
                });
        });
    });

### Filtering a Grid via Column Menu

How to interact with a grid column's menu, define a filter, and check the correct data is being
returned from the back end.

**Note:** WebDriver example

    // URL: http://examples.sencha.com/extjs/6.5.3/examples/kitchensink/?classic#grid-filtering

    describe('Grid filtering', function() {
        var rowCount;
        
        it('should add a filter to a column', function() {
            var driver = ST.defaultContext.driver;
            
            // This code moves the mouse over one of the column's headers which
            // shows the trigger to display the column menu
            ST.element('gridcolumn[text="Company"] => .x-column-header-text-container')
                .get('id')
                .and(function() {
                    driver.moveToObject('#' + this.future.data.id);
                });
            
            // This clicks the column header trigger which displays the column menu
            ST.element('gridcolumn[text="Company"] => .x-column-header-trigger')
                .click();
            
            // This references the column header menu and clicks the "Filters" item
            // to show the "Filters" sub-menu, then enters a value in to the text
            // field within the filter sub-menu
            ST.component('menu[activeHeader]')
                .gotoComponent('menuitem[text="Filters"]')
                .click()
                .gotoTextField('textfield')
                .focus()
                .type('Inc')
                .wait(1000);    // Filtering has a delay
            
            // Click away from the column menu to hide it
            ST.component('grid-filtering header')
                .click(); 
        });
        
        it('should find the grid and get the row count', function() {
            ST.grid('grid-filtering')
                .execute(function(grid) {
                    // This function inside of ".execute" runs in the context of 
                    // the browser.
                    // Get the number of rows in the grid by getting the Store count
                    return grid.getStore().getCount(); 
                })
                .and(function(future) {
                    rowCount = future.data.executeResult;
                });
        });
        
        it('Should check the record count', function() {
            // You could check the correct number of records are being returned
            // from your back end when the filter is applied
            expect(rowCount).toEqual(10);
        });
        
        it('Should check the dataset', function() {
            // You could check the correct records are being returned
            // when your filter is applied
            for (var i = 0; i < rowCount; i ++) {
                // Check the content of each cell as needed
                ST.grid('grid-filtering')
                    .rowAt(i)
                    .cellAt(1)
                    .textLike(/Inc/);
            }
        });
    });

### Finding a Grid Row by Record ID and Expanding the Row

How to find a grid row by record id, and expand the row.

    // URL: http://examples.sencha.com/extjs/6.5.3/examples/kitchensink/?classic#row-expander-grid

    describe('Row click', function() {
        it('should find a row with a record id of 4 and expand the row', function() {
            ST.grid('row-expander-grid')
                .rowWith('id', 4)
                .cellAt(0)
                .click();
        });
    });

### Selecting all Rows in a Grid

How to select all rows in a grid, when a checkbox selection model is being used.

    // URL: http://examples.sencha.com/extjs/6.5.3/examples/kitchensink/?classic#checkbox-selection

    describe('Grid tests', function() {
        it('should select all rows in the grid', function() {
            // Check all rows in the grid by clicking on CheckColumn header
            ST.component('grid[title="checkOnly: false"] checkcolumn')
                .click();
        });
    });

### Checking Text of a Toast Message

How to interact with an Ext JS Toast message, and check its text content.

    // URL: http://examples.sencha.com/extjs/6.5.3/examples/kitchensink/?classic#toast-view

    describe('Toast messages', function() {
        it('should show a toast message when button is clicked', function() {
            // Clicking the button shows a toast message
            ST.button('[text="Simple Toast"]')
                .click();
                
            // Reference the toast message and check its text
            ST.component('toast')
                .textLike(/Simple Toast/i);
        });
    });

## Non-Sencha Framework Examples

### Checking Table Contents

How to interact with a table using the `ST.table` Future API, finding a row by index, and checking the text content.

    // URL: http://the-internet.herokuapp.com/tables

    describe('Table tests', function() {
        it('should find the correct values in the table', function() {
            // Find a row by index, and check text content of a cell
            ST.table('@table1')
                .rowAt(1)
                .cellAt(0)
                .textLike('Smith');
        });
    });

### Getting Attribute of an Element

How to reference an Element in the page, and retrieve/check some of its attributes.

    // URL: http://the-internet.herokuapp.com/login

    describe('Login form', function() {
        it('should have correct attributes on the form element', function() {
            // Example 1: get "action" attribute of HTML form
            ST.element('@login')
                .get('action')
                .and(function() {
                    // Do something with the attribute value here
                    expect(this.future.data.action).toContain('/authenticate');
                });
                
            // Example 2: check "method" attribute of HTML form
            ST.element('@login')
                .expect('method').toBe('post');
        });
    });