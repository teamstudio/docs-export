# Release Notes
## Teamstudio Export 4.4
Teamstudio Export 4.4 is a feature update to Export. It adds support for @DbLookup, along with many fixes and enhancements.

The major new features of Export 4.4 include:

* **@DbLookup** - Export can now evaluate @DbLookup calls within the current database. All of the common @DbLookup options are supported, but note that lookups that retrieve data from the document rather than the view may run very slowly in Export. However, since exported data is read only, all lookups can be cached which will help offset the performance cost. This feature works with existing archives - there is no need to regenerate the archive file.

* **Binary Rich Text** - Export generally relies on Notes to convert rich text into XML within the DXL files. In some cases, typically where there is some corruption in the document, Notes is unable to convert rich text to XML and saves the raw binary data to the DXL file instead. Earlier versions of Export ignored this binary rich text data when exporting to HTML/PDF, but Export 4.4 will now attempt to display it. Depending on the severity of the corruption, Export may not be able to convert it, and in that case it will display the message *Invalid Rich Text* instead. These messages can typically be fixed by opening the affected document in the Notes client, making a simple edit (e.g. adding and removing a space), resaving the document and regenerating the archive.

Additional fixes are identified in the Fix List section below.

There is no need to re-archive your database to take advantage of the most of the new features and fixes in Export 4.4. The only exception is the fix for the missing *db.dxl* file in archives. If you encounter an *object reference not set to an instance of an object* error during HTML/PDF export and have no db.dxl file in the corresponding archive, regenerating the archive with Export 4.4 will solve the problem.

Please refer to [Installing Teamstudio Export](installing.md) for details on system requirements and installation. This page will be updated with any known issues and fixes as they become available.

## Fix List
### Export 4.4.1
[183595114]	Add notranslate attributes to the HTML/PDF sites  
[183621773]	An error creating db.dxl should halt archiving  
[183621836]	DxlExporter fails to generate db.dxl with a timeout  
[183623774]	PDF export fails with invalid binary rt tables  
[183632221]	Add more protection against bad data in binary rich text  
[183681762]	Improve WriteMarkerFile error handling  
[183681036]	Unable to access log file when archiving fails  
[183680706]	Jobs window leaves 'Cleaning up temporary files' message when displaying archive error  
[183680251]	Display save/replication conflicts in views  
[183692935]	Support view column hide formulas  
[183743597]	Support non-text keys in @DbLookup  
[183754923]	Render checkbox and radio button fields  
[183783673]	Improve embedded view formatting  
[183952090]	Provide limited support for invalid field names  
[183952259]	Ignore file items that aren't named $file  
[183954016]	Always display checkbox/radio button characters in black on PDF  
[184094392]	Handle nested attachments in binary rich text  
[184155752]	OutOfMemoryException loading processing large document with stored form  
[184165648]	PDF - Handle fonts with invalid cmap  
[184199258]	Subform lookup in stored forms should also search database  
[184197574]	Ignore embedded subform bodies in stored forms  
[184093717]	InvalidOperationException in @DbLookup  
[184261228]	Create support files for failed view exports  
[184274174]	Bump copyright year to 2023  
[184274148]	Handle shared keyword fields in PDF  
[184282155]	Handle unavailable values as @DbLookup keys  
[184282018]	Handle empty strings in @DbLookup  
[184298267]	Support computed URL links  
[184366765]	Handle paragraphs within attachmentrefs in binary rich text  

### Export 4.4.0
[181489567]	HTML/PDF export fails if an embedded view data file is missing  
[181505115]	Paragraphs directly in a tablerow (i.e., not in a tablecell) cause HTML and PDF export to fail  
[181564495]	PDF export fails with extraneous table columns  
[181588431]	Support "month" custom date format  
[181588978]	Handle computed imagerefs in stored forms  
[181613461]	Error exporting certain native NotesBitmaps  
[181659131]	Improve thread-safety of PDF generation  
[181779390]	Improve exception reporting during HTML/PDF export  
[181779342]	Improve error reporting when adding formatted text to a PDF  
[181781782]	Handle case differences in attachment references and $File names  
[181827402]	Handle missing attachments in PDF embed mode  
[181860691]	Unreferenced attachments leak an icon handle, ultimately causing Export to crash  
[181860746]	Protect the unhandled exception handler against recursion  
[181904774]	Handle missing colortable when checking for a bitmap metafile alternate  
[181964782]	Support computed subforms in stored forms  
[181964789]	Handle aliases in stored subforms  
[182005300]	Support formulas with no whitespace after REM/SELECT  
[182004980]	SELECT formulas parse but fail at runtime  
[182057508]	Support @Sqrt  
[182067660]	Support @Transform and @Nothing  
[182120640]	Support page breaks in PDF  
[182151133]	Error exporting to PDF when text begins with a Unicode combining character  
[182185976]	Export hangs with an empty DXL document  
[182218239]	Horizontal rules inside urllinks cause PDF export to fail  
[182250778]	@Length should return 0 for an empty list  
[182278248]	Handle empty text lists in computed image refs  
[182281270]	Support @ThisName in compiled formulas  
[182281249]	Support @ThisValue  
[182280872]	Computed fields should evaluate if the field is missing from the original document  
[182279873]	Support @SetField  
[182280528]	Fully implement FIELD assignment  
[182302659]	Support 'edit' and 'datetime' embedded controls  
[182303634]	DateTimePair field values don't render in HTML/PDF  
[182303204]	Handle self-closed datetimes in DXL  
[182337594]	Ignore page breaks inside a table cell  
[182365580]	Protect IndexRtItems against document modifications  
[182379274]	Prevent embedded view error when view has no entries  
[182395232]	Support descending category sort in embedded views  
[182575000]	Handle missing pattern table when checking for a bitmap metafile alternate  
[182578735]	Handle linebreaks in embedded field values  
[182588109]	Allow longer PDF documents to be created  
[182590994]	Tables with cells that span both rows and columns do not export to PDF correctly  
[182611234]	Add count and size attributes to files.xml  
[182752420]	Handle self-assignment in default value formulas  
[182754402]	Support raw rich text data  
[182795881]	Handle non-xml chars in binary rich text  
[182796727]	Upgrade third-party dependencies  
[182812479]	Handle missing CDPARAGRAPHs in binary rich text  
[182812845]	Handle nested attachment hotspots in binary rich text  
[182839715]	Support 'checkmark' list style  
[182823807]	Support embedded combobox controls  
[183082205]	Handle binary rich text that cannot be converted to DXL  
[183085117]	Url links with ampersands corrupted when exported to PDF  
[183086033]	Handle non-xml chars in embedded field values  
[183094808]	Support @LeftBack  
[183132002]	Support for font linking  
[183131534]	Support for embedded checkbox fields  
[183161561]	Date component @functions should return -1 on empty argument  
[183194389]	Create db.dxl ourselves rather than using DxlExportIDTable  
[183256652]	Stop invalid NotesBitmaps terminating an export  
[183256261]	Allow invalid colors when processing bitmaps  
[183304950]	Allow orphaned table cells in binary rich text  
[183304812]	PDF - Set a minimum width of 1% on table columns  
[183304731]	PDF - prevent paragraphs/tables from indenting more than the current width  
[183332385]	Doclinks should be more forgiving of missing views  
[183331946]	Handle bad doclinks consistently  
[183346159]	Left margins may be incorrect rendering binary rich text  
[183346055]	Handle table cell background colors in binary rich text  
[183346515]	Handle hide formula references in binary rich text  
[183346397]	Handle pre-subform embedded forms  
[183488422]	@Adjust fails with NaN argument values
