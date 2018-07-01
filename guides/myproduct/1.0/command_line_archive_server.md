# CLI and the Archive Server

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

## Image Comparison

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

In order to execute tests in a cloud-based browser farm such as SauceLabs or BrowserStack, you can specify credentials, 
callback addresses while controlling the automatic launch of the provider's tunnel.  Here are the options that may 
be applied:

`-u <username>` - Username for the browser farm

`-k <key>` - Access key for the browser farm

`--notunnel` - If specified, disables the automatic launch and teardown of the tunnel to the specified cloud provider. When 
this switch is used, a tunnel for the specified username must be already running, either in the local machine or in a 
dedicated host in the same network.

**Note:** The auto-connecting tunnel feature will not be available in the early access or beta releases.  All tunnels will need 
to be manually created until auto-connection is available.

`-c <callback_address>` - Callback address - host or IP by which the farm browsers can dial back to Sencha Test's proxy. 
If unspecified, defaults to localhost. This switch is particularly useful when a dedicated tunnel is being used. In such 
case, it's likely to be the local machine's LAN ip address.

In the following example to be run from a Linux command line, we are executing tests for: 

* Tests found within `tests\unit-tests`

* In the pool named `SauceLabs pool`

* Providing output in Jenkins format

* Using the credentials `username:xxxxx-xxxx-xxxx-xxxx-xxxxx` will be used

* A SauceConnect tunnel will not be launched automatically.  This means the user is responsible for starting one manually.

* All browsers will attempt to connect to **http://192.168.1.42**

Example:    

    stc run -o junit -p "SauceLabs pool" -s tests\unit_tests -u user -k *x-x-x-x-x* --notunnel -c *192.168.1.42*

## Setting up a Result Archive Server

Sencha Test provides a component called "result archive server".  This is the area in which test results can be stored 
for later review via the Sencha Test Studio GUI.

To set up an archive server, a configuration file called `storage.json` has to be created.  This file must contain one 
or more storage area definitions. 

A storage area is defined as a property whose name is the key that users need to know in order to store results.  The 
value is an object containing the physical path where its archives will be stored relative to the server root directory.

Here is a sample storage area.  

    {
    	"my_storage_key": {
    	    "path": "/mystoragearea"
    	}
    }

**Note**: Users must know the key `my_storage_key` in order to store test results in your archives under `/mystoragearea` 
on the designated server.  The key itself can be any value. 

These paths may contain multiple directory levels. These paths don't hold any special meaning. They can be reviewed 
by the server administrator in order to organize the test results archives and/or provide isolation across teams and 
projects. The keys are free-format strings.

In the following example, storage areas are separated by team. Each team, developers and qa in this case, need to know 
their key in order to store results in their respective storage areas.

    {
        "889jwx093jr8wuwer": {
            "path": "/developers"
        },
    
        "sccmnn840394843": {
            "path": "/qa"
        }
    }

In the next example, teams have isolated storage areas for each of their projects.

    {
        "879fnas9d8jf70sd": {
            "path": "/TeamA/project1"
        },
    
        "mx348r343mr34cj": {
            "path": "/TeamA/project2"
        },
    
        "sdnaaa090ilss": {
            "path": "/TeamB/project1"
        }
    }

### Starting the Archive Server

To start the result archive server, create a `storage.json` file in a dedicated directory and from there, run the 
following from your CLI:

    stc server

You should then see a success message:

    Archive server listening on port 1903

Here's an example of how you'd set up your Archive Server on a machine:

    mkdir archiveserver
    cd archiveserver
    vim storage.json #configure storage areas - see examples above
    stc server

### Archive Server Connection Options

In order to send the result archive to a configured archive result server, you may use the following switches with 
`stc run`.

`-S <server_address>` - Archive server address. If the archive result server host machine IP address is `192.168.1.42`, for 
instance, the value will be [http://192.168.1.42:1903](http://192.168.1.133:1903) (including the port number).

`-K <key>` - Key to the storage area. To store results in `/TeamA/project2` (example above), the value will 
be `mx348r343mr34cj`.

In the following example, we are:

* Storing results of `tests\unit_tests`
* With an output type of `teamcity`
* In the pool named `My WebDriver Pool`
* On a server hosted on `192.168.1.42:1903` with port `1903`
* Using the key of `mx348r343mr34cj`

Example:  

    stc run -o teamcity -p "My WebDriver Pool" -s tests\unit_tests -S http://192.168.1.42:1903 -K mx348r343mr34cj

### Expected Output

Outputs similar to the ones below are expected after a successful result storage on the server:

___
    Uploading archive to http://localhost:1903
    Server response: 200 - Archive received
    user:~$
    Client: successfully uploaded test result archive
___
    Receiving archive 28ea1080-a2a5-11e5-ac7d-51ab7d509196.zip
    Archive 28ea1080-a2a5-11e5-ac7d-51ab7d509196.zip extracted to /home/user/archiveserver/TeamA/project2/foo/orion/28ea1080-a2a5-11e5-ac7d-51ab7d509196
    Server: successfully received test result archive

### Running Multiple Scenarios as a Single Build

A single test project will often have multiple scenarios. In these cases, you may 
want to run multiple scenarios as part of a single "build" in your CI system. This
allows you to see all of the Scenario results as a single results set in Sencha Studio.

As an example, you may have Scenario A and Scenario B and you want to run both of
these whenever code is merged.

Once all of your Scenarios are complete, the Archive Server will merge the results
from Scenario A and B and Sencha Studio can then display the aggregated results as
one logical build or test run number.

## Result Merging

Sencha Test gives you the ability to merge the results of your tests in two different ways.

### Archive Server Configuration

In this method, you would need to include an allowOverwrite key to your configuration.  For example:

    {
        "multiscenario": {
            "path": "/multiscenario",
            "allowOverwrite": true
        }
    }
    
### STC Command

You can also add an overwrite flag to your STC command.  For example:

    stc run -s Dashboard -p embedded -S http://localhost:1903 -K multiscenario -n 6 --overwrite

