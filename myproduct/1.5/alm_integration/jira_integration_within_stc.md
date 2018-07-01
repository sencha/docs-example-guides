# Jira Integration within Sencha Test Command-line (STC)

New test failures can be pushed to Jira from STC. Configuration is done via the STC `alm.json` file. 
Issues from test runs are created in the specified Jira instance at the end of a test run, if enabled.

## STC Configuration

### alm.json

To provide credentials for connecting to Jira via STC, you will need to create a file 
named `alm.json` in the root of your archive server. This file should reside at the 
same level as the `storage.json` file that was used to initialize the archive server. 

This file should contain a simple object that defines, at a minimum, the following fields:

* **protocol**: The protocol for connecting to your Jira instance

* **host**: The host name for connecting to your Jira instance

* **username**: The username of the Jira user that will be used to create issues

* **type**: This should be **jira**

Optionally, you can also provide the following configurations:

* **port**: The port used to connect to the Jira instance. This should only be specified if needed

* **project**: The default project to use for creating issues. The project must be provided when executing the test run if not specified in the `alm.json` config

An example of the `alm.json` file is as follows:

    {
        "protocol": "https",
        "host": "mycompany.jira.com",
        "port": "8080",
        "username": "test.user@mycompany.com",
        "project": "MYPROJECT",
        "type": "jira"
    }

## Running Tests and Creating Issues with STC

To create issues in Jira using STC, there are three new command line arguments:

* `integrationPush`: Specifies any spec failures will be entered into Jira if there is 
not already an issue associated with the test spec

* `integrationProject`: Specifies the project key in Jira that will receive the issues

* `integrationPassword`: specifies the password for the user stored in the `alm.json` file 
on the destination archive server

Creating issues in Jira requires a test suite to be run with the results stored in an 
archive server. To create issues in Jira with STC, run STC similar to the following:

    stc run -p "Embedded" \
        -s /projects/admin-dashboard/test/dashboard \
        -S http://127.0.0.1:1903 \
        -K st_archive \
        --integrationPush \
        --integrationProject MYPROJECT \
        --integrationPassword SupErSEcrEtPW

Where: 

* `-p` is the browser pool that will execute the test scenario,

* `-s` is the test scenario to execute,

* `-S` is the archive server to receive the test results

* `-K` is the storage key for authenticating with the archive server

When the integration options are specified, the archive server will attempt to 
create new failures in Jira in the specified project. If a test spec has already been 
logged, a new one will not be created. 

