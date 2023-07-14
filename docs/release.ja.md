# Release Notes
## Teamstudio Export 4.5
Teamstudio Export 4.5 is a feature update to Export. It adds support for embedded Microsoft Office OLE objects, along with many fixes and enhancements.

The major new features of Export 4.5 include:

* **OLE Support** - Export can now extract embedded Microsoft Office OLE objects. It supports Word, Office and PowerPoint documents in both the older .doc, .xls and .ppt formats and the newer .docx, .xlsx and .pptx formats. Other document types will not be extracted. Please contact us if you need support for additional OLE object types.

* **Database Level Configuration** - Some applications rely on hide-when formulas using @UserRoles to control which parts of a form should be visible. Earlier versions of Export always returned an empty list for @UserRoles, resulting in incorrect output. Since user roles are specific to a particular database, it doesn't make sense to configure these in the global Export configuration. Export 4.5 adds the ability to configure, for each database, which roles should be returned by @UserRoles so that you can tailor the output as required. These settings are stored in the *config* folder of the PDF or HTML output and will be re-used for any subsequent exports of the same database.  Although rarely needed, you can also configure the value of @UserName and any notes.ini values that should be returned by @Environment.

Additional fixes are identified in the Fix List section below.

There is no need to re-archive your database to take advantage of any of the new features and fixes in Export 4.5.

Please refer to [Installing Teamstudio Export](installing.md) for details on system requirements and installation. This page will be updated with any known issues and fixes as they become available.

## Fix List
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
