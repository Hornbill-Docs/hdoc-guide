# Getting Started with Contributing

The Hornbill Docs team publishes most of its documentation on GitHub. Each HDocBook has its own public repository, and anyone is free to contribute to Hornbill Docs should they wish. The process is simple and makes use of readily available and free tools—simply follow this guide to learn how. 
## GitHub

GitHub is an online source code and community projects website for developers, and is primarily used to host open-source projects. Hornbill maintains a GitHub account which we use to host our documentation source code. Almost all documents available on the [Hornbill Docs](/) website are made available as a public repository on our GitHub account.  You can browse the Hornbill Docs GitHub account [here](https://github.com/Hornbill-Docs).

In order for you to contribute to Hornbill Docs content, you will need a basic working knowledge of GitHub and a free account.
## How Contributing Works

The basic workflow for contributing to documentation on Hornbill Docs is as follows. 

1. When logged into your own GitHub account, you can browse the [Hornbill Docs](https://github.com/Hornbill-Docs/?target=_blank) repository, and locate the specific document you wish to contribute to. Once you have located the repository to work on, you must create a *fork*, which will make a copy of that repository in your personal GitHub account. Although this will be a copy of the master document, GitHub maintains a link back to the master source you copied from, and this is what facilitates you being able to push back your changes for review and intake to the master.  

2. When you go to your own GitHub account repository list, you will see your forked copy of the document. This is where you can make your edits.

3. Now you can make your edits. [Simple Edits](/_books/hdoc-guide/getting-started/simple-edits) can be done from within GitHub directly. For more [Complex Edits](/_books/hdoc-guide/getting-started/complex-edits) we strongly recommend using a good source code editor, such as the utterly brilliant and free [Visual Studio Code](https://code.visualstudio.com/) editor from Microsoft (along with a small number of very useful plugins) for a great editing experience.

4. Once you have completed the edits you want to make, you can, if you want to, create a pull request to ask the maintainers of the master document source (in this case the Hornbill Docs team) to accept your edits. The team will review your changes and pull them into the master repo for inclusion in the next nightly documentation build. 

5. Once you have finished your editing session, you can save space on your personal GitHub account by deleting your fork of the document. Forking is fast and simple to do, so it's easy to take a copy of the latest source when you want to start a new editing session. 

::: tip
Once you have copied (forked) the master repo, your changes are not applied to the master, so you are safe to do whatever you want. If you do send a pull request, the changes you request will be reviewed by the Hornbill Docs team before being accepted into the master documentation source. The review process will be much faster if your changes are small.
:::

There are two workflows for content editing: simple and complex.  

### Workflow for simple edits
For the [Simple Edits Workflow](/_books/hdoc-guide/getting-started/simple-edits) you can do everything through the GitHub UI—no additional tools are required. Simple edits are good for when you want to make quick text changes. However, it's important to understand that while the Hornbill Docs system uses Markdown, there are many flavors of Markdown, and the GitHub UI will not render ours exactly as the Hornbill Docs website will. So for more complex edits/contributions you should follow the [Complex Edits Workflow](/_books/hdoc-guide/getting-started/complex-edits). 

### Workflow for complex edits
For the [Complex Edits Workflow](/_books/hdoc-guide/getting-started/complex-edits) you will generally install some specific tools, including Git command-line tools or TortoiseGIT Windows shell extension, a text/code editor of choice, Node.js and some other supporting tools. Editing will involve forking in GitHub, cloning your forked copy to your local hard drive, and then using your favorite text editor to make the changes/edits. The advantage of the [Complex Edits Workflow](/_books/hdoc-guide/getting-started/complex-edits) is that you can install and use a tool that will give you a live preview of the documentation you are editing, and this preview gives you a lifelike preview of how the documentation will be presented on the live [Hornbill Docs website](/).

### Workflow for edits by partners
For the [Partner Edits Workflow](/_books/hdoc-guide/getting-started/partner-edits) you will generally install some specific tools, including Git command-line tools or TortoiseGIT Windows shell extension, a text/code editor of choice, Node.js and some other supporting tools. Editing will involve cloning the master repository to your local hard drive, and then using your favorite text editor to make the changes/edits. The advantage of the [Partner Edits Workflow](/_books/hdoc-guide/getting-started/partner-edits) is that firstly, you are working directly in the master repository for the document, so you do not need to worry about staging and pull requests, you are effectively working as a master document editor.  In addition, like the [Complex Edits Workflow](/_books/hdoc-guide/getting-started/complex-edits), you can install and use an authoring tool that will give you a live preview of the documentation you are editing, giving you a lifelike preview of how the documentation will be presented on the live [Hornbill Docs website](/) locally on your computer.
