# Lab 3: Finding Component Locators

**Total Time: 10 minutes**

In order to generate locators for Ext JS Components, you either need to have
access to the original source code that the developer worked on, to see
which properties and values have been set on components, or you need to use 
a tool that inspects elements as the app runs in the web browser, and shows you 
different locators that can be used.

The Inspect tool within Sencha Test Studio enables you to inspect elements 
within a running web application, and helps produce element or component locators.

## Component Locator extension for Google Chrome

1. Download the [Sencha Component Locator extension](https://chrome.google.com/webstore/detail/sencha-component-locator/facapfmceabacjkjhjfjoaimoopiakdl) 
  for Google Chrome.

  ![Sencha Component Locator in the Chrome Store](../images/labs/SenchaComponentLocator.png)

1. Load the Asset Register app in the browser, login, and wait for the Dashboard
  to display.

1. Bring up Chrome's Developer Tools in Inspect mode:
    - Mac: `Cmd` + `Shift` + `C`
    - Windows: `Ctrl` + `Shift` + `C`

  ![Chrome's Developer Tools](../images/labs/SenchaComponentLocator-DevTools.png)

1. Switch to the `Elements` tab within the Developer Tools.

1. Inspect the Logout button, by hovering over it which should highlight it, then 
  click. In the `Elements` tab, to the right you should see a `Sencha Component Locator`
  tab. Select this tab. It will show a variety of different locators that could be used, 
  in order of preference.
  
  ![Inspecting with Sencha Component Locator](../images/labs/SenchaComponentLocator-Inspect.png)
  
  For the Logout button, it's showing us the following 6 options as a locator:
  
    main button[reference=logout]
    
    main button[iconCls=x-fa fa-sign-out]
    
    button[iconCls=x-fa fa-sign-out]

    button[reference=logout]
    
    main button
    
    button
    
  It's always best to choose a locator that narrows down the component search
  as much as possible. That's why the first two choices in the list above
  are the best options, because they have a parent component type (`main`), 
  followed by the `xtype` of the component we're referencing (`button`),
  where either the `reference` or `iconCls` matches the string defined.
  
1. Try this out on some other components in the application, such as form fields, 
  buttons, message boxes and the dashboard panels, to get familiar with the different
  locator choices.