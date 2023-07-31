# The HDocBook Specification
The source content for a Book is made up of a folder structure containing any number of documents which can be authored in Markdown, or as plain HTML. This specification is called HDocBook and is defined in this article.

## Book ID
Every HDocBook project needs to be allocated a Book ID. This ID will uniquely and globally identify each Book (just like an ISBN does for a physical book). This ID must be allocated by the Hornbill Docs Team on request; these IDs are globally unique, and maintained within a central list.

## Folder Structure
The folder structure of a HDocBook project is organized as a typical Node.js assisted development project.  

- The root folder contains a hdocbook-project.json file, which is required and used by the preview server and document build tools to identify the Book ID (docId) for the project.
- The root folder of the project must contain a folder whose name is the same as the Book ID for the project. All HDocBook content should appear inside this folder. 
- The '/resources' folder.  When creating content, for example images and illustrations, while the resultant image will be included within the published content, you should also keep any files, for example Photoshop or PowerPoint files, that are used in the creation of the images. This way, should the image need to be updated in the future, we will have the source for that image to hand.  

### Folder Structure Example
``` md
  [some location on your disk]
   ├── <doc-id>
   │   ├── hdocbook.json
   │   └── **/* (any content goes in here)
   ├── resources/   
   ├── hdocbook-project.json
   ├── package.json
   └── README.md
```

## hdocbook-project.json file

This file contains configuration settings used by the supporting HDocBook development and build tools. The most important property inside this file is the `docId` property, which tells the tools the name of the folder where the hdocbook.json file can be found. The file also includes several other properties that control the PDF generation and book validation components when validating and building books. 

The `pdfGeneration` property is an object containing two other properties:

- `enable`: boolean true or false - should the book build process generate PDFs for page content
- `exclude_paths`: an array of strings, paths (fully qualified root relevant paths, and supports wildcards) that should be excluded from the PDF generation process

The `validation` property is an object that contains properties to control various aspects of book validation:

- `exclude_links`: an array of strings, containing links that should be excluded from the validation process. These could be example links that do not actually exist, or endpoints that are not available to the book build and publishing processes
- `exclude_spellcheck`: an array of objects, where `document_path` is the root relevant path to the document that should have additional validation exclusions applied, and `words` which is an array of strings, containing a list of words that should be excluded from the US - UK spell check validation
- `exclude_h1_count`: an array of strings, containing rot-relevant paths of articles within the book that should be excluded from the H1 heading count validation

Here is an example of the project file:

``` json
{
    "docId": "hdoc-guide",
    "pdfGeneration": {
        "enable": true,
        "exclude_paths": [
            "hdoc-guide/concepts/*"
        ]
    },
    "validation": {
        "exclude_links": [
            "http://www.hornbill.com/thefile.pdf",
            "http://some-url.com/api"
        ],
        "exclude_spellcheck": [
            {
                "document_path": "hdoc-guide/hdocbook/frontmatter.md",
                "words": [
                    "labeled",
                    "favorite"
                ]
            }
        ],
        "exclude_h1_count": [
            "hdoc-guide/hdocbook/markdown"
        ]
    }
}
```

## hdocbook.json file

Located in the root of the &lt;doc-id&gt; folder, the hdocbook.json file provides information needed to describe the HDocBook, its navigation, keywords, taxonomy, and other metadata. The following properties are defined at the top level of this file:

|Property|Description|
|:---|:---|
|`docId`|This is the document ID and should be set to the exact same name as the folder that the hdocbook.json file sits in.|
|`title`|The title of this Book.|
|`description`|A short description of the contents/purpose of this Book.|
|`coverImage`|Fully-qualified [optional] path from root for an image used as a cover image. This will be used for gallery rendering and social sharing. If not specified, a global generic image will be used.|
|`audience`|[array] Defines the audience that this HDocBook will be published to.|
|`publicSourceCode`|A URL to the public source location of the HDocBook. If not specified, this HdocBook is considered private.|
|`version`|A version tag which identifies the revision number of this Book. This also controls automated publishing. Do not change this as an external contributor.|
|`navigation`|An object containing the definition of the navigation that is presented to the left of the documentation.<br><br>The navigation object contains an items[] array containing the top-level navigation items. See the table below for navigation item properties.| 

## Controlling Document Publishing

Each document being publshed is added to a list on one of the publishing servers. The publishing server will poll the repository for each document and will keep track of the last published version.  When the publishing detects a change in version number for a given document, the publishing server will clone a copy of the repository, build, package, and publish to the required server(s) automatically.  

::: warning
For external contributions, no pull requests that include a version number change in the hdocbook.json file will be accepted into the main repository. 
:::

### Navigation Item Properties
|Property|Description|
|:---|:---|
|`text`|The text displayed on the navigation view for this navigation item.|
|`link`|The link to the content page you want this item to navigate to (this is ignored if `items` is present).|
|`expand`|Set this to "true" you want this item to expand on refresh (assuming there are child navigation items).|
|`draft`|Set this to "true" you want this item to be in draft mode. This means while the link is still available in the development workflow and preview server, this link will be removed and unavailable when published.  Default if not present is "false"|
|`items[]`|An array of child navigation items. There are only three levels allowed, so levels defined beyond this are ignored.|

Here is an example configuration, showing the file used to define this HDocBook:

``` json
{
    "docId": "hdoc-guide",
    "title": "Hornbill Docs Contributor Guide",
    "description": "Information about developing and publishing documentation on the Hornbill Docs (docs.hornbill.com) website",
    "publicSourceCode": "https://github.com/Hornbill-Docs/hdoc-guide",
    "version": "1.0.0",
    "navigation": {
        "items": [
            {
                "text": "Introduction",
                "expand": true,
                "items": [
                    {
                        "text": "Welcome",
                        "link": "hdoc-guide/index"
                    },
                    {
                        "text": "Concepts",
                        "expand": true,
                        "items": [
                            {
                                "text": "Overview",
                                "link": "hdoc-guide/overview",
                                "draft": true
                            },
                            {
                                "text": "HDocBook",
                                "link": "hdoc-guide/concepts/hdocbook"
                            },
                            {
                                "text": "Library",
                                "link": "hdoc-guide/concepts/library"
                            },
                            {
                                "text": "Publishing",
                                "link": "hdoc-guide/concepts/publishing"
                            }
                        ]
                    },
                    {
                        "text": "Getting Started",
                        "expand": true,
                        "items": [
                            {
                                "text": "1. Create a GitHub Account",
                                "link": "hdoc-guide/getting-started/github"
                            },
                            {
                                "text": "2. Install HDocBook Tools",
                                "link": "hdoc-guide/getting-started/tools"
                            },
                            {
                                "text": "3. Clone A Book Repository",
                                "link": "hdoc-guide/getting-started/clone-repo"
                            }
                        ]
                    },
                    {
                        "text": "HDocBook Reference",
                        "expand": true,
                        "items": [
                            {
                                "text": "Specification",
                                "link": "hdoc-guide/hdocbook/specification"
                            },
                            {
                                "text": "Markdown Syntax",
                                "link": "hdoc-guide/hdocbook/markdown"
                            },
                            {
                                "text": "Layout Templates",
                                "link": "hdoc-guide/hdocbook/layout-templates"
                            },
                            {
                                "text": "Frontmatter",
                                "link": "hdoc-guide/hdocbook/frontmatter"
                            },
                            {
                                "text": "Server Variables",
                                "link": "hdoc-guide/hdocbook/server-variables"
                            }
                        ]
                    },
                    {
                        "text": "Other Useful Resources",
                        "link": "hdoc-guide/additional-resources"
                    }
                ]
            }
        ]
    }
}
```

### Audience
The Hornbill Docs publishing system is used to publish documentation to customers, as well as partners and internal Hornbill employees. The audiences are defined in the table below. 

|Audience|Description|
|:---|:---|
|`private`|Any internal Hornbill user.|
|`private.cloud`|Any member of the cloud team, relates to cloud operations, systems, processes and procedures etc.|
|`private.dev.platform`|Any member of the platform dev team, relates to development processes, systems, tools, reference guides etc.|
|`private.dev.apps`|Any member of the application dev team, relates primarily to development processes, tools, reference guides etc.|
|`private.hdocs`|Any member of the Hornbill Docs team.|
|`private.elearning`|Any member of the Hornbill E-Learning team.|
|`public`|Anyone inside or outside of Hornbill.|
