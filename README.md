# Umbrella Add-on for Splunk Enterprise
## Table of Contents

### OVERVIEW

- About the Umbrella Add-on for Splunk Enterprise
- Release notes
- Support and resources

### INSTALLATION AND CONFIGURATION

- Hardware and software requirements
- Installation steps
- Deploy to single server instance
- Deploy to distributed deployment
- Deploy to distributed deployment with Search Head Pooling
- Deploy to distributed deployment with Search Head Clustering
- Deploy to Splunk Cloud 
- Configure Umbrella Add-on for Splunk Enterprise

### USER GUIDE

- Data types
- Lookups

### OVERVIEW

#### About the Umbrella Add-on for Splunk Enterprise

| Author | Mikael Bjerkeland |
| --- | --- |
| App Version | 1.0 |
| Vendor Products | Cisco Umbrella/OpenDNS |
| Has index-time operations | True |
| Create an index | False |
| Implements summarization | False |

The Umbrella Add-on for Splunk Enterprise allows a Splunk® Enterprise administrator to index, extract and filter event information from the Cisco Umbrella/OpenDNS service using AWS S3 bucket data.
The app is CIM compliant.

##### Scripts and binaries

No scripts or binaries are included.

#### Release notes

##### About this release

Version 1.0 of the Umbrella Add-on for Splunk Enterprise is compatible with:

| Splunk Enterprise versions | 6.x |
| --- | --- |
| CIM | 4.8, 4.7 |
| Platforms | Platform independent |
| Vendor Products | Cisco Umbrella/OpenDNS |
| Lookup file changes | |

##### New features

Umbrella Add-on for Splunk Enterprise includes the following new features:

- Initial release

##### Fixed issues

Version 1.0 of the Umbrella Add-on for Splunk Enterprise fixes the following issues:

- Initial release

##### Known issues

Version 1.0 of the Umbrella Add-on for Splunk Enterprise has the following known issues:

- None known

##### Third-party software attributions

Version 1.0 of the Umbrella Add-on for Splunk Enterprise incorporates the following third-party software or libraries.

- opendns_categories.csv collected from https://api.opendns.com/v3/categories
- Log format reference: https://support.umbrella.com/hc/en-us/articles/231248508-Log-Management-Export-Format

##### Support and resources

**The Umbrella Add-on for Splunk Enterprise for Splunk Enterprise is community supported. If you require professional support, please contact the author**

* Support URL: https://github.com/inspired/TA-Umbrella/issues

**Best effort support is available via Splunk Answers**

* Access questions and answers specific to the Umbrella Add-on for Splunk Enterprise at http://answers.splunk.com/app/questions/3629.html

## INSTALLATION AND CONFIGURATION

### Hardware and software requirements

#### Hardware requirements

Umbrella Add-on for Splunk Enterprise supports the following server platforms in the versions supported by Splunk Enterprise:

- Windows 7, 8, and 8.1 (64-bit)
- Windows Server 2008, 2008 R2, 2012 and 2012 R2 (64-bit)
- Windows 7, and 8 and 8.1 (32-bit)
- Windows Server 2008 (32-bit)
- 2.6+ kernel Linux distributions (64-bit)
- 2.6+ kernel Linux distributions (32-bit)
- Solaris 10, 11 (64-bit)
- Solaris 10, 11 (SPARC)
- OSX 10.8 (Intel)
- OSX 10.9 (Intel)
- OSX 10.10 (Intel)
- FreeBSD 8, and 9 (64-bit)
- AIX 6.1, 7.1

#### Software requirements

To function properly, Umbrella Add-on for Splunk Enterprise requires the following software:

- Splunk Add-on for Amazon Web Services (https://splunkbase.splunk.com/app/1876/)

#### Splunk Enterprise system requirements

Because this add-on runs on Splunk Enterprise, all of the [Splunk Enterprise system requirements](http://docs.splunk.com/Documentation/Splunk/latest/Installation/Systemrequirements) apply.

#### Download

Download the Umbrella Add-on for Splunk Enterprise at https://apps.splunk.com/app/3629/.

#### Installation steps

To install and configure this app on your supported platform, follow these steps:

1. In your Splunk Enterprise web interface, click on App(s) -> Manage Apps
1. Click on Install app from file
1. Select the file you downloaded, Click Upload, optionally selecting Upgrade app if you are upgrading from an earlier version. Restart Splunk if required

##### Deploy to single server instance

Follow these steps to install the app in a single server instance of Splunk Enterprise:

1. In your Splunk Enterprise web interface, click on App(s) -> Manage Apps
1. Click on Install app from file
1. Select the file you downloaded, Click Upload, optionally selecting Upgrade app if you are upgrading from an earlier version. Restart Splunk if required

##### Deploy to distributed deployment

**Install to search head**

1. In your Splunk Enterprise web interface, click on App(s) -> Manage Apps
1. Click on Install app from file
1. Select the file you downloaded, Click Upload, optionally selecting Upgrade app if you are upgrading from an earlier version. Restart Splunk if required

**Install to indexers**

This app should not be installed on indexers

**Install to forwarders**

Install this app on a Heavy Forwarder used as a data collection node

1. Install the Umbrella Add-on for Splunk Enterprise in $SPLUNK_HOME/etc/apps/TA-Umbrella
2. Install the Splunk Add-on for AWS S3 from Splunkbase
3. Follow this guide to set up inputs for your AWS S3 bucket: https://support.umbrella.com/hc/en-us/articles/230650987-Configuring-Splunk-for-use-with-Cisco-Umbrella-Log-Management-in-AWS-S3
3.1. During Stage 2 of Step 3, make sure you set the sourcetype for your S3 input to opendns:dnslog

##### Deploy to distributed deployment with Search Head Pooling
Follow the same steps as *Install to search head*.
##### Deploy to distributed deployment with Search Head Clustering
Follow the same steps as *Install to search head*.
##### Deploy to Splunk Cloud
Unknown
#### Configure Umbrella Add-on for Splunk Enterprise

The following procedure should be followed on your Data Collection Node which may be a Heavy Forwarder or in the case of a single instance Splunk-deployment, your Splunk server:

1. Install the Umbrella Add-on for Splunk Enterprise in $SPLUNK_HOME/etc/apps/TA-Umbrella
2. Install the Splunk Add-on for AWS S3 from Splunkbase
3. Follow this guide to set up inputs for your AWS S3 bucket: https://support.umbrella.com/hc/en-us/articles/230650987-Configuring-Splunk-for-use-with-Cisco-Umbrella-Log-Management-in-AWS-S3
3.1. During Stage 2 of Step 3, make sure you set the sourcetype for your S3 input to opendns:dnslog

If you have a standalone Heavy Forwarder, follow all steps. On your search head you should only do step 1.

## USER GUIDE

### Data types

This app provides search-time knowledge for the following types of data:

**Search-time**

- opendns:dnslog - AWS S3 bucket CSV logs

These data types support the following Common Information Model data models:

| Source Type | CIM Data Models |
| --- | --- |
| opendns:dnslog | Network Resolution (DNS)|

### Lookups

The Umbrella Add-on for Splunk Enterprise contains 1 lookup files.

**opendns_categories.csv**

Lookup for OpenDNS category names

- File location: lookups/opendns_categories.csv
- Lookup fields: categoryId,name,description
- Lookup contents: See the file contents
