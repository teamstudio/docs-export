# docs-export

## Installation
* Install Python and pip
* Using pip, install
    * mkdocs
    * mkdocs-material
    * mkdocs-static-i18n
    * mike
 
## Develop and Test
Test the doc using
```
mkdocs serve
```

## Publish
Commit and push changes to the source markdown files on the main branch.

Tag the main branch with the appropriate version, in the format *v2.3.0*.

To redeploy an existing version, use
```
mike deploy <major>.<minor> -p
```

To deploy a new latest version, use
```
mike deploy <major>.<minor> latest -p -u
```

In these commands, `-p` pushes changes up to the gh-pages branch and `-u` is required to update the *latest* alias to point to the new version.
For more deployment options, consult the [mike](https://github.com/jimporter/mike) documentation.
