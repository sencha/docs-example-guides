# Sencha Test Overview

Sencha Test is a critical piece of the Sencha Platform that helps developers and test
engineers achieve new levels of quality in their applications while providing a much-needed
productivity boost throughout the testing effort. Sencha Test does this by bringing together
the best Open Source testing libraries (such as Jasmine, WebDriver and Istanbul), adding
the missing pieces and integrating everything in one comprehensive solution.

## Product Components

Sencha Test consists of two applications: **Sencha Studio** (for the GUI) and **stc** or
"Sencha Test Command" (for the command line). Both applications provide the ability to execute
tests, however, Sencha Studio provides a graphical, interactive test runner while stc provides
a scriptable test runner suitable for unattended use in Continuous Integration (CI) systems
such as Jenkins or TeamCity. These applications also collaborate to provide powerful test
result archiving and reviewing capabilities that go beyond the build logs and linear views
provided by the CI.

### Sencha Studio

![Sencha Studio](images/sencha-studio.png)

Sencha Studio uses a *Workspace* to organize tests as either a stand-alone project (when
application code is unavailable) or alongside the applications and packages they support.
Sencha Studio can integrate with your Sencha Cmd applications as well as with applications
that do not use Sencha Cmd.

You can write tests directly in Sencha Studio using its built-in text editor, or you can
use your own preferred IDE or text editor. Sencha Studio's text editor offers code completion
and assistance that is aware of Jasmine (the test framework included in Sencha Test) and
the Sencha Test API.

Tests, like application files, are typically kept in a version control system (such as Git,
Subversion, etc.). This is true even in a stand-alone test project for backup and team
collaboration reasons.

### Interactive / GUI Test Runner

The cornerstone of Sencha Test is its test runner, which makes the interactive test runner
the most essential component of Sencha Studio. The test runner is designed to be used during
all phases of development. This iterative process helps developers deliver robust applications
because each piece can be easily tested as it is being built.

![Sencha Test Code Coverage](images/sencha-test-results.png)

The test runner allows the developer or test engineer to select specific tests, execute
them in parallel against multiple browsers and see the results in real-time.

### Unattended / CLI Test Runner

Once the tests are in source control, they can be run unattended in a CI system using the
Sencha Test Command (stc). The test configurations, displayed and edited by Sencha Studio,
are seamlessly used by the command-line test runner. This combination of a CI and stc
enables test runs to be easily triggered by changes in source control, or on a regular cycle
such as every night.

Tests run at the command line use WebDriver to manage the required browsers. Sencha Test
supports the use of a local WebDriver hub as well as connecting to a cloud-based provider
such as Sauce Labs or BrowserStack.

Test results are captured by the CI using stc's various output options and can also be uploaded
to the Sencha Test Archiver. Using Sencha Studio, archived test results can be reviewed using
the same graphical format as the interactive test runner.

### Sencha Test Archiver

The Sencha Test Archiver is a Node JS-based web server provided by stc. The archiver (or
"archive server") is typically installed on a designated machine in the CI environment. A
single archive server can be configured to handle any number of teams and projects.
Alternatively, multiple archive servers can be installed as needed.

## Key Features

Beyond the test runner, Sencha Test provides a number of important features designed to
make testing simple and productive.

### Test Management and Configuration

Sencha Studio streamlines the setup and configuration required to get started writing and
running tests. This starts with the *workspace* as the organizational root and continues
with the configuration of *Test Projects* and *Test Scenarios*. Sencha Studio allows
developers to configure all aspects of the test run from the location of the test subject,
to the inventory of tests and the various run-time options. All of these settings can be
verified in the interactive test runner before moving on to the CI system.

#### Browser Farm Integration

Maintaining the vast number of browser combinations required for real-world testing is not
always possible or desirable. Sencha Test comes with out-of-the-box support for browser farms
like Sauce Labs and BrowserStack so developers and test engineers do not have to become IT
specialists in order to run their tests. These solutions can also drastically reduce test
execution time, as tests can be run simultaneously on multiple browsers with minimal effort.

### Test API

Sencha Test understands Sencha Frameworks. The Sencha Test API provides numerous features
to minimize the effort required to test Ext JS and Sencha Touch applications. While most
test frameworks (including Jasmine) are synchronous by nature, Sencha Test provides an API
family called the "Futures API's" that recognize the asynchronous nature of GUI testing.

Using the Futures API, complex sequences of GUI interactions can be expressed in a simple,
compact way. Under the hood, Sencha Test ensures that the steps of the test are properly
scheduled without assistance from the test author in typical cases. For example:

    ST.grid('#userGrid').               // locate a grid via component query
        rowWith('firstName', 'Bill').   // and select the row w/matching field
            cell('lastName').           // then select a cell given a column id
                reveal().               // scroll to this cell
                textLike('Preston');    // -> wait for the text to match a pattern

If the cell does not have the desired text within a timeout period (which can be set
to 0), the test will fail.

The Futures API provides many more Ext JS Component-aware methods as well as API's for
dealing with primitive DOM elements. Validation logic can be easily added to the sequence
of events and custom wait conditions can be inserted with equal simplicity.
                
### Event Recorder

Using Sencha Studio's built-in text editor, users can launch the Event Recorder to
quickly record and insert a sequence of events directly into their tests.

The Event Recorder will launch the application, run the current test and then record the
stream of events as the user interacts with the application. These events can be edited
and filtered before being inserted into the test.

Using the Event Recorder can save significant time getting test cases started. The recordings
can be run without modification to ensure no errors were generated or they can be extended
with custom expectations or assertions to ensure the correct information is displayed.

### Result Review

When test run results are saved to an archive server, Sencha Studio can download these
results and display them in the same format as the interactive test runner: organized by
folder (vertically) and by browser (horizontally). This format is much more time efficient
than finding failure patterns by reading CI build logs.

Beyond the pass/fail types of results, however, Sencha Studio allows developers and test
engineers to review visual test results as well as code coverage.

#### Visual Screen Comparison

Sencha Test also provides a simple means to verify correct application state by capturing
screenshots and comparing them to a baseline. This is as simple as calling the `screenshot()`
method at the appropriate time. The baseline (or expected) image is automatically established
the first time the test is run. Subsequent test runs will produce test failures if the
screenshot does not match the established baseline.

While computational tests are faster and typically preferred when they can be used, visual
tests are at times the only way to test certain aspects of an application. For example,
the outcome of CSS rules that set things such as color or text alignment, as well as highly 
visual components like charts.

Screenshots are captured during unattended test runs (via stc) using WebDriver. These are
compared to the baseline obtained from the archive server and the results are stored in the
archive server for later review in Sencha Studio. Sencha Studio is also able to update the
baseline should the correct answer change over time.

#### Code Coverage 

Sencha Test contains an integrated version of Istanbul, a leading JavaScript code coverage
tool, with which you can identify the gap in the amount of code that you have covered and
not covered with your tests. Leveraging this integration, Sencha Test provides a detailed
breakdown to the level of Statements, Branches, Functions, and Lines in a readable format
with percentage analysis.

Using the code coverage report is a great way to reduce project risk due to critical code
not being properly tested.

![Sencha Test Code Coverage](images/sencha-test-code-coverage.jpg)

## Conclusion

For instructions on installing and getting started with Sencha Studio refer to the 
[Sencha Studio Installation &amp; Setup](sencha_test_installation.html) guide.  If you 
have further questions, concerns, or bug reports, please visit the 
[Sencha Test forums](https://www.sencha.com/forum/forumdisplay.php?144-Sencha-Test).
