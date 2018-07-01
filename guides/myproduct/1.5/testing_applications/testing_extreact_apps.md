# Testing ExtReact Applications

Sencha Test is able to help you write and execute end-to-end tests against ExtReact applications
using WebDriver scenarios.

By using capabilities like the Event Recorder and Inspect tool, you are able to quickly generate unique
and stable locators for components in the page.

This guide walks you through the typical process of using Sencha Test and configuring it to run tests 
against a ExtReact application.

You have two choices when deciding where to create your test project:

- Creating a new Project in Sencha Studio and adding test suites in a standalone project
- Opening the ExtReact app in Sencha Studio and adding your tests in the ExtReact app folder structure

## Creating a new Project

1. Open Sencha Studio, and create a new Project. Define the URL where you have your ExtReact app running, for 
example, `http://examples.sencha.com/ExtReact/6.5.3/conference-app/`.

    * **Name:** Name of the project, for example `ConferenceApp`
    * **Path:** Where the project will be created. Scenarios and test suite files will be added in this location.
    * **URL:** Web address for the running web app, for example `http://examples.sencha.com/ExtReact/6.5.3/conference-app/`.

1. Once the project has been created, you will be able to click on the "New Scenario" button to create
a scenario that will hold your test suite files.

    * **Name:** A name for the scenario, for example if you are creating end-to-end tests, you could call
    the scenario `EndToEnd`
    * **Test type:** Selecting WebDriver will run your tests separately from the browser. This is suitable for
    end-to-end testing. If you have the Test Engineer persona selected in Sencha Studio, this option will be 
    hidden, and new scenarios will default to WebDriver type.
    
1. After the scenario has been created, select the scenario in the tree, then click the "New Test Suite" button >> select 
"Jasmine Test Suite" from the menu. Enter a name for the test suite, for example `ConferenceApp`. This creates a new 
Jasmine test suite file. The `.js` file extension gets added automatically.

1. With the new test suite loaded in the editor, you can now begin writing your tests. You can leverage the 
[Event Recorder](../event_recorder/introduction_to_event_recorder.html) to capture a set of actions for insertion
in to your test suite, or write code using the 
[Futures APIs](../futures_apis/introduction_to_futures_apis.html). You can also leverage the 
[Inspect tool](../inspect_tool/introduction_to_inspect_tool.html) to help you create locators for elements.

## Opening ExtReact apps in Sencha Studio

In order to open your ExtReact app in Sencha Studio and add your tests to the app's folder, the ExtReact app needs 
to reside within a Sencha workspace, so that it can be opened in Sencha Studio. This can either be a blank 
workspace just for the ExtReact app, or one with other Ext JS apps/packages. 

1. If you don't already have a workspace for your ExtReact app, create a new Project in Sencha Studio. This 
creates a folder with a `workspace.json` config file.

1. Copy or move your ExtReact app folder in to the root of the workspace folder.

1. Modify the `workspace.json` file to define the presence of any ExtReact apps, by adding a new `extreact` 
config, and defining the folder names of the ExtReact applications that reside within the workspace folder:

        {
            /**
            * Array of Ext JS apps
            */
            "apps": [
                "Dashboard"
            ],

            /**
            * Array of ExtReact apps
            */
            "extreact": {
                "apps": [
                    "my-react-app"
                ]
            }

            ...

1. When you open the workspace in Sencha Studio, you will see your ExtReact apps show up in the project structure 
under the "ExtReact Applications" node, and you will be able to add your scenarios and tests. These will be 
created within a `test` folder inside of the ExtReact app folder.

    ![ExtReact app support in Sencha Studio](../images/extreact-app-support.png)

## Further Information

For more information on scenarios and test suites, see the 
[Projects, Scenarios and Suites guide](./test_projects_scenarios_suites.html#testing_applications-_-test_projects_scenarios_suites_-_test_projects_and_scenarios).