# Installing Teamstudio Export

## System Requirements
Teamstudio Export installs onto a workstation. There is no server component and no changes are required to your Domino server other than ensuring that the user running Export has the necessary acess permissions if you will be creating archives.

## Workstation Requirements
* Windows 7, 8, 10

If you want to create new archives in addition to browsing and managing existing archives, then you will also need

* A Notes client install, version 8.5 or higher (version 10 or higher strongly recommended)
* A Notes ID with the necessary permissions to access the databases to be archived
* Free disk space in the TEMP folder (or on another volume) equal to roughly twice the size of the largest database you will archive

!!! note
    We recommend installing the most up-to-date Notes client available to you. Teamstudio Export uses the XML exporting capabilities provided by Notes itself and using the latest version will help to ensure that archives are as complete and accurate as possible. You do not need to upgrade your servers, only the client on the machine(s) where Export will run.

## Installation
Once you have a workstation that meets the requirements, you can download and install the latest version of Teamstudio Export from [teamstudio.com](https://www.teamstudio.com/downloads). The installer will install the program files and you can then proceed to launch the program and enter your license details. You can then continue to [Configuration](configuration.md).
