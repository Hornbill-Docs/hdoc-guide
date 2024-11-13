# HDocBook Overview

A **HDocBook** (or book for short) is the name we give to a collection of individual, but related Articles.  As well as including a collection of written articles that make up the content of the book, a HDocBook provides the wrapper for containing and referencing supporting assets like images, downloadable files, icons and other static resources.  Like a physical book, this Book Package also includes the definition of a book's primary navigation index and table of contents, as well as other metadata to describe the books position in the Hornbill Docs library taxonomy. Other metadata that helps the Hornbill Docs search function includes information about the book such as subject, summary, keywords, tags and other such metadata that helps keeps books organization, categorized and easily searchable.  You can think of a Book analogous to a physical book. 

An **Article** is what we call an individual page within a *Book*, an Article can be a single page of information or can be many screens full of information. A HDocBook will have an automated H2/H3 generated table of contents, which provides navigation links to locations within the current page.  The key attribute that defines a document as an Article is, it is represented physically, by a single file. Articles are generally written using Markdown [HDocBook Markdown](/hdoc-guide/hdocbook/markdown), but where required, in special cases, they can be written using raw HTML. 

::: caution
When writing article content in HTML, you should ensure the HTML code you generate is compatible with the semantics, as well as the CSS we are using for layout/content positioning.
:::

In source code form, a book is simply a folder with certain mandatory files and folders, organized into a well defined structure.  A file called `hdocbook.json` must be included in the root folder, this file which essentially includes all of the metadata required to create the book, as well as metadata that controls publishing, indexing and taxonomy attribution. 

Developing content for the Hornbill Docs system is supported with development tools created by the the Hornbill Docs team. These tools are available to install as part of your local [Node.js](https://nodejs.org/en/) and [Node Package Manager (npm)](https://www.npmjs.com/) deployments. 

## The Anatomy of a Book
All books have a number of immutable characteristics, including a Globally Unique Identifier (called a slug), a Title, a Summary Description, a Table of Contents, as well as metadata that defines/controls publishing and presentation options, as well as information that helps organize Books into a structured taxonomy. 

### Book Unique Identifier (slug)
Each book is allocated a unique identifier, this is in the form of a lower-case-multi-word-hyphen-separated text string. When consuming the content pages of the book, this slug is always included in the URL when accessing the book content, so forms part of the final SEO optimization in relation to the search engine, crawling and final content location URL.

### Book Content
Document content is written in [Markdown](/hdoc-guide/hdocbook/markdown). Markdown is a plain text-based
content writing system that uses very simple markup to control aspects of page layout and presentation, while at the same time providing a complete separation of concerns between content and presentation. 

Markdown is a simple plain text scheme for marking up a document, that document can then be rendered using web pages, PDFs or other formats on many different device and screen types. Using Markdown ensures that content writers can focus on content and not have to worry about presentation and design issues such as fonts, colors, page alignment and so on. 

If required, there are more advanced options to use HTML and inline CSS instead of Markdown to create custom layouts and presentations, but this is encouraged only for very special situations where Markdown is simply not an option.  The markdown syntax is based on the [CommonMark](https://commonmark.org/) standard, but the HDocBook specification also includes additional custom elements that are specialized for this type of documentation content rendering.

### Table of Contents
A Book includes the definition of a table of content, which is presented on the left-hand navigation panel of links to pages, the table of contents can be a simple vertical list of links, or, can be a hierarchical tree of up to three levels deep leading to links. An entry in the table of contents tree can either be an expandible/collapsible "group of items" - OR - an item, which is link to an article and/or page anchor.

### Anchor Shortcut Table
For larger articles, where the content spans multiple screen pages, it is possible to enable an Article Anchor Link Shortcut Table.  This table appears at the top-right of the content page, and is automatically generated to include anchor links to all H2 and H3 content headings that have been written into the document. 

### Access Controls
A Book includes metadata and options that allow you to control who should be able to see the document. These access controls make it possible to give different people different levels of visibility/access to documentation, all through the same documentation website. 

### Internationalization 
Books may contain pages for multiple languages if required, this is achieved by writing the main page in the default language (English), and then, you can write one or more language variants of each page. 
