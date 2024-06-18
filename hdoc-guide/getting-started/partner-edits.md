# Partner Content Creator/Editor Workflow

Sometimes Hornbill will partner with and outsource to professional writers who are working on substantial portions of, or even creating whole documents that will be published on the Hornbill Docs site.  Like our internal documentation team, and in these cases, we can provide direct access to individual documents' GitHub repositories allowing the author to work directly on the master repo, removing the need for the Hornbill Docs team and the author to work with Pull Requests and review/merge cycles which is typical in the Complex Edits workflow.  In effect, this is the exact same workflow as we use internally for authoring documents, which we extend to trusted content partners and individuals who are otherwise outside of Hornbill.

## How it Works
Once we have agreed to work with you on a specific document where there is substantial writing required, we will:

* Advise you we are using this workflow
* Ask you for your GitHub account name in order that we may add you to the specific master repository that contains the document source. Although there may be exceptions to this, generally speaking you will only have access to the master repository during the development phase, which means your edits will not be published directly to the Hornbill Docs website.  Instead we will have a specific preview site which you will be able to see published versions of the document(s) you have made changes to. 
* Share a link to the master repository in order that you may clone it directly to your local computer, without having to clone to your personal account (and therefore negating the need to use the Complex Edits workflow with Pull requests), and be able to commit back to the master repository as required. 

## Before you begin
The following steps must be complete before you can edit and commit Hornbill documentation:
1. Let us know the account name for your GitHub account, or register for a free [GitHub account](https://github.com/signup) if you do not already have one.
2. Download and install [GitHub Desktop](https://desktop.github.com/) if you do not already have this installed. 
3. Log into your GitHub account within GitHub Desktop.
4. Download and install [Visual Studio Code](https://code.visualstudio.com/), or use any other text editor you are comfortable/familiar with.
5. Download and install [Node.js LTS](https://nodejs.org/en/) (Minimum version: Node.js LTS v18 LTS).

  ::: important
  Install the latest Long Term Support (LTS) version of Node.js. Non-LTS versions are not validated by Hornbill.
  ::: 
  ::: note
  During the Node.js installation, you may be asked to automatically install the tools necessary to compile native modules. Because these tools are required by the Hornbill's HDocBook tooling, you must either:
   1. Allow the Node.js installation to download and install these automatically.
   2. Install the tooling manually once the Node.js installation is complete. To do this, see the [node-gyp](https://www.npmjs.com/package/node-gyp)  package documentation for further information.
   :::
6.  Install HDocBook Tools. To install HDocBook Tools, open a terminal window and enter the following command: 
    ```bash
    npm install hdoc-tools -g
    ```
   Depending on your local operating system permissions, you may need to run the command as the root user. This installs the package globally to your Node.js installation, making the `hdoc` CLI tool available for you to use. If installing node modules globally does not work for you, use local administrator rights.

## Cloning Document Repository
Open GitHub Desktop and add a repository using the '''Clone Repository...''' option. Once cloned, open the project in VS Code and edit as required.  You can use all of the usual Git features to manage and commit your changes, and use GitHub Desktop to push change sets back into the master repository as required. 

:::note
Please remember to always validate your documentation before committing changes.  In VS Code, open a terminal and simply type `hdoc validate' and your document will be checked for spelling, link integrity, missing pages, missing images and so on. 
:::

Failing to validate your document will prevent any publishing because our publishing tools will run these validations first.  

## Start Editing
Once you have cloned a repository, in GitHub Desktop there should be an __Open In Visual Studio Code__ button, simply press that button, Visual Studio Code will open at the correct location. 

Edit and commit changes using VS Code GitHub integration.  

When you wish to commit your changes to the master repository, go to GitHub Desktop and press the "Push Origin" button and your changes will be pushed to the repository master 