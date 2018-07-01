#Release Notes for Sencha Test 1.0.3

Date: July 26, 2016

Version Number: 1.0.3.76

##New Features

###API (3)

- ORION-892 - Futures should have up/down/child methods to navigate component or element hierarchy

- ORION-905 - ST.future.Item should be able to return component futures (via asButton, etc) for lists of components in Modern toolkit

- ORION-906 - Grid and dataView futures should provide select/deselect/selected/deselected methods

###BrowserFarm (1)

- ORION-931 - Browser pool editor should leverage Sauce Labs and BrowserStack discovery protocols

Total: 4

##Bug Fixes

###API (1)

- ORION-795 - Click method on button future does not work in modern toolkit

###BrowserFarm (3)

- ORION-1013 - Can't add Generic Web Driver pool

- ORION-226 - Browser pool editor does not produce a proper BrowserStack configuration file

- ORION-932 - Properly display browser names, versions and platforms for Sauce Labs and BrowserStack capabilities files

###CodeEditor (2)

- ORION-916 - Go to Declaration fails to open editor tab

- ORION-927 - Code completion failing because of incorrect cursor position

###EventPlayer (2)

- ORION-555 - Special keys are recorded but not played back

- ORION-813 - Click events are not properly translated on touch device browsers

###Installer (1)

- ORION-894 - Destination not writable error at the end of installation if installing on Linux

###License (2)

- ORION-843 - Link to proxy server settings is missing in Getting Started sequence

- ORION-910 - License activation does not properly use system-defined proxy (must manually enter)

###LocalBrowser (1)

- ORION-431 - New local browser cannot be launched 

###TestRunner (2)

- ORION-690 - Connections fail using self-signed certifcates or custom AD CA

- ORION-937 - "Cannot read property 'isVersion' of undefined" error in Studio when app launched from UIWebView (PhoneGap / Cordova)

###TestRunnerGUI (4)

- ORION-1008 - Infinity loading mark on description into test runner, when xit method is used.

- ORION-717 - Sencha Studio stuck on Loading Tests

- ORION-970 - New test suites are not loaded by the browser if added after the Runner is launched

- ORION-978 - Test runner should launch local browsers using loopback address (127.0.0.1) not external address

###stc (3)

- ORION-1020 - stc throwing "Error: Couldn't connect to selenium server"

- ORION-833 - STC throws error after launching on OS X.

- ORION-955 - Wrong stc version

Total: 21

##Known Issues

###BrowserFarm (1)

- ORION-166 - Sauce Labs tunnel cannot be started automatically

###EventRecorder (1)

- ORION-63 - ST cannot play back a recorded Drag and Drop sequence

###TestRunner (1)

- ORION-561 - Test Runner does not handle all forms of Pending specs in Jasmine

Total: 3

#Release Notes for Sencha Test 1.0.2

Date: June 14, 2016

Version Number: 1.0.2.151

##New Features

###API (9)

- ORION-740 - ST.future.DataView should support modern toolkit

- ORION-767 - ST.future.CheckBox should support modern toolkit

- ORION-776 - ST.future.Grid/Row/Cell should support modern toolkit

- ORION-780 - ST.future.Button should support modern toolkit

- ORION-782 - Should provide ST.future.Select class for modern toolkit

- ORION-783 - ST.future.Component should support modern toolkit

- ORION-784 - ST.future.Field should support modern toolkit

- ORION-785 - ST.future.Item should support modern toolkit

- ORION-788 - ST.future.TextField should support modern toolkit

###CI (1)

- ORION-729 - Archive server should have an option to specify the contact port

###EventRecorder (1)

- ORION-624 - Use "name" property of form fields as identifier when recording events

###Installer (1)

- ORION-432 - Sencha Studio installer should provide an option of overriding older versions

###License (1)

- ORION-695 - License activation should support authenticated proxy servers

###Studio (2)

- ORION-632 - Context menu for files should be common to all file nodes

- ORION-864 - Studio should allow user to provide alternate proxy server settings vs those defined in the OS

Total: 15

##Bug Fixes

###API (5)

- ORION-651 - ST.textfield() should be able to type() empty string, but throws error.

- ORION-810 - ST.Version getRelease() method throw exception

- ORION-816 - ST.Element getComponent() fails for Ext JS 4/Sencha Touch

- ORION-817 - ST.item.blurred() is not working on modern

- ORION-834 - Tests are infinity running after call ST.cell/cellAt/cellBy/cellWith.

###BrowserFarm (1)

- ORION-294 - Renaming of browser is not optimal

###CmdIntegration (3)

- ORION-631 - Copies of shellwrapper.sh installed by EA/Beta breaks Sencha Test builds

- ORION-659 - Can execute App watch when Cmd Integration is disabled

- ORION-793 - App watch is not checked if service is running

###CodeEditor (1)

- ORION-755 - Code completion doesn't offer future classes after ST.

###Documentation (1)

- ORION-331 - Note Node.js dependency for CLI runner in docs

###EventPlayer (1)

- ORION-706 - Event player should default to the "getFocusEl" when a type event targets a component

###EventRecorder (1)

- ORION-621 - Event recorder does not include element in target locator for "type" events

###Installer (4)

- ORION-716 - Shortcut name incorrect on Windows - "Sencha Sencha Test"

- ORION-857 - Installer doesn't install ST to folder Applications on OS X

- ORION-861 - Unable to install Sencha Studio into 'Program Files' directory.

- ORION-894 - Destination not writable error at the end of installation

###Jasmine (7)

- ORION-237 - Inconsistent results of demo workspace

- ORION-340 - Studio ignores custom message in matchers.

- ORION-341 - Custom matchers without result message crashes test if result is false

- ORION-703 - Failed expectation message not meaningful when using Jasmine Spies

- ORION-728 - Futures and event player do not work from beforeAll or afterAll

- ORION-736 - Calling Jasmine's it() with no test fn does not treat test as disabled

- ORION-737 - Expectations in beforeAll functions are not reported

###License (4)

- ORION-597 - Prompts for "Sencha Account" should read "Sencha Forum Account" to avoid confusion

- ORION-847 - Impossible to activate Trial via provided Activation code.

- ORION-875 - Activation error "Cannot activate license: License is corrupted"

- ORION-878 - Activation trial is possible with any email 

###Misc (3)

- ORION-718 - Sencha Studio stuck on development build

- ORION-752 - Page with a "head" tag containing attributes will cause tests and event recorder to fail

- ORION-792 - Missing files for unittest in 4.x frameworks

###ScenarioEditing (3)

- ORION-770 - Default scenario path for all new scenarios created

- ORION-802 - Renaming scenario directory to an existing directory results in ENOTEMPTY

- ORION-848 - 'cacheBuster' error is observed after entering Location(URL).

###Studio (18)

- ORION-229 - Error if last opened workspace is missing

- ORION-230 - Creating a workspace / application from Studio displays red alert badges

- ORION-424 - Unable to navigate if too many tabs are open (no overflow handling)

- ORION-478 - Tabs cannot be closed until the content is edited in some way

- ORION-511 - Studio task has undefined name

- ORION-585 - Manual file system updates only work for one new file at a time

- ORION-590 - Test summary incorrectly indicates a passed result when only one test case fails

- ORION-602 - Socket hang up at createHangUpError when opening applications over HTTPS

- ORION-672 - Studio becomes unusable when entering location URL without two slashes or scheme

- ORION-674 - Swiping between 2 screenshots isn't working.

- ORION-696 - Cant create workspace or open existing one on Windows

- ORION-700 - Event recorder doesn't work after creating workspace

- ORION-701 - Hidden files and folders should not be displayed

- ORION-719 - Studio displays misleading message when connecting to Archive Server with no test runs

- ORION-743 - Test page gets wrongly cached on Safari leading to JSON errors and perpetual reload

- ORION-757 - Unclear error message if parking lot port is in use

- ORION-760 - User is not navigated from test runner to project settings when no location URL is configured

- ORION-839 - Sencha Studio is not properly closed on Linux and Windows

###TestRunner (8)

- ORION-215 - Test describe blocks are run too early - cannot use Ext or app code in them

- ORION-490 - Global variables leaks are sometimes wrongly reported due to race condition

- ORION-535 - Error when connecting to self-signed cert endpoint

- ORION-598 - Cache disable setting in test runner does not affect corresponding Ext JS loader setting

- ORION-626 - Sencha Test throws error running tests when Ripple plugin in Chrome is installed

- ORION-638 - Package test configuration requires user to specify Location (URL)

- ORION-771 - TestRunner does not show parked remote browsers with exactly matching userAgent

- ORION-772 - Player timeouts from one spec are sometimes reported under subsequent specs

###TestRunnerCLI (1)

- ORION-601 - Failed to find test scenario when running tests of packages in CLI

###TestRunnerGUI (5)

- ORION-620 - Test Runner displays non-JS files and displays wrong results for them in some cases

- ORION-641 - Changing scenario's location value has no effect in certain cases

- ORION-643 - When selecting an individual test or a group of tests, the master checkbox for the scenario should be unchecked

- ORION-653 - Newly added specs are labelled as passed even though they have never run

- ORION-738 - Test runner does not always reuse locally parked agents

###stc (2)

- ORION-791 - STC exits with error "Cannot find module 'process'"

- ORION-891 - Unable to run STC, when path to the STC contains 'space'.

Total: 68

##Known Issues

###BrowserFarm (1)

- ORION-166 - Sauce Labs tunnel cannot be started automatically

###EventRecorder (1)

- ORION-63 - ST cannot play back a recorded Drag and Drop sequence

###TestRunner (1)

- ORION-561 - Test Runner does not handle all forms of Pending specs in Jasmine

Total: 3

#Release Notes for Sencha Test 1.0.1

Date: March 2, 2016

Version Number: 1.0.1.38

##New Features

###API (2)

- ORION-571 - Should provide ST.future.Element#content() method to wait for exact markup

- ORION-572 - Should provide ST.future.Element#text() method to wait for exact textContent

###EventRecorder (1)

- ORION-126 - Provide alternate framework-specific target locators

###Studio (1)

- ORION-573 - Tree nodes with associated files or folders should have a "Reveal in Explorer/Finder" context menu item

###TestRunnerGUI (1)

- ORION-353 - Test Runner should provide a way to filter and show only failed tests

Total: 5

##Bug Fixes

###API (2)

- ORION-575 - ST.future.Element text state methods do not work with input element values

- ORION-578 - Calling ST future methods inside and() callback does not properly delay the callback's completion

###CmdIntegration (1)

- ORION-536 - Unable to generate app if Studio generated the workspace sans framework

##Coverage (1)

- ORION-582 - Run code coverage doesn't work and throws error

###Documentation (1)

- ORION-530 - Typo in documentation - future.Picker method collapsed has wrong name 

###EventRecorder (2)

- ORION-405 - Studio repeatedly creates parking pages on Linux, Win

- ORION-539 - Recorder stuck on Launching

###Installer (1)

- ORION-332 - Update license statement in installer

###License (1)

- ORION-540 - License does not persist after restart and trial version behaves like licensed one - Ubuntu, Mac

###Misc (3)

- ORION-45 - Test runner shows different result counts for folders for some browsers

- ORION-509 - Top-level disabled suites do not appear in the test runner UI.

- ORION-97 - Update can be completed when instance of Orion is running

###ScenarioEditing (1)

- ORION-487 - Libraries get wrong path when selected via file picker dialog

###Studio (9)

- ORION-217 - Many tree node icons do not propagate to their associated tabs

- ORION-459 - Two indexing processes can run at the same time

- ORION-502 - Uncaught TypeError: j.record.drop appears in ST

- ORION-544 - Settings window does not layout correctly after clearing logs

- ORION-554 - New added file has folder icon instead of file icon

- ORION-557 - Using context menu to create Jasmine suite often instead creates a Scenario node (only on Windows)

- ORION-559 - Allowed global variables are not allowed for second and next test run until restart Studio

- ORION-565 - Sencha Studio does not properly report failed archive downloads and leaves progress bar

- ORION-574 - Navigation tree gains Scenario nodes for files created outside of Studio (found by file system change notification)

###TestRunnerGUI (7)

- ORION-355 - Test selection is reset when run is stopped

- ORION-358 - Test results are additive

- ORION-392 - Test result summary is not properly reset

- ORION-457 - Studio gets stuck in "Loading Tests" state

- ORION-521 - Re-running tests will cause opening several browser tabs/windows

- ORION-538 - No visual indication when filters are enabled in the test runner

- ORION-551 - "Start App Watch?" popup is shown every time a new browser is selected

Total: 29

#Release Notes for Sencha Test 1.0.0

Date: February 16, 2016

Version Number: 1.0.0

##Bug Fixes

The following bugs were reported by the Sencha Community - a big thanks to everyone
who tried out the Beta!

- ORION-247 - Unable to configure archive server

- ORION-255 - Unable to create/open workspace using Cmd 5.x

- ORION-320 - Cannot generate Sencha Touch App

- ORION-321 - SenchaTestDemo needs some more examples with older frameworks

- ORION-351 - Testing ExtJS 4.2 app - never loads in any browser (just keeps loading)

- ORION-426 - Creating test project deletes all comments from app.json
