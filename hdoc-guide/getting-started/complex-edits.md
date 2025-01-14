---
layout: article
---
# Workflow for making extensive edits
This article explains how to get set up for making extensive edits to Hornbill documentation. 

The main benefit of this workflow over the simple-edits workflow is being able to preview documents in a browser window as you work on them.

This workflow is more complex to set up than the [Simple Edits workflow](/hdoc-guide/getting-started/simple-edits) as you need to install a number of dependencies and tools.

Once you are set up, the editing process is relatively straightforward.

## Overview
This workflow uses Hornbill's hdoc-tools, which is a command-line extension of Node.js that allows you to preview your edits in a browser window.

With this workflow, you make local copies of files from Hornbill's documentation repositories on GitHub, then you edit and preview the files locally using a text editor and browser, respectively. When finished, you submit your changes back to GitHub for publishing.

The steps are the following:

1. Check out (fork) content from Hornbill's main branch of the documentation. The forked content is hosted online into your GitHub account.
2. Copy (clone) documents from your account to your local machine, then make edits using a text editor.
3. Save (commit) documents locally using Git.
4. Send documents back (push) to your online GitHub account.
5. Publish (commit) your changes to Hornbill's main branch to be validated by the Hornbill Docs team and then included in the public-facing Hornbill documentation. 

We recommend using Microsoft's Visual Studio Code as a text editor. VS Code is free, well-supported, and has a large ecosystem of extensions that can be useful when editing documentation.

## Before you begin
The following steps must be complete before you can edit and commit Hornbill documentation:
1. Register for a free [GitHub account](https://github.com/signup) if you do not already have one.
2. Download and install [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git). 
3. Follow these instructions to [Link your installation of Git to your GitHub account](https://docs.github.com/en/get-started/quickstart/set-up-git).
4. Download and install [Visual Studio Code](https://code.visualstudio.com/). 
5. Download and install [Node.js Active LTS](https://nodejs.org/en/).

  ::: important
  Install the latest Active Long Term Support (Active LTS) version of Node.js. Non-Active LTS versions (including the Maintenance LTS stream) are not supported by Hornbill.
  ::: 
  ::: note
  During the Node.js installation, you may be asked to automatically install the tools necessary to compile native modules. Because these tools are required by Hornbill's HDocBook tooling, you must do one of the following:
   - Allow the Node.js installation to download and install these automatically.
   - Install the tooling manually once the Node.js installation is complete. To do this, see the [node-gyp](https://www.npmjs.com/package/node-gyp)  package documentation for further information.
   :::
6.  Install HDocBook Tools. To install HDocBook Tools, open a terminal window and enter the following command: 
    ```bash
    npm install hdoc-tools -g
    ```
   Depending on your local operating system permissions, you may need to run the command as the root user. This installs the package globally to your Node.js installation, making the `hdoc` CLI tool available for you to use. 

## How to make and publish edits

1. Select an article to edit. To do this, browse to the [Hornbill Docs GitHub account](https://github.com/Hornbill-Docs) and locate the HDocBook you wish to contribute to. 

2. Fork your copy on GitHub. To contribute to a HDocBook, you are first required to fork the repository that contains it, which will make a copy of that repository in your personal GitHub account. In your Github account, having selected the Hornbill document, select the fork menu item and create a new fork.

3. Clone your copy to your local computer. To do this:
    1. On your computer, create a folder called "hornbill-docs" in the desired location.
    2. Open a terminal window in that folder and type the command:

   `git clone [your cloned HDocBook url]`

4. Preview the document. To do this:
    1. In Visual Studio, select File > Open Folder and open the first/top-level hdoc-guide folder. This folder contains the hdocbook-project.json file. 
    2. To open a terminal window, select Terminal > New Terminal. 
    3. In the terminal prompt, type `hdoc serve` then press return to start the preview server. 
    4. Open a web browser, then navigate to http://127.0.0.1:3000/. The web browser should display a preview of the document.

5. Edit documents in Visual Studio and save changes as you go. You can work on multiple documents simultaneously in Visual Studio by having them open in different tabs. 

    ::: note
    Updates in the text editor are not automatically displayed in the document preview. To preview saved changes as you work on a document, refresh the browser page.
    :::

    ::: tip
    Run this command to view basic statistics of the document, including file count and total word count:
    - `hdoc stats`

    Run this command to access a more detailed breakdown of the statistics:
    - `hdoc stats -v`
    :::

6. Verify the book's integrity. 
    Before committing your changes, stop your local server (CTRL+C) and run `hdoc validate`, which should catch any errors that would otherwise cause a fail during the build process. This command verifies the HDocBook integrity, making sure config files are correct, paths are set, links work, spelling and grammar comply with our writing standards, and so on. 

7. Commit your edits. To do this:
    1. Select "Source Control" on the left side of the VS Code screen, then select "Commit". 
    2. A commit message window opens. Add a commit message, then select the tick button to commit.

    ::: note
    A commit message is your description of the changes you have made. The message is read by the Hornbill Docs team to evaluate your changes. The heading of your message (a summary of your actions) should be no more than 50 characters, and the body (details) should be no more than 72 characters. See [best practices for commit messages](https://www.freecodecamp.org/news/how-to-write-better-git-commit-messages/). 
    :::

8. Push your changes to your fork. 
    To do this, select the "Sync Changes" button under the "Source Control" menu in VS Code.

9. Create a pull request from your fork to the Hornbill main branch. To do this: 
    1. Go online to your GitHub account. 
    2. Navigate to your fork of the HDocBook repository. 
    3. Select "Pull Requests", then select "New Pull Request". Your pushed changes should appear here. If you cannot see your changes, ensure that you are in the correct fork.
    4. When prompted, add a message to summarize the pull request. If you pushed multiple versions of the document during editing, this message summarizes all of them. Note your commit messages are also preserved and submitted with the pull request.
    5. Select the option to submit the request.

After a pull request, your change is submitted to the Hornbill Docs team. They will review the proposed changes and decide whether to approve them for inclusion in the Hornbill documentation.

::: tip
You can use a combination of this extensive-edits workflow and the [simple-edits workflow](/hdoc-guide/getting-started/simple-edits), depending on your need for the previewing feature.
:::

## Additional resources

### Using Git with Visual Studio Code (external)
<iframe width="560" height="315" src="https://www.youtube.com/embed/i_23KUAEtUM" title="Using Git with Visual Studio Code (Official Beginner Tutorial)" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### Optional Visual Studio Code extensions (external)

There are a number of [Visual Studio code Extensions ](https://code.visualstudio.com/learn/get-started/extensions) available to enhance your editing experience.

Examples include:

* [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) 
  * Gives you spell checking and highlighting
* [Word Count](https://marketplace.visualstudio.com/items?itemName=ms-vscode.wordcount) 
  * Provides a useful count of words in your current document
* [Preview](https://marketplace.visualstudio.com/items?itemName=searKing.preview-vscode) 
  * Gives you Markdown preview capability
* [SVG Previewer](https://marketplace.visualstudio.com/items?itemName=vitaliymaz.vscode-svg-previewer)
  * Shows .svg images
