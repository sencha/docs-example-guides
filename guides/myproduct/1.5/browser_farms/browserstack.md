# BrowserStack

[BrowserStack](https://www.browserstack.com) is a cloud based platform for automated 
testing of web applications. 

Rather than spending time and effort manually configuring and maintaining an internal 
browser farm, hosted browser farms such as BrowserStack already have the 
infrastructure configured on their end, and you are able to quickly and easily leverage 
their various browser instances to test your web applications.

## Using BrowserStack with Sencha Test

1. Navigate to the [BrowserStack website](https://www.browserstack.com), and register for a 
 trial if you don't already have an account.
 
1. After logging in to your BrowserStack account, navigate to the **Account** screen, 
 select the Settings tab, and scroll down to view your **Access Key**. Copy this key to the clipboard. You will
 need to use this key within Sencha Studio.

    **Note:** If you don't populate the Access Key within Sencha Studio, you will be required
    to define the key when using Sencha Test CLI (stc).
 
    ![BrowserStack Access Key](../images/browserstack-access-key.png)

1. In Sencha Studio, select the **Browsers** tab, and **Add** a configuration for 
 **BrowserStack**:
 
    ![New BrowserStack configuration](../images/browserstack-new-farm.png)

1. After adding the new Browser Farm, change the settings by specifying your BrowserStack
 **Username**, **Access Key**, setting **Concurrency** to a desired number (e.g. **3**) and clicking **Save**.

    **Note:** By setting **Concurrency** on the farm to **3**, this tells Sencha Test
    that 3 different browsers can be used simultaneously. If this was left at 1, only a single browser
    would be tested, and when that finishes only then would the next browser be started.

    ![BrowserStack settings](../images/browserstack-added-farm.png)

1. Once the settings have been populated, you can start to specify which browsers you 
 want to use. This is done by creating a Browser Pool. **Right-click** on the 
 **BrowserStack** node in the tree and select the option to **Add pool**. Enter a meaningful name, such as
 `BrowserStack Modern Browsers`.
 
    ![New Browser Pool](../images/browserstack-add-pool.png)
 
1. You will then be prompted to choose a location to save the configuration file
 for this Browser Pool. We recommend saving this in the Sencha Test workspace folder.
 
1. Select the newly added Browser Pool, and using the drop-down list at the bottom of the 
 screen, select the browsers you want to add, e.g. **Chrome**. The Version drop-down list will default to 
 select the latest version. Click the **Add** button to add this browser and version combination to the list.
 You can then optionally select which Platform you want this browser to run on, along with
 a desired screen resolution.

    **Note:** If your app is hosted on a publicly facing network, like the Internet, the "Local" option should
    be left unchecked on each of the added browsers.

    ![Adding a new browser to the Browser Pool](../images/browserstack-added-browsers.png)

1. After making your changes, click the Save button.

1. Return to the Project tab, and select one of your Scenarios. The newly added list of BrowserStack browsers 
will be displayed. Select the entire pool, or one or more browsers, to run your tests.

    ![Test runner screen with BrowserStack browsers](../images/browserstack-using-browsers.png)
