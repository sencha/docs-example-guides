# Installation and Setup

Sencha Test contains two applications: Sencha Studio (a GUI application) and stc (a command-line tool). This guide
will walk through the installation process and get you ready to start testing! You can also check out the
[Sencha Test Overview](product_overview.html) for general product information.

Before getting started, let's review the supported browsers, platforms, and Sencha frameworks. We will then walk
through the installation steps.

## Supported Platforms

### Operating Systems
+ Windows (Win 7+)
+ Mac OS X
+ Linux 32-bit / 64-bit

### Browsers
* **Desktop:** Internet Explorer 8-11, Edge, Chrome, Firefox, Safari, Opera
* **Mobile (Tablet and Phone):** Chrome, Safari, Internet Explorer, Firefox

### Sencha Frameworks
+ Ext JS 4.2+
+ Sencha Touch 2.1+

### Sencha Tools
Though optional, Sencha Test can interoperate with Sencha Cmd 6.0.2 or higher (6.1.0 is recommended).
Sencha Cmd integration can be disabled even if you are using Sencha Cmd.

### Other JavaScript Libraries and Frameworks
You may use Sencha Test with any JavaScript-based application or web page, however, Sencha Test
includes its own version of Jasmine and Istanbul which may conflict with other versions of these
libraries included by the page. In addition, Sencha Test uses the "ST" global object as its
namespace.

## Installation
You will need to download the zip archive fom [the web site](https://www.sencha.com/products/test/).

### Installing Sencha Studio and STC
1. Launch the newly downloaded installer.
1. Click "Next" to begin the installation.
1. Accept the license agreement to proceed (select “I accept the agreement” and click "Next").
1. Choose your install path (if different from the default install path) and click "Next".
1. **(Windows)** Check the checkboxes for “Create a Start Menu folder” and “Create shortcuts for all users” (optional) and click "Next".
1. The installation is now complete.  Click "Finish" to close the installer.
1. Launch Sencha Studio from the install path, desktop icon, or (Windows) Start Menu icon or
  (Mac) Launchpad.

### Dependencies
#### Embedded Selenium Server
Sencha Test Studio (version 2.0 and above) comes with an embedded Selenium Server instance that can be leveraged to run WebDriver-based scenarios. In order to utilize this functionality, **Java 8** (or above) must be installed.

#### STC and Node.js
To run STC, **Node.js** must be installed (version 6 or 7) and should be on the system PATH.

## License Activation Workflows

### Trial License (free for 30 days)

If you are evaluating the product for the first time, follow these steps to download a trial license:

1. On the initial screen, click Get Started.

1. Enter the email address used to download the Sencha Test trial.

1. Click Start Trial.

1. Wait for the "Activating License" dialog to complete.

1. You can start using Sencha Test once your activation is successful.

### Purchased License (No Trial)

If you have purchased a Sencha Test License and don’t have a trial license:

1. Click Get Started on the initial screen.

1. Enter a valid email address and your activation code.

1. Click Activate.

1. Wait for the "Activating License" dialog to complete.

1. You can start using Sencha Test once your activation is successful.

### Purchased License (Activation After Trial)

If you have purchased a Sencha Test License and have a working\expired trial license:

1. Navigate to the License tab on the settings screen. Information about trial license is available on this screen.

1. Click Activate.

1. Enter the activation code obtained in the email. Check with the person who purchased the product for your company if 
you did not receive an email.

1. Click Activate

1. Wait for the "Activating License" dialog to complete.

1. The license is now "Purchase".

### Successful Trial (Offline)

If you are evaluating the product for the first time and are unable to download a trial license then follow these steps 
to get an offline license:

1. Click Get Started on the initial screen.

1. Click Offline License.

1. Enter the email that was used to download Sencha Test.

1. Click Request Trial

1. Offline license information is copied to the clipboard. 

1. Paste the information into an email, verify, and send it to activations@sencha.com

1. A license file will be emailed back to you once Sencha receives the information needed.

1. Click on Open License File and select the offline license file from Sencha.

1. Click Open.

1. The License is validated and you should see the Trial Activation successful screen. Continue on to use Sencha Test.

### Purchased License (Activation After Trial Offline) 

If you have purchased a Sencha Test License and have a working\expired trial license:

1. Navigate to the License tab on the settings screen. Information about the trial license should be available on this screen

1. Click Activate

1. Enter the activation code obtained in the email. Check with the person who purchased the product for your company if 
you did not receive an email.

1. Press Request Activation

1. Offline license information is copied to the clipboard. 

1. Paste the information into an email, verify, and send it to activations@sencha.com

1. A license file will be emailed back to you once Sencha receives the information needed.

1. Click on Open License File and select the offline license file from Sencha.

1. Click Open.

1. The License is validated and you should see Trial Activation successful screen. Continue on to use Sencha Test.

## Upgrading to Sencha Test 2.x

If you're currently using Sencha Test 1.x and you are upgrading to Sencha Test 2.x, 
follow these steps:

1. Download and unzip the Sencha Test 2.x.
1. Run the installer and select the recommended options
1. Make sure that your new STC install is added to your PATH variable and takes precedence over the older version

Sencha Test 2 should now be installed on your system.  Workspaces created in Sencha Test 1.x can be opened in Sencha
Test 2.x.

## Uninstalling Sencha Test

1. Open the "Sencha Test" application folder (e.g., in "C:\Program Files" on Windows, or in
  "Applications" on Mac).
1. Double-click the “uninstall” icon.
1. **(Windows)** Click "Yes" on the "User Account Control" dialog if applicable.
1. Click "Next".
1. Sencha Studio has been uninstalled.
1. Click "Finish" to close the uninstaller.

## Next Steps

Now that Sencha Studio and stc are installed, you can [get started](getting_started.html)
writing some tests! If you have  further questions, concerns, or bug reports, please visit the 
[Sencha Test forums](https://www.sencha.com/forum/forumdisplay.php?144-Sencha-Test).
