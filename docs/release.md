# Release Notes
## Teamstudio Export 4.5.1
Teamstudio Export 4.5.1 is a maintenance update to Export. It contains a number of fixes and minor enhancements.

The major new features of Export 4.5 include:

* **OLE Support** - Export can now extract embedded Microsoft Office OLE objects. It supports Word, Excel and PowerPoint documents in both the older .doc, .xls and .ppt formats and the newer .docx, .xlsx and .pptx formats. Other document types will not be extracted. Please contact us if you need support for additional OLE object types.

* **Database Level Configuration** - Some applications rely on hide-when formulas using @UserRoles to control which parts of a form should be visible. Earlier versions of Export always returned an empty list for @UserRoles, resulting in incorrect output. Since user roles are specific to a particular database, it doesn't make sense to configure these in the global Export configuration. Export 4.5 adds the ability to configure, for each database, which roles should be returned by @UserRoles so that you can tailor the output as required. These settings are stored in the *config* folder of the PDF or HTML output and will be re-used for any subsequent exports of the same database.  Although rarely needed, you can also configure the value of @UserName and any notes.ini values that should be returned by @Environment.

Additional fixes are identified in the Fix List section below.

There is no need to re-archive your database to take advantage of any of the new features and fixes in Export 4.5.

Please refer to [Installing Teamstudio Export](installing.md) for details on system requirements and installation. This page will be updated with any known issues and fixes as they become available.

## Fix List
### Export 4.5.1
[185642000]	Support '\*' format in @Text  
[185659716]	Add a basic view when creating support files  
[185894864]	Improve handling of onread="collapse" sections  
[185769401]	Support imagemaps  
[186028370]	Allow exporting in read or print mode  
[186043382]	Incorrect search match highlight breaks images  
[186205126]	Possible hang when creating a support file by noteid  
[186216769]	Support Excel 5 OLE objects  
[186267662]	Handle "Word.Document" OLE type  
[186288032]	PDF export can fail with embedded attachments  
[186326438]	Support % characters in formulas  
[186489298]	Allow multiple descriptions for support file entries  
[186488956]	Embedded views are not included in support files  
[186572669]	@Adjust can fail with an OverflowException  
[186751698]	Support image resource icons in embedded views  
[186754146]	Improve edge cases in @Middle  
[186759675]	Support repeat="center" on cell background images  
[186775545]	Protect @GetField against an empty list argument  
[186775840]	Improve positioning of keyword fields in paragraphs  
[186813576]	Include profile documents in support files  
[186864681]	Non-pairwise (\*) operators can return incorrect results  
[187005613]	OpenExportFileWrite can fail under load  
[187013849]	Handle doclinks with no view attribute  
[187015303]	Tabbed tables don't honor fixed width on HTML  
[187056924]	Add an option to expand all sections  
[187093492]	Support OLE1 objects  
[187100941]	Support "ExcelWorksheet" object type  
[187128050]	Implement basic @Abstract rich text handling

### Export 4.5.0
[184587425]	Improve handling of missing $File items  
[184578743]	Handle attachments in forms/subforms  
[184633099]	Handle unsupported year formats  
[184666006]	Handle rowspans in PDF tabbed tables  
[184690086]	Support database-level configuration for @UserName, @UserRoles, @Environment  
[184764016]	Don't try to preview empty documents  
[184763654]	Support 'onread' = 'collapse' in sections  
[184764830]	Handle missing documents in @DbLookup  
[184835589]	Handle corruption in binary bitmaps  
[184836217]	meta.xml should be written without a BOM  
[184847648]	Protect against errant paragraphs inside runs  
[184873442]	Include item name in files.xml  
[184873262]	Unreferenced attachment names may not display correctly in PDF  
[184873249]	Improve detection of unreferenced attachments  
[184884947]	Protect against 0-length records in binary rich text  
[184893394]	Protect against errant paragraphs inside paragraphs  
[184972331]	Support @GetDocField  
[184992361]	Installer should offer to install shortcuts  
[184992632]	Improve wording on configuration dialog  
[185047386]	Support cross-database embedded views  
[185086409]	Set the $REF item for response documents  
[185086023]	Support TYPE\_NOTEREF\_LIST items in dxl  
[185103812]	Support 'weekday' custom date format  
[185131124]	Update code signing certificate  
[185140992]	Fix NPE for attachments on stored forms  
[185141852]	Ignore corrupt OLE object files  
[185142986]	Ignore OLE object files with missing segments  
[185152697]	Improve handling of corrupt tables in binary rich text  
[185216262]	Handle AttachmentRefs outside paragraphs in binary rich text  
[185249056]	Allow longer PDF documents to be created  
[185249094]	Disable style support in MigradocXML to improve PDF performance  
[185250993]	Handle errant runs in DXL tables  
[185252245]	Handle hidden Excel OLE objects  
[185260169]	Basic support for rich text in @Text  
[185260108]	Plain text in paragraphs may not display correctly in PDF  
[185297670]	@DbLookup views aren't always added to support files  
[185316756]	Handle @ERROR view numeric values in @DbLookup  
[185358166]	@ThisName should be available in keyword formulas  
[185466971]	Handle nested attachments at the end of binary rich text  
[185525338]	Computed fields should be evaluated if not present on the document  
[185577528]	Handle computed fields with no formula  
[185578342]	Support 'day' custom date format  
[185579036]	Add a timestamp to error logs  
[185592149]	Fix rare problem with one digit day/month custom formats
