# Release Notes
## Teamstudio Export 4.2
Teamstudio Export 4.2 is a feature update to Export. It removes the limitation that table cells in PDF documents cannot span multiple pages, and can now export large nested tabbed tables. There are a number of other fixes and enhancements to improve robustness and PDF accuracy.

The major new features of Export 4.0 include:

* **Export to PDF** - Export can now export documents to PDFs, along with an HTML site containing the database views that can be used to navigate the PDFs. See [Exporting to PDF](pdf.md) for details. This feature will work with existing archives - there is no need to re-run the archive process.
* **Formulas from Hidden Designs** - Export can now export documents to HTML or PDF even if the original database design contains formulas from hidden designs. As with the Notes client, the formulas remain encrypted on disk (in the archive) but can be evaluated for display.
* **Encrypted Content** - Version 4.0.0 supports encrypted content, including file attachments.
   <div class="admonition note">
     <p class="admonition-title">Note</p>
    You will need to recreate any archives created with a version of Export earlier than 3.2.1 if you
    need to have access to encrypted content. The ID used to perform the archive must have access to the
    keys required to decrypt the content, otherwise a warning will be generated during archive. Note that
    the archive will contain the decrypted content and you should take any steps necessary to secure
    access to the archive.
     </p>
     <p>
     There is no need to re-archive databases that do not contain encrypted content.
     </p>
   </div>

Additional fixes are identified in the Fix List section below.

Please refer to [Installing Teamstudio Export](installing.md) for details on system requirements and installation. This page will be updated with any known issues and fixes as they become available.

## PDF Limitations
Converting Notes documents to PDF is a complex process and some Notes concepts do not map well to PDFs. This section lists some known limitations in the current version, but please contact our tech support team if you run into these or any other issues and we are happy to work with you to find a solution for your application.

### Doclinks and Attachments
While PDFs do an excellent job of providing a consistent display across devices and viewers, different PDF viewers behave very differently when handling links between files. Unfortunately, there is no one solution that works flawlessly in all environments. In our testing, relative web links worked with the most viewers for both file-system and server-hosted exports so that is the solution we have currently implemented as the default option. An option is available in the Export configuration to embed the attachment within the PDF, which may be the best option if you intend to utilize or distribute the PDFs separate from the viewer application produced by Export. At this time, however, most browsers cannot view embedded files and you will need to use Acrobat Reader or Firefox. Please contact us if you need a different solution in your environment.

## Fix List
### Export 4.2.1
179549001	URL links do not function correctly when exported to PDF (TMS-1452)  
179549002	Certain URL links can cause 'Name cannot begin with the & character...' error exporting to PDF (TMS-1453)  
179549004	Images taller than a single page cause multiple errors exporting to PDF (TMS-1454)  
179549006	Work around PDF viewers not handling network paths in URL Links (TMS-1455)  
179549007	Include the Export version number in stack traces (TMS-1456)  
179549009	Export uses the current locale when parsing decimal table column widths for PDFs (TMS-1457)  
179549014	Support for monochrome bitmaps (TMS-1458)  
179549015	Invalid cdstorage images cause html/pdf export to abort (TMS-1459)  
179549016	Support for NotesBitmaps that contain image data vs cdstoragelinks (TMS-1460)  
179549017	Doclinks don't work on HTML data hosted on SharePoint (TMS-1461)  
179549018	Attachments with long extensions can exceed the max windows path length (TMS-1462)  
179549020	Display warning if DxlExporter fails with a non-zero exit code (TMS-1463)  
179549023	Nested urllinks cause PDF export to fail (TMS-1464)  
179549024	Errors deleting and moving DXL file (TMS-1465)  
179531650	Archives should use a forward slash as the directory separator (TMS-1451)  
179552203	Remove lang="en" from the template index.html page  
179552189	Include UNIDs in Full Text Search  
179552074	Support for UNC file paths as the HTML/PDF output directory  
179584382	HTML UI doesn't correctly update to show views with no entries

### Export 4.2.0
[TMS-1428] - An invalid image can cause PDF export to abort  
[TMS-1431] - PDF page height for US Letter is incorrect  
[TMS-1432] - InvalidOperationException generating HTML/PDF with invalid numeric values  
[TMS-1433] - Support the 'weekday' date format  
[TMS-1434] - Support for NotesBitmap images  
[TMS-1435] - External doclinks in PDFs resolve to the HTML directory rather than the PDF directory  
[TMS-1436] - Installer signature expires May 2021  
[TMS-1438] - 'The format string is empty' error writing views with empty datetimeformats  
[TMS-1439] - Write a map file to convert attachment short names to their original names  
[TMS-1440] - String comparisons with empty strings in formulas are incorrect  
[TMS-1441] - PDF exporter doesn't handle encrypted formulas  
[TMS-1443] - Computed text should display numeric and date values, not just text  
[TMS-1444] - Intermittent XML parse errors when archives are on a network drive  
[TMS-1445] - Shared rich text fields on documents can cause PDF generation to fail  
[TMS-1446] - Table cells in PDFs cannot span multiple pages and are truncated  
[TMS-1447] - Scaled images are not sized appropriately  
[TMS-1448] - Support A3 page size and landscape orientation in PDF  
[TMS-1449] - Improve 'Error decompressing bitmap segment' handling during archiving  
[TMS-1450] - PDF nested tables don't respect colspan on their parent cell  

### Export 4.1.0
[TMS-1409] - Error exporting to PDF when a form references a missing subform with quotes etc in its name  
[TMS-1410] - Support @Repeat  
[TMS-1411] - PDF tables columns may extend into right margin  
[TMS-1412] - PDF tables created when a form is not available have extraneous backticks  
[TMS-1413] - Support for subtraction of datetimes in formulas  
[TMS-1414] - Pdf section headers with a border are always left-aligned regardless of paragraph style  
[TMS-1415] - Pdf export fails when a document references a font with a localized name from a TrueType Collection font  
[TMS-1416] - Support EmbeddedControl elements in HTML and PDF  
[TMS-1417] - Pdf Export should allocate more width to narrow columns when fixed width columns exceed the page width  
[TMS-1418] - FT Index grows massively when the data contains large base64 text fields  
[TMS-1419] - The archive log should show if the archive was built in demo mode  
[TMS-1420] - Run in demo mode if no serial number and key provided  
[TMS-1421] - Computed for display fields should not be evaluated if they already exist in the document  
[TMS-1422] - Support for @ThisName  

### Export 4.0.1
[TMS-1400] - PDF links to unreferenced attachments don't work on the web  
[TMS-1401] - Optionally support attachments embedded in PDFs, enabled in the advanced settings  
[TMS-1402] - Copying logs to the clipboard occasionally fails with 0x800401D0 and crashes Export  
[TMS-1403] - PDFs can use the display name for attachments, retaining the extension  
[TMS-1404] - Invalid attachment size causes HTML export to fail  
[TMS-1405] - PDF export fails when the document contains strings of backticks  
[TMS-1406] - Nested tables should ignore the left margin when computing width  
[TMS-1407] - Tables on subforms inside tables have the wrong width  
[TMS-1408] - Internet Explorer fails with blank page (Export 4.0.0)  