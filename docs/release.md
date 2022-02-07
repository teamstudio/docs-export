# Release Notes
## Teamstudio Export 4.3
Teamstudio Export 4.3 is a feature update to Export. It adds support for embedded views and stored forms, along with a number of fixes and enhancements.

The major new features of Export 4.3 include:

* **Embedded Views** - Export will now create a representation of embedded views when exporting to HTML or PDF. This feature works with existing archives - there is no need to regenerate the archive file.
  Most embedded views can be exported, but there are a few limitations. See [Exporting to HTML](html.md#embedded-views) or [Exporting to PDF](pdf.md#embedded-views) for details.
* **Stored Forms** - Export will now honor a stored form stored with a document rather than defaulting to the database default form. This feature also works with existing archives - there is no need to regenerate the archive file. You may encounter situations where the stored form rendering is missing some aspects of the original Notes document. Please contact support if you run into this.

Additional fixes are identified in the Fix List section below.

Please refer to [Installing Teamstudio Export](installing.md) for details on system requirements and installation. This page will be updated with any known issues and fixes as they become available.

## Fix List
### Export 4.3.0
179665914	Local database support is no longer in beta 
179665918	Japanese full-text indexing is no longer in beta
180136338	Empty tablerows can mess up rowspans
180381305	Certain Windows metafile images export as a black rectangle
180498324	Fix 'Parameter must be positive and < Width' error exporting a NotesBitmap
180500000	Use a valid bitmap in preference to a metafile
180515732	Protect against corrupt native NotesBitmap data
180563874	Error 'e-06' is an unknown unit type during PDF export
180562030	Protect against exceptions while displaying an unhandled exception
180565355	Add 'Support mode', additional options on the right-click menu if you hold down 'alt' when clicking.
180698882	HTML/PDF exports fail calling @Name on name with trailing $ sign
180731984	Error exporting to HTML/PDF for computed authors field with no default value formula
180739876	Add more protection against corrupt bitmaps
180829295	Support custom date formats
180882791	PDF export - Don't render underline or strikethrough for tabs.
180957791	Support commas in addition to periods as decimal separators in formulas
181038393	HTML significant characters in views don't render correctly
181144493	Add an option to hide templates in the UI
181162785	Update demo text to include a link to web site enquiry page
