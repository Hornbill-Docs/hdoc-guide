# Getting started

Hornbill's Docs team publish its documentation on GitHub. Each HDocBook has its own public repository, and you can contribute to the documentation as you wish. This guide explains how. 

## GitHub

GitHub is an online source code and community projects website for developers, and is primarily used to host open-source projects. Hornbill's GitHub account is what we use to host our documentation source code. Almost all documents available on the [Hornbill Docs](/) website are made available as a public repository on our GitHub account. You can browse the Hornbill Docs GitHub account [here](https://github.com/Hornbill-Docs).

In order to contribute to Hornbill Docs content, you will need a basic working knowledge of GitHub and a free account.

## How contributing works

The basic workflow for contributing to documentation at Hornbill Docs is as follows. 

1. Having logged in to your own GitHub account, browse through or search the [Hornbill Docs](https://github.com/Hornbill-Docs/?target=_blank) organization, and locate the book (repository) you want to work on. Once you have located the repository, you create a *fork*, which makes a copy of that repository in your personal GitHub account. Although this fork is a copy of the main document, GitHub maintains a link back to the main. The link enables you to *push* your changes for review and intake to the main.  

2. Go to your own GitHub account repository list to see your forked copy of the book. This is where you can make your edits.

3. Make your edits. For [Simple Edits](/hdoc-guide/getting-started/simple-edits), do these within GitHub directly. For more [Complex Edits](/hdoc-guide/getting-started/complex-edits), use a good source code editor, such as the utterly brilliant and free [Visual Studio Code](https://code.visualstudio.com/) editor from Microsoft (along with a small number of very useful plugins) for a great editing experience.

4. Once you have completed your edits, create a pull request to ask the maintainers of the main document source (in this case the Hornbill Docs team). This pull request gives the Docs team the opportunity to review and accept your edits. Once reviewed, the Docs team will pull your changes into the main repo for inclusion in the next documentation build. 

5. To save space in your personal GitHub account, when you have finished your editing session, delete your fork of the document. Forking is fast and simple to do, so it's easy to take a copy of the latest source when you want to start a new editing session. 

::: tip
Once you have forked the main repo, your changes are not applied to the main, so you are safe to do whatever you want. If you do make a pull request, the changes you request will be reviewed by the Hornbill Docs team before being accepted into the main documentation source.
:::

There are two workflows for content editing: simple and complex.  

### Workflow for simple edits
For the [Simple Edits Workflow](/hdoc-guide/getting-started/simple-edits) you can do everything through the GitHub UI. Simple edits are good for when you want to make quick text changes. However, it's important to understand that while the Hornbill Docs system uses Markdown, there are many flavors of Markdown, and the GitHub UI will not render ours exactly as the Hornbill Docs website will. So for more complex contributions, you should follow the [Complex Edits Workflow](/hdoc-guide/getting-started/complex-edits). 

### Workflow for complex edits
For the [Complex Edits Workflow](/hdoc-guide/getting-started/complex-edits) you will generally install some specific tools, including Git command-line tools or TortoiseGIT Windows shell extension, a text/code editor of your choice, Node.js, and some other supporting tools. Editing involves forking in GitHub, cloning your forked copy to your local hard drive, and then using your favorite text editor to make your edits. The advantage of the [Complex Edits Workflow](/hdoc-guide/getting-started/complex-edits) is that you can install and use a tool that gives you a live preview of the documentation you are editing --- a preview of how the documentation will be presented on the live [Hornbill Docs website](/).

### Workflow for edits by partners
For the [Partner Edits Workflow](/hdoc-guide/getting-started/partner-edits) you will install some tools, including Git command-line tools or TortoiseGIT Windows shell extension, a text/code editor of your choice, Node.js, and some other supporting tools. Editing involves cloning the main repository to your local hard drive, and then using your favorite text editor to make your edits. The advantage of the [Partner Edits Workflow](/hdoc-guide/getting-started/partner-edits) is that firstly, you are working directly in the main repository for the document, so you do not need to worry about staging and pull requests, you are effectively working as a main document editor.  In addition, like the [Complex Edits Workflow](/hdoc-guide/getting-started/complex-edits), you can install and use an authoring tool that will give you a live preview of the documentation you are editing --- a preview of how the documentation will be presented on the live [Hornbill Docs website](/).
