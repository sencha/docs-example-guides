# Requiring Node Modules

For those familiar with Node.js, you will be used to leveraging the `require` capability to require other classes or Node Modules.

In Sencha Test 2.1+, it is possible to leverage the `require` capability within WebDriver test suites,
to require your own classes or other pre-installed Node Modules.

This significantly increases the power of testing your apps because you will be able
to leverage thousands of available packages to quickly and easily extend the capabilities of Sencha Test, 
for example by looping through data in an Excel spreadsheet using 
[exceljs](https://www.npmjs.com/package/exceljs), or 
looking up data from a SQL Server database using [mssql](https://www.npmjs.com/package/mssql).

## Usage

### Requiring Local Files

To require a local file in a WebDriver test suite, you can do the following:

1. Create a `.js` class file under the Scenario's "lib" folder:

        module.exports = class MyClass {
            doSomething() {
                // Do something here
            }
        }; 

2. Require the class in your test suite:

        var MyClass = require('./lib/MyClass.js');

### Requiring Packages

To require a package in a WebDriver test suite, you can do the following:

1. Run `npm init -y` within the root of the `test` folder. This will make the `test` folder a package, with its own `package.json`. This only needs to be done once for the test project.

2. Run `npm install <package_name>` at the `test` folder. The package will be installed to the `node_modules` 
folder within `test`, and the `package.json` will have the specified package added as a dependency. For 
example:

        npm install exceljs

    **Note:** If you want to leverage an existing globally installed package, you will need to link the 
    package, rather than installing it:

        npm link exceljs

3. Require the package in your test suite:

        var ExcelJS = require('exceljs');

## Examples

Here are some examples.

### Requiring a Local File

This example demonstrates creation and use of a class that contains a test suite to handle the login screen 
of an application.  This class can then be required by any test suites that need to handle login 
functionality, rather than replicating these steps in multiple test suites.

1. Create a new WebDriver scenario, using this URL:

        http://examples.sencha.com/extjs/6.5.3/examples/classic/ticket-app/index.html

1. Create a custom class, inside of which is a `login` method containing a test suite
to handle the login screen of an application.  This file will be created within the Scenario's `lib` folder:

    `lib/LoginHelper.js`:

        'use strict';

        module.exports = class LoginHelper {
            login() {
                describe('Login', function() {
                    it('should login to the app', function() {
                        ST.textField('[name="username"]')
                            .setValue('Dan');
                            
                        ST.textField('[name="password"]')
                            .setValue('test');
                            
                        ST.button('[text="Login"]')
                            .click();
                    });
                    
                    it('should show the dashboard after logging in', function() {
                        ST.panel('app-dashboard')
                            .visible();
                    });
                });
            }
        }; 

1. Create a test suite which requires the `LoginHelper` class:

        describe('Example', function() {
            var LoginHelper = require('./lib/LoginHelper.js'),
                loginHelper = new LoginHelper();
            
            // Run the login test suite
            loginHelper.login(); 
            
            it('should contain data in the tickets grid', function() {
                ST.grid('[reference="activeTickets"]')
                    .rowAt(2);
            });
        });

1. Run the scenario, and the tests should pass.

### Requiring a Package

This example demonstrates usage of the `exceljs` package, for comparison of data from an Excel spreadsheet
with data being displayed in an Ext JS grid. 

1. Create a new WebDriver scenario, using this URL: 

        http://examples.sencha.com/extjs/6.5.3/examples/kitchensink/?classic#actions-grid

2. Install the `exceljs` package by following the "Requiring a Package" steps above.

3. Create a Microsoft Excel `.xlsx` file in the following folder path:

        /<scenario_folder>/lib/data/LookupData.xlsx

4. Populate the spreadsheet with the following data:

| Company | Price | Change | % Change | Last Updated |
|---------|-------|--------|----------|--------------|
| Roodel  | 59.47 | 1.23   | 2.11     | 10/08/2018   |
| Voomm   | 41.31 | 2.64   | 6.83     | 10/18/2018   |
| Dabvine | 29.94 | 3.55   | 13.45    | 10/11/2018   |

5. Create a test suite with the following code:

        describe('Spreadsheet', function() {
            var ExcelJS = require('exceljs'),
                worksheetData;
            
            beforeAll(function(done) {
                var workbook = new ExcelJS.Workbook();
                
                // Strip off test suite file name from folder path
                contextPath = contextPath.substring(0, contextPath.lastIndexOf('/'));
                
                // Read the Excel file
                workbook.xlsx.readFile(contextPath + '/lib/Data/LookupData.xlsx')
                    .then(function(file) {
                        // Get worksheet values
                        worksheetData = file.getWorksheet(1).getSheetValues();
                        
                        // Remove first row (contains column/field names)
                        worksheetData.splice(0, 2);
                        
                        done();
                    })
                    .catch(function(error) {
                        fail('Unable to read Excel file, with the following exception: ' + error);
                    });
            });
            
            it('Should match the data from the spreadsheet', function() {
                var grid = ST.grid('[title=Actions Grid]'),
                    rowIndex = 0;
                
                // Loop through Excel worksheet rows, and compare text with grid row's cell content
                for (var row of worksheetData) {
                    // Company
                    grid.rowAt(rowIndex)
                        .cellAt(0)
                        .textLike(row[1]);
                    
                    // Price
                    grid.rowAt(rowIndex)
                        .cellAt(1)
                        .textLike(row[2].toString());
                    
                    rowIndex ++;
                }
            });
        });

        // This is needed to obtain the full folder path of this test suite. This has to be placed here.
        var contextPath = module.id;

6. Run the scenario, and the tests should pass if the data from the spreadsheet matches what's shown
in the grid.