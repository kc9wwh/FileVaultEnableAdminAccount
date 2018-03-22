# FileVault Enable your OrgAdmin Account
###### FileVault enable your organizational admin account...even on macOS 10.13!

___
This script was designed to be part of a policy within Jamf Pro to FileVault enable your local admin account on your macOS devices. This script is compatible with SecureToken on macOS 10.13 as well. If the script runs and doesn't find the admin account, it will create it and then FileVault enable it.

Requirements:
* Jamf Pro
* macOS Clients on 10.9 or later
* LOGO File present on macOS device.
* Look over the VARIABLES and configure.

___

**Why is this needed?**

Starting with macOS High Sierra, Apple has introduced SecureToken along with the APFS filesystem. Currently when accounts (including the management account) are created with Jamf Pro via a Policy, QuickAdd or DEP (Management Account) these accounts do NOT get a SecureToken. This script will prompt the currently logged in user if they are FileVault Enabled for their macOS password, which is used to FileVault enable the orgAdmin account.

*This script has been tested on OS X 10.11.6, 10.12.6 and macOS 10.13.3*


**Configuring the Script**

When you open the script you will find a variables section that will need to be configured. Here you can specify the message that is displayed to the end user while the script is running, your custom logo file, and the orgAdmin credentials (using Encrypted Strings) that you want to FileVault Enable.

For setting up Encrypted Strings, please ensure the USER and PASS both use the same SALT and PASSPHRASE.

https://github.com/brysontyrrell/EncryptedStrings.

These variable should also be using Jamf Pro Parameters and the labels should be specified after upload to Jamf Pro under Settings > Computer Management > Script > {thisScript} > Options
* PARAMETER 4: ADMIN_USER_ENCRYPTED
* PARAMETER 5: ADMIN_PASS_ENCRYPTED
* PARAMETER 6: SALT
* PARAMETER 7: PASSPHRASE

https://www.jamf.com/jamf-nation/articles/146


**Example of Script Parameter Labels**

![Example of Script Parameter Labels](/assets/scriptParameterLabels.png)


**Example of Script Parameter in Policy**

![Example of Script Parameter in Policy](/assets/policyScriptParameters.png)


**Video Guide to Setting up Encrypted Strings**

[![Click to watch on YouTube](http://img.youtube.com/vi/JvulskR2IWE/0.jpg)](http://www.youtube.com/watch?v=JvulskR2IWE)

*Click the video to start playing on YouTube*
