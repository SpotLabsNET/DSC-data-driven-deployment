[![Build status](https://ci.appveyor.com/api/projects/status/6a59vfritv4kbc7d/branch/master?svg=true)](https://ci.appveyor.com/project/Microsoft/DSC-data-driven-deployment/branch/master)

#Lab In a Box
Utility to allow developers to spin up a sandbox lab environment quickly.    Virtual machines will be created on a private network without access to host. 
 
#Why
Getting started with DSC can be difficult for developers because they don't have control over all over their environment.  Often its difficult to validate secure configurations due to the need for certificates.  With LabInaBox these restrictions are lifted since its all encompassed in a sandbox.  Active Directory and Certificate services are already installed and configured allowing developers to begin testing their configurations as soon as the deployment is complete.

##Prerequisites
* Machine running Windows 10 or Windows Server 2016
* 16GB of Memory
* Sysprepped image of Windows 2016
	* Can utilize windows Core or Full
	* Should leverage an answer file  

##Installation
* Download LabInaBox to a USB drive
* Create folder under LabInaBox named ParentDisks
* Copy your sysprepped image of Windows 2016 to ParentDisks
	* AnswerFile Reference: [https://technet.microsoft.com/en-us/library/cc749317(v=ws.10).aspx](https://technet.microsoft.com/en-us/library/cc749317(v=ws.10).aspx "Building a Simple Answer File")
	* Sysprep Command Reference: [https://technet.microsoft.com/en-us/library/hh825033.aspx](https://technet.microsoft.com/en-us/library/hh825033.aspx "Sysprep Command Line")
* Open PowerShell ISE as an administrator
* Open Main_Setup.ps1
* Read through Required Variables to Configure and Optional Variables to Configure
* LabInaBox will utilize your sysprep drive in as a parent differencing disk
	* Reference: [https://technet.microsoft.com/en-us/library/cc720381(v=ws.10).aspx](https://technet.microsoft.com/en-us/library/cc720381(v=ws.10).aspx "Using differencing disks")
* For the best performance parent and child disks should be on different disk drives
* Ensure you update the $Parent and $ChildDrive variables to the drives for your machine
* Modify $localAdminPass and $domainAdminPass to your liking 
* Modify $sysPrepDriveName and $DCSysPrepDriveName to point to match your name
	* I have provided two names here in-case you want to utilize Windows Core for your Domain Controller
* Modify $DCMachineName $DSCentral and $DomainJoinServers variables
* Execute Script
* If Hyper-V is not installed on the machine a reboot will be required and the script will need to be executed one final time.

##Assumptions
* Requires Windows 10 or Server 2016 as the Host Operating System
* Requires Windows 2016 as a Guest OS.

##Contribute
There are many ways to contribute.
Submit bugs and help us verify fixes as they are checked in.
Review code changes.
Contribute bug fixes and features.
For code contributions, you will need to complete a Contributor License Agreement (CLA). Briefly, this agreement testifies that you grant us permission to use the submitted change according to the terms of the project's license, and that the work being submitted is under the appropriate copyright.
Please submit a Contributor License Agreement (CLA) before submitting a pull request. You may visit https://cla.microsoft.com to sign digitally. Alternatively, download the agreement Microsoft Contribution License Agreement.pdf, sign, scan, and email it back to cla@microsoft.com. Be sure to include your GitHub user name along with the agreement. Once we have received the signed CLA, we'll review the request.
Code of Conduct
This project has adopted the Microsoft Open Source Code of Conduct. For more information see the Code of Conduct FAQ or contact opencode@microsoft.com with any additional questions or comments.
License
This project is licensed under the MIT License.