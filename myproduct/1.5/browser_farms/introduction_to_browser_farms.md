# Introduction to Browser Farms

Sencha Test comes with the ability to run tests on locally installed
browsers (for In-Browser tests), and an embedded Selenium Server with ChromeDriver (for 
WebDriver tests).

In a real-world environment, you will likely want to commence a test run 
from a centralized server on a wide range of different browsers, across a 
variety of different browser versions.

This is where browser farms come in to the picture. A browser farm is typically made up 
of a collection of virtual machines, each with 
a particular version of a browser installed. When you link these together, 
you have a browser farm, and can easily fire up an instance of a particular 
operating system and browser in order to run some tests.

There are two different routes you can go with deciding on a browser farm solution:

1. Building and configuring your own browser farm
1. Using a cloud-based browser farm provider

## Building and Configuring Your Own Browser Farm

One option is to build your own infrastructure of multiple operating systems,
with different browsers installed on to each, and configuring them in a WebDriver farm.

It can take a lot of time, effort and system resources to build and maintain this type
of infrastructure, which is why many companies choose to use a cloud-based
service.

If you want to create your own browser farm, or leverage a standalone Selenium Server instance,
see the [Standalone Selenium Servers guide](./standalone_selenium_servers.html).

## Cloud Based Browser Farms

A cloud based browser farm is where you make use of a third party's 
existing virtual machine and browser infrastructure when executing tests.

Sencha Test supports two popular cloud-based browser farms:

1. [Sauce Labs](https://www.saucelabs.com)
1. [BrowserStack](https://www.browserstack.com)

Using a cloud-based service can offer quick ramp-up times, and lower long-term 
overheads compared to building and maintaining your own browser farm.

For more information on the browser farms supported by Sencha Test, see the separate guides 
on [Sauce Labs](./sauce_labs.html) and [BrowserStack](./browserstack.html).