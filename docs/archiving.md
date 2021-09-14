# Archiving

Teamstudio Export can generate an archive file from a Notes database. The archive file contains a complete copy of all of the design and data from the database but is stored in a simple, XML-based format that can be accessed with no proprietary tools or libraries. See [Archive File Format](archive.md) for more details on the structure of an archive file.

!!! note
    You need an active subscription to use the Teamstudio Export tool to **generate** archives, but
    the archives themselves simply contain your data and do not have any licensing or runtime costs.
   
To create archives, select the database or databases to be exported from the main window, right-click on one of the selected databases, and select *Archive* from the context menu. As with standard Windows controls, you can use *Ctrl-Click* to select a range of databases and Alt*-Click* to add a database to the selection. You do not need to wait for all existing archive operations to complete before adding more, but note that Export will run at most 3 tasks at once and all other tasks will be queued until earlier operations have completed.

You can view the status of any active and queued archiving tasks from the [Progress Window](progress.md). Please see that page for details of how to handle errors and warnings encountered during archiving.