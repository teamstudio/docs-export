# HTML View and Field Display

Teamstudio Export can generate a static HTML site from an archive. By default, the HTML site displays all of the non-hidden views in the original application, and all of the fields found on the exported documents.  Some Notes applications contain a significant number of views and fields that are used by application logic.  Often, these views and fields do not provide useful information to the end-user and impede the end user's ability to locate relevant information.
Teamstudio Export supports configuration settings within the exported HTML site that can be used to:

* control which views are displayed
* control which fields are displayed, including the order of display, and optionally provide field labels

!!! note
    Configuration settings for an HTML site are located inside the site's HTML folder (the .tse folder),
    at config/config.js. Documentation for configuring view and field display, along with examples can be
    found in the default config.js file generated when a site is created.

## The Configuration File
The configuration file (config.js) is essentially a JavaScript / JSON configuration file, similar to properties files used by many modern web technologies.  To allow an HTML site to be self-contained and browsed locally without the use of a web server, the JavaScript object that represents the configuration properties is registered with the application by passing it to a function ('tmsData') that is called when config.js is loaded by the browser.  The default config.js file contains comments documenting this function, along with example settings that can be uncommented and modified as appropriate. A basic understanding of JavaScript syntax and JSON is helpful when editing this file.

!!! note
    The web application must be reloaded in the browser for changes to the config.js file to take effect.
    
!!! note
    The file config-base.js contains default settings, and is overwritten with each HTML export. 
    The config.js file is only created the first time an HTML export is created, and can override
    properties in config-base.js.  See config-base.js for information on properties that are overridden
    in groups.

## Default View Display
By default, views are displayed if:

* they are not hidden (the view name does not start with the '(' character)
* they are recognized as a *special view name* in standard Notes templates, for example, *($Inbox)*

When *special view names* are encountered, Export tries to apply the same title that the Notes client uses, for example, a view named *($All)* is displayed as *All Documents*, and *($Inbox)* as *Inbox*.

The mapping of view names is provided by config-base.js in the function assigned to the *views.filterFn* property.  This function can be copied to the same property in config.js, and adapted as desired to override the default handling.

## Filtering Views
The configuration allows control of which views are displayed by:

* explicitly listing the views to display
* providing a JavaScript function that accepts an array of available view names and returns an array of views to show
* disabling the default hiding of views that start with '(' 

!!! note
    Views that start with '(' are filtered by default in Export 2.0 and later.

A simple config.js filtering views
``` javascript
window.tmsData('config.js', {
   views: { filter: [ 'all', 'by date', 'by author'] }
});
```

See the default config.js file for detailed examples of view filters.

## Filtering Fields
The configuration allows control of which fields are displayed for a particular form by:

* explicitly listing the fields to display, in display order
* explicitly listing fields to display along with the labels to display for the fields
* providing a JavaScript function that accepts an array of field names and returns an array of fields to show in one of the above formats

A simple config.js filtering fields
``` javascript
window.tmsData('config.js', {
    forms: 
        {
        'Main Topic':
            {
                'fields': [
                    {name: 'Created', label: 'Date of publication'},
                    {name: 'Subject', label: 'Topic'}
                ]
            }
        }
});
```

!!! note
    The view generated in the *Preview* tab is created by rendering the document based on the form
    design, and is not influenced by the *forms* property in the config.js file. These settings
    control display of the fields in the *Data* tab only.

See the default config.js file for detailed examples of field filters.
