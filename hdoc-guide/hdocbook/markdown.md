---
title: HDocBook Markdown Overview
layout: article-toc
---
# HDocBook Markdown Overview

Every system that uses Markdown is generally built on a basic Markdown syntax, frequently based on the strongly typed and documented [CommonMark](https://commonmark.org/) specification. However, individual Markdown systems generally need to expand the syntax to include extra functions or rendering capabilities that are specific to the needs of the system.

Accordingly, the HDocBook Markdown syntax is also based on [CommonMark](https://commonmark.org/) but extends that with additional capabilities that allow rich documentation content features and visualizations to be created. This article is the reference for both basic and extended syntax for the HDocBook Markdown grammar and feature set.


## Alerts (Note, Tip, Important, Caution, Warning)

Alerts is a HDocBook Markdown extension that will create block quotes that render on Hornbill H-DOC with colors and icons that indicate call-out information within the document.

Avoid notes, tips, and "important" boxes. Readers tend to skip over them. It's better to put that information directly into the article text.

If you need to use alerts, limit them to one or two per article. Multiple notes should never be next to each other in an article.

The following alert types are supported:

```md
::: note
Information the user should notice even when skimming.
:::

::: tip
Optional information to help a user be more successful.
:::

::: important 
Essential information required for user success.
:::

::: caution
Negative potential consequences of an action, be careful.
:::

::: warning
Dangerous consequences of an action.
:::
```

These alerts look like this on Hornbill Docs:

::: note
Information the user should notice even when skimming.
:::

::: tip
Optional information to help a user be more successful.
:::

::: important 
Essential information required for user success.
:::

::: caution
Negative potential consequences of an action, be careful.
:::

::: warning
Dangerous consequences of an action.
:::



## Angle Brackets

If you need to use angle brackets &lt;&gt; in your text, you need to encode these using standard HTML entity encoding. 

The following:
```md
&lt;between&gt;
```
will render as: &lt;between&gt;

## Blockquotes

Blockquotes are created using the `>` character:

```md
> This is a blockquote. It is usually rendered indented and with a different background color.
```

The preceding example renders as follows:

> This is a blockquote. It is usually rendered indented and with a different background color.

## Bold and Italic text

To format text as **bold**, enclose it in two asterisks:

```md
This text is **bold**.
```

To format text as *italic*, enclose it in single asterisks:

```md
This text is *italic*.
```

To format text as both ***bold and italic***, enclose it in three asterisks:

```md
This text is both ***bold and italic***.
```

## Code Tags

Hornbill Docs supports in-article code highlighing, using the popular [highlight.js](https://highlightjs.org/) library.

To add blocks of code to your articles, you need to wrap your code with three backticks, and set an (optional) language to apply highlighted code, as so:

<pre class="code-badge-pre"><div class="code-badge"><div class="code-badge-language">md</div><div title="Copy to clipboard"><i class="bi bi-clipboard code-badge-copy-icon"></i></div></div><code class="language-md hljs markdown"><span class="hljs-code">```js
// Your JavaScript code could go here
console.log('Hello, world');
```</span></code></pre>

Which would render as:

```js
// Your JavaScript code could go here
console.log('Hello, world');
```

### Supported Languages

The following highlight.js supported languages are also supported in hdoc-tools:

* `apache`
* `bash`
* `cpp`
* `cs`
* `css`
* `markdown`
* `dart`
* `diff`
* `dns`
* `dockerfile`
* `dos`
* `foxpro`
* `fsharp`
* `go`
* `http`
* `ini`
* `java`
* `javascript`
* `json`
* `kotlin`
* `less`
* `makefile`
* `xml`
* `nginx`
* `perl`
* `pgsql`
* `php`
* `powershell`
* `python`
* `rust`
* `sql`
* `swift`
* `typescript`
* `vbnet`
* `ruby`
* `yaml`

## Headings

Hornbill Docs supports six levels of headings, specified by one through six hash `#` characters, followed by a space, and then the heading text:


```md
# Heading 1 (H1)
## Heading 2 (H2)
### Heading 3 (H3)
#### Heading 4 (H4)
##### Heading 5 (H5)
###### Heading 6 (H6)
```

The above Markdown will render like this. 

# Heading 1 (H1)
## Heading 2 (H2)
### Heading 3 (H3)
#### Heading 4 (H4)
##### Heading 5 (H5)
###### Heading 6 (H6)

::: note
- There must be at least one space between the `#` and heading text.
- Only a single H1 heading should exist in any Markdown file, and should be the first content item in the document.
- For templates that include the right-hand table of contents, H2 and H3 headings will automatically appear inside it.
- You can put links to individual headings in a Markdown file using anchor links, as so: `[create an anchor](#anchors-in-markdown)`.
:::

## HTML
Markdown supports inline HTML. As a general rule, HTML is not recommended for publishing to Hornbill Docs, but it may be useful in a limited number of situations. Basically, you should avoid using inline HTML to the greatest extent possible.

:::important
Hornbill Docs does not support runtime-compiled stylesheets, and therefore the use of `<style />` HTML tags in book markdown or static HTML documents is unsupported.
:::

## Images
The following image types are supported.  

- .jpg
- .png
- .svg

For illustrations, flow diagrams and info graphics, we recommend you have your graphic designer use SVG format, and follow the [Hornbill Graphics and Illustration Style Guide](/_books/hdoc-guide/writing-style-guide#graphics-and-illustrations) in order to ensure that images scale properly for screen, print and PDF, and in the case of screen rendering look high-quality in both light and dark screen rendering modes.

The basic Markdown syntax you should use to embed an image in your content is: 

``` md
![Alt Text](/path/to/image.jpg)
```

## Links
For information on using links, see [Using Links In Documentation](/hdoc-guide/hdocbook/using-links).

## Lists - Numbered and Bulleted

### Numbered List

To create a numbered list, you can use any numbers, but for consistency it's best to just use all 1's and the rendering process 
will take care of sequencing the numbers correctly for you. The numbers are rendered in ascending order sequentially. For increased  readability in markdown, you can increment your list numbers manually.

```md
1. The first item
1. The second item in the parent list
   1. and this is the first child item
   2. in a nested numbered list
1. The third item, and so on...
```

This renders as follows:

1. The first item
1. The second item in the parent list
   1. and this is the first child item
   2. in a nested numbered list
1. The third item, and so on...

### Bulleted List

You can create a bulleted list using either `-` or `*` followed by a space at the start of each item. Choose one, then stick to that throughout the entire article:

```md
* The first item
* The second item in the parent list
   * and this is the first child item
   * in a nested numbered list
* The third item, and so on...
```

This renders to a bulleted list follows:

* This is
* a parent bulleted list
  * and this is
  * a nested bulleted list
* All done!


## Superscript / Subscript

Subscript and superscript are "inline" styles used normally for technical documentation. As a best practice, use these styles only in a context that requires subscript/superscript for technical accuracy (e.g. for formulas) and NOT for creating smaller text items, such as notes under images and so on.

To get superscript or subscript we are using the in-line HTML feature of the markdown processor:

```html
Get <sub>subscript</sub> like this
```

Which will render:

Get <sub>subscript</sub> like this

```html
And get <sup>superscript</sup> like this.
```

Which will render:

And get <sup>superscript</sup> like this.

## Tables

Markdown provides a simple way to create a table using the `|` pipe and `-` hyphen symbols. An example of a simple table is shown below.

```md
|Column Header 1 |Col 2   | Col Three|
|---------------|--------|----------|
|any information|in your |table |
|and you don't need to |worry too much about |alignment|
```

And this is what the above renders to:

|Column Header1 |Col 2   | Col Three|
|---------------|--------|----------|
|any information|in your |table |
|and you don't need to |worry too much about |alignment|

To align the table content horizontally you can use colons in the header separating lines either size of the hyphens like this:

```md
| Left Aligned         |    Center Aligned    |   Right Aligned |
| :------------------- | :------------------: | ---------------:|
| Left Here            |      Center Here     |      Right Here |
| 1.00                 | 4.57                 | 88            |
| one                  | two                  | three             |
```

The above renders the following table:

| Left Aligned         |    Center Aligned    |   Right Aligned |
| :------------------- | :------------------: | ---------------:|
| Left Here            |      Center Here     |      Right Here |
| 1.00                 | 4.57                 | 88            |
| one                  | two                  | three             |

::: tip
If you want a more interactive way to create a table you can use any one of a number of online markdown table generators, for example:

- [TableConvert](https://tableconvert.com/markdown-generator)
- [Tables Generator](http://www.tablesgenerator.com/markdown_tables)
:::

### Data matrix tables

You can create a data matrix table like this:

```md
|              |column 1 |Column 2|
|--------------|---------|--------|
|**Row 1 Name**|Data 1a  |Data 2a |
|**Row 2 Name**|Cell 1b  |Data 2b |
```

The example renders as:

|              |column 1 |Column 2|
|--------------|---------|--------|
|**Row 1 Name**|Data 1a  |Data 2a |
|**Row 2 Name**|Cell 1b  |Data 2b |

This is really the same as any other table, except every entry in the first column is styled bold (`**bold**`) using normal bold syntax.
