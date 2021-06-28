# CyberArk Plug-in Workflow Step Package

This package contains a Commander plug-in workflow step for Querying a CyberArk PAM Server for rotating credentials. The Queried credentials are then used with SSH or WinRM commands against a target VM/Instance.

It can be used with several Commander workflow extension scenarios, which can be found on the [Snow Software Support Knowledge Base](https://community.snowsoftware.com). It can also be used outside of Commander scenarios.

## Changelog

**Version 1.1:** Addition of WinRM support.
**Version 1.0:** Initial version.

## Plug-in steps in this package

+ CyberArk SSH
+ CyberArk WinRM

### CyberArk

**Purpose:** Run SSH command or WinRM command against a target with rotating Credentials from a CyberArk Server.

**Workflows supporting this plug-in step:**

 * COMMAND, COMPONENT_COMPLETION, SHARED_COMPLETION, CHANGE_COMPLETION

**CyberArk SSH Inputs:**

* Step Name: Input field for the name of the step
* Step Execution: Drop-down that sets the step execution behavior. By default, steps execute automatically. However, you can set the step to execute only for specific conditions.
* CyberArk server address: Input field for the DNS address of the CyberArk Server. 
* Sys Credentials: Input field for the credentials used to Query the CyberArk Server for VM and Instance Credentials
* Ingnore CyberArk Certificate: Check Box to Ignore an Unsigned CyberArk Server Instance in a Dev/Test Scenario
* Authentication Type: Dropdown Input Field to indicate the type of Credential being used to access the CyberArk Server
* Search Name: Input Field for the DNS or Container Name of the target VM or Instance used for lookup in the CyberArk Server.

* SSH Address: Input field for a reachable Address or DNS name of the Target VM or Instance workload
* SSH Port: Input Field Port used for SSH, Typically port 22. If required an alternate could be set. 
* Command Elevation: Dropdown Input Field, to select Elevation if it's required on the target VM or Instance with the queried credential type. 
* Command Line: Input text field for the Command to run against the Target VM or Instance. 

**CyberArk WinRM Inputs:**

* Step Name: Input field for the name of the step
* Step Execution: Drop-down that sets the step execution behavior. By default, steps execute automatically. However, you can set the step to execute only for specific conditions.
* CyberArk server address: Input field for the DNS address of the CyberArk Server. 
* Sys Credentials: Input field for the credentials used to Query the CyberArk Server for VM and Instance Credentials
* Ingnore CyberArk Certificate: Check Box to Ignore an Unsigned CyberArk Server Instance in a Dev/Test Scenario
* Authentication Type: Dropdown Input Field to indicate the type of Credential being used to access the CyberArk Server
* Search Name: Input Field for the DNS or Container Name of the target VM or Instance used for lookup in the CyberArk Server.

* WinRM Address: Input field for a reachable Address or DNS name of the Target VM or Instance workload
* WinRM Port: Input Field Port used for WinRM, Typically port 5985 or 5986. If required an alternate could be set. 
* Command Elevation: Dropdown Input Field, to select the WinRM Authentication type as required on the target VM or Instance with the queried credential type. 
* Command Line: Input text field for the Command to run against the Target VM or Instance. 

## Installation

Plug-in workflow steps are supported with Commander release 8.7 and higher. 

See [Adding plug-in workflow steps](https://docs.snowsoftware.com/commander/admin-portal/Using-Plug-In-WF-Steps.htm) in the Commander documentation to learn how to install this package. 

## Return codes
+ **0** - *Step completed successfully*


## Logging
To change the logging level, add the following named loggers to the Log4j configuration file located at: 

`<vcommander-install>\tomcat\common\classes\log4j2.xml` 

+ **General Utilities**
    + Loggers:
      + `<Logger level="DEBUG" name="wfplugins.cyberark.client"/>`
      + `<Logger level="DEBUG" name="wfplugins.cyberark.task"/>`
      + `<Logger level="DEBUG" name="wfplugins.cyberark.ssh"/>`
      + `<Logger level="DEBUG" name="wfplugins.cyberark.winrm.runner"/>`
      + `<Logger level="DEBUG" name="wfplugins.cyberark.winrm.task"/>`


