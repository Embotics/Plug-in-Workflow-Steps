# CyberArk Plug-in Workflow Step Package

This package contains a Commander plug-in workflow step for using CyberArk Credentials for SSH and WinRM commands to a target VM/Instance.

It can be used with several Commander workflow extension scenarios, which can be found on the [Embotics Support Knowledge Base](https://support.embotics.com/support/home). It can also be used outside of Commander scenarios.

## Changelog

**Version 1.1:** Addition of WinRM support.
**Version 1.0:** Initial version supporing SSH.

## Plug-in steps in this package

+ CyberArk SSH
+ CyberArk WinRM

### CyberArk

**Purpose:** Run SSH command or WinRM command against a target with rotating Credentials from CyberArk.

**Workflows supporting this plug-in step:**

 * COMMAND, COMPONENT_COMPLETION, SHARED_COMPLETION, CHANGE_COMPLETION

**CyberArk SSH Inputs:**

* Step Name: Input field for the name of the step
* Step Execution: Drop-down that sets the step execution behavior. By default, steps execute automatically. However, you can set the step to execute only for specific conditions.
* To: Input field for the "To" recipients. Single email address or semi-colon-separated list of addresses. 
* CC: (Optional) Input field for the "CC" recipients. Single email address or or semi-colon-separated list of addresses.
* Subject: Input field for the email subject
* Body: Text area for the email body
* Attachment: (Optional) Input field for the attachment. Can be a file accessible to the Commander service account, in-line content, or a variable that resolves to a file or the attachment content.
* Content Type: (Optional) Input field for the attachment content type. Required if attachment is specified. For valid options, see https://www.iana.org/assignments/media-types/media-types.xhtml.

**CyberArk WinRM Inputs:**

* Step Name: Input field for the name of the step
* Step Execution: Drop-down that sets the step execution behavior. By default, steps execute automatically. However, you can set the step to execute only for specific conditions.
* To: Input field for the "To" recipients. Single email address or semi-colon-separated list of addresses. 
* CC: (Optional) Input field for the "CC" recipients. Single email address or or semi-colon-separated list of addresses.
* Subject: Input field for the email subject
* Body: Text area for the email body
* Attachment: (Optional) Input field for the attachment. Can be a file accessible to the Commander service account, in-line content, or a variable that resolves to a file or the attachment content.
* Content Type: (Optional) Input field for the attachment content type. Required if attachment is specified. For valid options, see https://www.iana.org/assignments/media-types/media-types.xhtml.

## Installation

Plug-in workflow steps are supported with Commander release 8.7 and higher. 

See [Adding plug-in workflow steps](https://docs.embotics.com/Commander/Using-Plug-In-WF-Steps.htm#Adding) in the Commander documentation to learn how to install this package. 

## Return codes

### Generic return codes
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


