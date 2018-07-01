# Sencha Test CLI (STC)

In order to provide integration with continuous integration (CI) servers like Jenkins and Teamcity, Sencha Test allows 
you to execute tests for an existing scenario from the command-line.  The command-line tool doesn't support launching of 
local browsers, which means a browser farm and browser pool must be configured for the target scenario.

Let's walk through executing a test via CLI.

## Command Line Syntax

The basic command-line syntax for executing a test from the command line is as follows:

    stc run -o output -p pool -s scenario

### Required Flags

Here are the optional flags that may be passed along via your command line execution:

`-o <output>` - Output format. Supported values are `text`, `teamcity` and `junit`

`-p <pool>` - Name of the pool from whence tests will be executed. This must be a pool associated with a browser farm

`-s <scenario>` - Path to the scenario to be executed. If unspecified, defaults to the current directory.

In the following example to be run from a Windows command line, we are executing tests for: 

* The scenario located at `tests\unit_tests` 
* In the browser pool called `My WebDriver Pool` 
* Providing output in `TeamCity` format

        stc run -o teamcity -p "My WebDriver Pool" -s tests\unit_tests

### Optional Flags

Here are some optional flags that can be used:

`--debug` - Sets log level to a higher verbosity

## Code Coverage

Code coverage can be enabled for In-Browser Scenarios as follows:

`-C` - Enables code coverage for this session

To exclude files/folders from the scope of the code coverage report, use the Project Settings screen in Sencha Studio. For example, the Ext JS SDK directory should be excluded, as you would want to focus the code coverage analysis on just your own application code. To exclude all code files within the `ext` directory, use this code coverage filter:

    ^/ext/.*?$

To access the Code Coverage reports, use Sencha Studio to view test results that have been saved in an Archive Server.

## Screenshot Comparison

To perform image comparisons from screenshots, Sencha Test will use an existing run as the reference (baseline) against 
which each image will be compared. If a baseline for comparison is not present, all comparisons will pass, and the 
resulting archive directory can then be specified as the baseline for future comparisons.

To use a specific result archive as baseline, it has to be copied or renamed to `${workspace.dir}/reports/baseline`. Alternatively, 
the `-b` switch can be used to specify any arbitrary result archive directory.

`-b <baseline>` - Path to the result archive directory to be used as baseline for image comparisons

By default, Sencha Studio will assign a dynamically generated build number to each test execution. To specify the build 
number for a given test run, the `-n` switch can be used.

`-n <build_number>` - Build number for the test execution

By specifying the baseline directory and the build number, it's possible to control all the directory and file names 
associated with the test execution. This way, one can easily archive test results and fetch arbitrary baselines in a 
CI system.

## Cloud-based Browser Farm Options

In order to execute tests in a cloud-based browser farm such as SauceLabs or BrowserStack, you can specify credentials and callback address.  Here are the options that may 
be applied:

`-u <username>` - Username for the browser farm

`-k <key>` - Access key for the browser farm

`--notunnel` - If specified, disables the automatic launch and teardown of the tunnel to the specified cloud provider. When 
this switch is used, a tunnel for the specified username must be already running, either in the local machine or in a 
dedicated host in the same network.

**Note:** The auto-connecting tunnel feature is not currently available in the product.  All tunnels will need
to be manually created until auto-tunnel creation is built-in.

`-c <callback_address>` - Callback address - host or IP by which the farm browsers can dial back to Sencha Test's proxy. 
If unspecified, defaults to localhost. This switch is particularly useful when a dedicated tunnel is being used. In such 
case, it's likely to be the local machine's LAN IP address.

In the following example to be run from a Linux command line, we are executing tests for: 

* Tests found within `tests\unit-tests`

* In the pool named `SauceLabs pool`

* Providing output in Jenkins format

* Using the credentials `username:xxxxx-xxxx-xxxx-xxxx-xxxxx` will be used

* A SauceConnect tunnel will not be launched automatically.  This means the user is responsible for starting one manually.

* All browsers will attempt to connect to **http://192.168.1.42**

Example:    

    stc run -o junit -p "SauceLabs pool" -s tests\unit_tests -u user -k *x-x-x-x-x* --notunnel -c *192.168.1.42*
