# Page Redirects for Moving or Permanently Removing Documents
Sometimes it is necessary to rename a document, or move it; this results in a change to the document's SEO-friendly URL. To ensure that indexers and references to those documents are not broken, we need to inform the requesters that the document has moved, or been permanently removed. Failing to do so will end up with broken links, which is a poor experience for end users, and will cause search rankings to be down-rated. To solve this problem, you should provide explicit document redirects to inform the documentation servers how to handle those requests. Typically, you are either reporting a permanent move to a new location, or a permanent removal of the content. Both are important to do. 

It is also possible to move content from one hdocbook to another, and in this case, you simply specify the redirect in the hdocbook where the content was moved from.

To achieve this, we are able to specify one or more redirects. These redirects are specified in the `hdocbook-project.json` file, in the `redirects` property, which is an array of redirect objects.  Each redirect object contains the following properties: -

- `url`: The fully rooted URI that is being deleted, for example "/hdoc-guide/some/place/the-moved-or-deleted-resource".
- `location`: The new location of the resource. This is optional in the case of a delete.  This is the URL that will be sent in the Location header.
- `code`: The HTTP response code, which can be 301, 308, or 410.  For 301/308, you are required to provide a valid `location` link. This property is optional; if you do not provide a code, the server will send a 410 response code if there is a URL match but no `location` property provided. If the location property is provided, then a 308 response code will be sent.
    - HTTP response code 301: Moved permanently - The requested page has moved to a new URL 
    - HTTP response code 308: Permanent redirect - 	The requested page has moved permanently to a new URL
    - HTTP response code 410: Gone - The requested page is no longer available     

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
    },
    "redirects": [
        { "url": "/hdoc-guide/some/path/to/previous-resource", "location": "/hdoc-guide/new/location/to-resource", "code": 301 },
        { "url": "/hdoc-guide/some/path/to/deleted-resource", "code": 410 }
    ]
}
```
