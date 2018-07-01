# Release Notes for Sencha Test 2.2.0 

**Date:** May 30 2018  
**Version Number:** 2.2.0.148

###  New Features, Enhancements and Bugfixes

###  API

+ ORION-2074	itemAt not working correctly with modern infinite lists in Ext JS 6.5.0+

+ ORION-2207	ST scripts don't load in Internet Explorer version 9 mode

+ ORION-2235	Add Custom Strategy to Core API

+ ORION-1726	PivotGrid rowAt() will not work for grids with a large number of rows and buffered rendering

+ ORION-2052	ST.future.Element.expect() retrieves value from textfield too early after type()

+ ORION-2072	Add displayValue() method for ComboBox

+ ORION-2136	"node.up is not a function" fail is observed, when you use rowWith()

+ ORION-2210	WebDriver doesn't load ST scripts synchronously

+ ORION-2269	reveal() does not always scroll items into view when used multiple times

+ ORION-2088	Add Futures API for Slider

+ ORION-2103	Add HTML Table API

+ ORION-2233	Row/Cell indexes should not depend on "grouping" within table

+ ORION-2234	Row/Cell xpath queries don't start from correct context node


###  Code Tree

+ ORION-2046	Implement new styling for Code Tree

+ ORION-2047	Add "table of contents" for Code Tree structure

+ ORION-2105	Disable Tree view button for non .js files

+ ORION-2117	Code completion not turned on when using tree view

+ ORION-2166	Code Editor not available on error

+ ORION-2169	Functions in test files duplicate items in Code Tree

+ ORION-2171	Uncaught error thrown to log when editor fails to show code tree

+ ORION-2096	Scroll tree items into view when selected

+ ORION-2097	Add indication that "done" needs to be used when async is true

+ ORION-2115	Add search for nav tree

+ ORION-2134	System error when switching to Tree view

+ ORION-2144	Move async checkbox to editor

+ ORION-2165	Error banner not dismissed between loads of code tree

+ ORION-2175	Allow disabled suites and pending specs

+ ORION-2133	Code tree editor will freeze when user delete all text in file and switch to code tree view


###  EventRecorder

+ ORION-2146  EventRecorder hangs when recording after bad step

+ ORION-1869	Incorrect locators for radio group causing multiple items error

+ ORION-2090	Error appears when user use InBrowser Event Recorder

+ ORION-2257	Interacting with modern grid menus throws errors in Event Recorder

+ ORION-2270	Event Recorder doesn't work properly with Ext.ux.form.ItemSelector

+ ORION-2297	Scroll on Combo is not playable

+ ORION-1481	Recording of slider change doesn't work

+ ORION-1751	Locator for colorpicker is not stable in inBrowser event recorder.

+ ORION-1893	Header checkbox click coordinates are miscalculated when recording

+ ORION-1964	Select day on calendar is not playable

+ ORION-1977	dblclick doesn't trigger grid cell editing

+ ORION-2068	Grid trigger is not recorded properly for IE and Edge

+ ORION-2305	Using In-Browser event recorder can cause Ajax requests in app to slow down or timeout

+ ORION-2320	Event Recorder not generating specific enough locator for Combobox's Boundlist on Ext JS 4.2.0 app

+ ORION-2323	Event Recorder and Inspect not always using custom locator builders for some components

+ ORION-2131	Event recorder does not handle some React elements

+ ORION-2321	Inspecting or recording CheckBoxField doesn't always create a specific enough locator


###  Inspect

+ ORION-2079	Determine UX for different inspector scenarios

+ ORION-2107	ReferenceError while using Inspector

+ ORION-2170	Inspect hierarchy tree steals focus

+ ORION-2172	Unavailable pageobject component shows error in tooltip and doesn't show component type

+ ORION-2173	inspector does not properly higlights components on IE11 and throws error

+ ORION-2176	Inspector doesn't work with  Microsoft webdriver on react app

+ ORION-2179	Inspector sometimes return Unavailable component

+ ORION-2232	Inspect has fatal error when transitioning from non-ext app to ext app

+ ORION-2268	Inspector does not load hierarchy until some component is inspected

+ ORION-2112	Error when clicking some elements for DomTree

+ ORION-2114	Error when refreshing DomTree hierarchy

+ ORION-2132	DOM inspector always return "Nothing matches or visible"

+ ORION-2150	DOM elements are highlighted on hierarchy tree only on non ExtJS pages/examples

+ ORION-2154	Bad wizard query throws error when no matches are found

+ ORION-2155	find() and batchQuery() do not account for widgets

+ ORION-2164	Inspect doesn't notice when browser being inspected is closed.

+ ORION-2178	Inspect returns bad xpath locators in some circumstances

+ ORION-2187	Fast clicking elements for Inspect causes freeze in Studio

+ ORION-2199	Improve Inspect performance with IE/WebDriver on Windows

+ ORION-1857	Inspector window size is too big on Mac

+ ORION-2160	Element.getClassMap() fails when the node is a non-HTML element

+ ORION-2194	Duplicated component is incorrectly verified

+ ORION-2212	Inspect PageObject items dirty, clicking "Insert API Code" button doesn't warn of changes.

+ ORION-2317	Inspect grid and Event Recorder combobox are rendering HTML tags within generated locators

+ ORION-1763	Error when Inspector is launched and cursor is not placed at "IT"

+ ORION-2032	Support ExtReact component casing in Strategy

+ ORION-2152	Inspector doesn't highlight elements on keyboard navigation in hierarchy tree

+ ORION-2158	Table, slider futures missing in Inspector future type

+ ORION-2159	Inspector wizard hierarchy view is not scrolled into selected component on some ReactApp

+ ORION-2174	Wrong pop up message is displayed




###  studio

+ ORION-2025	Errors appears when user clicks on Project list before its loaded

+ ORION-2073	Cannot open Sencha Studio

+ ORION-2113	Specs duplicated when switching between Code and Tree view

+ ORION-2282	Highlighting has disappeared on Scenario Results grid

+ ORION-223	  First run of app asks to update and reload

+ ORION-2156	xpath() incorrectly returns an array of elements when ST.options.failOnMultipleMatches is disabled

+ ORION-2244	Scrolling in test results during test execution causes errors

+ ORION-520	  Image miniature is not visible due to unnecesarily long message element

+ ORION-558	  socket hang up at createHangUpError when running test on remote browsers

+ ORION-1667	Error in unit test is not propagate up in studio when run only unit test

+ ORION-2239	Links to docs and forum on start page do not direct to external links

+ ORION-2262	Test detail isn't removed when "Clear" button is clicked

+ ORION-2265	Settings window stays opened when workspace is closed

+ ORION-2311	Studio not defaulting to source code view when Developer role selected

+ ORION-286	  Should prevent generating apps/workspace/themes when no cmd is detected on first start

+ ORION-336	  Records in Archive Results browser are duplicated after closing and reopening root folder

+ ORION-1908	Upgrade Studio to use Ext JS 6.5

+ ORION-2205	Upgrade Studio to use Ext JS 6.5.1

+ ORION-2240	Runner test results header height is too small

+ ORION-2241	Project tree should be wider by default

+ ORION-2242	"Continue" button on role selection screen is not visible on default ST window size 

+ ORION-2245	Prevent project tree toolbar from being hidden

+ ORION-2261	Not actual colors of lost connection messagebox

+ ORION-96	  Orion has 2 shortcuts for Close window

+ ORION-2264	Jira integration settings section is stretched

+ ORION-2267	Text on Welcome tour is not properly visible


###  Test Runner

+ ORION-1260	Bad global variable fail after test is executed.

+ ORION-1999	Disable code coverage button for ExtReact applications

+ ORION-287	  CLI needs to accept a farm name to resolve ambiguous pool names

+ ORION-519	  Cli (stc) doesn't show exact version info

+ ORION-903	  URL must have / at the end of the string

+ ORION-2231	Correct the usage of "timer-worker.js"


###  CmdIntegration

+ ORION-489	  Missing framework in workspace navigation tree when generating app in frameworkless workspace

+ ORION-982	  Unable to build touch app.

+ ORION-2098	Development Build process is not generating proper files

+ ORION-504	  ST wants start app watch although app watch is running

+ ORION-2253	App watch task doesn't stop after closing of workspace

+ ORION-2185	Special Development Build process is not generating proper files in .sencha/temp/<appname> with ExtJS 6.2.1 and Cmd 6.2.2


###  Jasmine

+ ORION-960  Custom matchers pass message is not accepted


###  sencha test command (STC)

+ ORION-2022  STC creates duplicate Jira tickets when multiple browsers are used in a pool

+ ORION-2027  STC includes information about unused -W parameter

+ ORION-1577	STC does not scaffold Embedded Farm

+ ORION-2067	Include scenario name as top-level suite in TeamCity reports


###  Misc

+ ORION-2064	Cannot open Sandbox folder from git as workspace

+ ORION-2138	Selenium server does not start

+ ORION-2012	Cannot access local archive server results without internet connection

+ ORION-299	  Can access scenario without URL when tab is pinned

+ ORION-2034	Support ExtReact apps in Studio

+ ORION-2045	Create icon for ExtReact apps in project tree

+ ORION-2051	Upgrade to latest version of webdriverio

+ ORION-2142	Keep scenario form open when save occurs because of application blur

+ ORION-2151	Disable app watch for ext-react apps in project settings

+ ORION-1014	Enable Sencha Cmd or Sencha Test CLI to create ".sencha/temp/app_name" files

+ ORION-2285	Google Chrome 62 and 63 compatibility issues

+ ORION-2286	Inspector not working with Chrome 62 and 63

+ ORION-2306	Using XPath element locator in 2.2.0 throws an error

+ ORION-2080	Improve prioritization of locators to always return a unique locator

+ ORION-2302	 Browser needs to close after the event recorder is finished with

+ ORION-208	  Settings of browsers pool is not saved if you want to save the setting in workspace folder

+ ORION-255	  Unable to create/open workspace using Cmd 5.x

+ ORION-333	  Proxy server is not shown in Tasks tab after clearing results

+ ORION-1603	Support require() within WebDriver-based scenario tests

+ ORION-2089  Allow extra arguments to be passed to execute()
