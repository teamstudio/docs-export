# Release Notes
## Teamstudio Export 5.0
Teamstudio Export 5.0 is a feature update to Export.

The major new feature of Export 5.0 is a powerful data exporter. This allows you to export data in a variety of formats:

* **SharePoint Lists** - Upload data to a new or existing SharePoint list, optionally including attachments.
* **CSV** - Generate text files delimited with commas or tabs.
* **Attachments** - Extract all attachments, OLE objects and embedded images.

For any output format, you can select documents in three different ways:

* **By Formula** - Similar to a view selection formula, using any @function supported by Export.
* **By View** - Includes all of the documents from an existing view.
* **By Search** - Export now includes the Apache Lucene.NET search library, allowing you to perform full-text searches on your data. The full-text search that Export uses when you export data to HTML/PDF needs to run within a browser using JavaScript. This places severe limitations on the features that it can provide. Lucene.NET, on the other hand, runs within Export and thus can offer a much more powerful experience. For example, you can search for phrases rather than single words, and can also exclude documents matching certain terms.

In addition to selecting which documents to include, you can also specify the data to be exported, in the form of one or more columns. When you select documents by formula or by search the columns can be any fields from the database design or any computed expressions using @formulas. When you select documents by view, the columns will initially be all of the columns defined in the view along with a column for the Note ID. You can re-order the columns and remove any unwanted ones, but you cannot add new values.

For full details on the new data export features, see [Exporting Data](data.md).

Additional fixes are identified in the Fix List section below.

There is no need to re-archive your database to take advantage of any of the new features and fixes in Export 5.0.

Please refer to [Installing Teamstudio Export](installing.md) for details on system requirements and installation. This page will be updated with any known issues and fixes as they become available.

## Fix List
### Export 5.0.1
[478] Handle missing Content-Type in SharePoint upload  
[479] SharePoint upload fails with "Unauthorized" error  
[480] Improve error message when refresh hits a corrupt archive  
[481] Improve SharePoint connection logging  
[482] Create a separate MSAL cache for each site  
[483] Support Visio.Drawing.4 OLE type  
[484] Handle additional invalid file name characters in data export  
[485] Do not automatically index SharePoint list columns  
[486] Trim attachment filenames in data export  
[487] Handle additional invalid file name character in data export  
[488] Handle Package OLE2 objects  
[489] Repair right-click support file generation  
[490] Embedded view column widths incorrect in European locales  
[491] Support @ sign in variable names  
[492] Support @ServerName  
[493] Handle large note ids in archived views  
[494] Skip PaintShopPro OLE 1 objects  
[495] Support Excel.Chart.5 OLE 1 type  
[496] Skip images specified by URL  
[497] Handle invalid row/colspans in stored forms  
[498] Handle text horizontal alignment in stored forms  
[499] Handle page breaks in stored forms  
[500] Table margins may be incorrect in older databases  
[501] Table margins may be incorrect in stored forms  
[502] Support Visio.Drawing.3 OLE type  
[503] Unreferenced attachments do not embed correctly in PDFs  
[504] Handle OLE object references with no attachments  
[505] Dedupe multiple periods in attachment file names  
[506] Handle $file objects with an empty name  
[507] Improve section title background handling

### Export 5.0.0
[187316243]	Handle missing view data file in @DbLookup  
[187318928]	Provide a way to import DXL to an archive  
[187363948]	Protect against invalid attachment names  
[187408442]	Handle multi-value icon columns in embedded views  
[187416749]	Handle multi-line entries in embedded views  
[187486941]	Include TYPE\_NOTEREF\_LIST items in full text index  
[187540358]	Add beta option to size PDF images to fit  
[187694126]	Protect against @Created in column hide formula  
[187703998]	Support cross-database @DbLookups  
[187937349]	Support 'PBrush' and 'AutoCAD' OLE types  
[187961958]	Support 'Paint.Picture' and 'SoundRec' OLE types  
[188164406] Improve display of long decimal numbers