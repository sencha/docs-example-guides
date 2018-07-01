# Sencha Test Archive Server

Sencha Test provides a component called "result archive server".  This is the area in which test results can be 
stored for later review via the Sencha Test Studio GUI.

## Setting up a Result Archive Server

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

In the following example, storage areas are separated by team. Each team, Developers and QA in this case, need to know 
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

## Starting the Archive Server

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

## Archive Server Connection Options

In order to send the result archive to a configured archive result server, you may use the following switches with 
`stc run`.

`-S <server_address>` - Archive server address. If the archive server host IP address is `192.168.1.42`, for 
instance, the value will be [http://192.168.1.42:1903](http://192.168.1.133:1903) (including the port number).

`-K <key>` - Key to the storage area. To store results in `/TeamA/project2` (example above), the value will 
be `mx348r343mr34cj`.

In the following example, we are:

* Storing results of `tests\unit_tests`
* With an output type of `teamcity`
* In the pool named `My WebDriver Pool`
* On an archive server hosted on `192.168.1.42:1903` with port `1903`
* Using the key of `mx348r343mr34cj`

Example:  

    stc run -o teamcity -p "My WebDriver Pool" -s tests\unit_tests -S http://192.168.1.42:1903 -K mx348r343mr34cj

## Expected Output

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

## Running Multiple Scenarios as a Single Build

A single test project will often have multiple scenarios. In these cases, you may 
want to run multiple scenarios as part of a single "build" in your CI system. This
allows you to see all of the Scenario results as a single results set in Sencha Studio.

As an example, you may have Scenario A and Scenario B and you want to run both of
these whenever code is merged.

Once all of your Scenarios are complete, the Archive Server will merge the results
from Scenario A and B and Sencha Studio can then display the aggregated results as
one logical build or test run number.

### Result Merging

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