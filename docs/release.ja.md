# Release Notes
## Teamstudio Export 5.1
Teamstudio Export 5.1 is a feature update to Export.

The data export feature introduced in Export 5.0 has been updated to allow you to save and reload your data selection criteria. This includes your specific selection (formula, view, or search) as well as the list of columns to be exported.

Export 5.1 has transitioned to *.NET 10*, replacing the older .NET Framework used in all previous versions. We now bundle a local .NET runtime directly with Export. While this increases the download and install size, it removes the need for a shared .NET installation on your computer. 

This architectural shift provides several key benefits:

* **Simplified Deployment:** Eliminates bugs caused by subtle differences in user-installed .NET Framework versions.
* **Cutting-Edge Security:** Allows Export to take advantage of the newest, most secure .NET features.
* **Easier Maintenance:** Simplifies the process of updating Export if vulnerabilities are ever discovered in .NET or third-party libraries.

Lastly, we have updated our code signing to use *Microsoft Artifact Signing*. This improves security by utilizing short-lived certificates that are valid for only 3 days. Because of this, *it is normal and expected for the certificate to appear expired by the time you install the product.* Rest assured, our signatures are all securely timestamped at the exact moment of signing. As long as the certificate was valid when the product was signed, the signature remains completely valid. Expiring the certificates quickly simply ensures they cannot be misused if they ever fall into the wrong hands.

Additional fixes are identified in the Fix List section below.

Please refer to [Installing Teamstudio Export](installing.md) for details on system requirements and installation. This page will be updated with any known issues and fixes as they become available.

## Fix List
### Export 5.1.0
[545] Fix debug warnings from SQLite  
[546] Constant columns are not properly handled in @DbLookup  
[547] Update Code Signing Certificate  
[548] Improve handling of corrupt Base64 attachments  
[549] Support @While  
[550] Fix HTML generation for aligned paragraphs with custom bullets  
[551] Fix PDF error with relative/ambiguous URL links  
[552] Data for views hidden from the client is not archived  
[553] Fix 'cannot access file' exception processing certain corrupt OLE objects  
[554] Support Visio.Drawing.5 OLE type