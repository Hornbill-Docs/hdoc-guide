---
title: Content Creation Overview
layout: article-toc
---
# Content Creation Overview

Creating good quality documentation is challenging, even aside from the challenge of knowing the subject and writing about it in a way that readers will be able to consume. There is a lot involved in taking basic written content and publishing it in a format that is consistent, reliable, accessible and scalable.  

Traditional documentation systems are generally built around "what you see is what you get" editing tools and proprietary formats/publishing schemes. Hornbill has chosen to take a more contemporary approach to content development, using simple text-based Markdown. Markdown has many benefits over proprietary formats, the most significant benefit being a complete abstraction of content from the design/presentation needs. The use of Markdown helps you, as a content creator, focus on the content, and removes the distractions of styling, publishing and deploying content. 

As well as basic writing skills and the requisite subject matter expertise, writing documentation at scale also needs a consistent, well defined, easy-to-use workflow for content creation, preview and publication. The Hornbill Docs in-house document system provides all of this in an end-to-end, tool and system-supported workflow, which handles the three main process steps of Content Development, Build/Publishing and Consumption. 

![Documentation Architecture](/_books/hdoc-guide/images/hdocbook-architechture.svg)



## High-Level Content Workflow

To get the best quality and consistency of documentation on Hornbill Docs there is a well-defined workflow supported by guidelines, specifications and tools. These are designed to make the process as easy and repeatable as possible, by multiple authors, even if they do not work together. This consistency in approach and tooling is required because we wish to encourage the broadest possible audience to help us develop and expand the documentation that helps our user community get the very best out of Hornbill's software. 

The three key stages of the document publishing lifecycle are explained in this document. The architecture diagram shows you the workflow, which is broken down into these distinct steps. Contributors to the Hornbill Docs content only need to be concerned with the Content Development step, but the full workflow cycle is explained here for context, helping you to understand how the Content Development workflow fits into the creation-to-consumption process. 

## 1. Content Development

The primary capability of any documentation system is facilitating the creation of content. When developing Hornbill Docs content, your work unit is a **HDocBook**. Each Book is a separate, stand-alone project. The source content for a Book is simply made up of a folder structure containing any number of documents that can be authored in Markdown or as custom HTML. This structure is called HDocBook. The workload for content creation is designed around standard, easy-to-use development tools and plugins, and the ability to accurately preview your content during the content development process. Some documentation (for example, APIs and other content that is defined in metadata such as XML or JSON) can be automatically extracted from source code comments or markup.  

## 2. Build and Publish

Publishing a Book involves building the document source, rendering Markdown into HTML, generating metadata and an index, and packaging everything rendered/generated into a deployable HDocBook package. Once built, the document is published into the Document Library ready for consumption. The Published Document Library is a content deployment scheme that makes HDocBooks accessible to the content publishing application servers.  

## 3. Consumption

Consuming documentation is really describing the implementation of the web server and the Docs UI Web App that makes up the [website](/) that all published documentation is consumed from. The website provides the ability to search for content, browse the Book library and read Books. 
