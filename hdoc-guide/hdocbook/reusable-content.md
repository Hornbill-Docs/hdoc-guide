# Reusable Content

Creating reusable content for books or pages is often desirable. Good candidates for reusable content include copyright notices, terms and conditions, and any other commonly used content that, for maintenance requirements, should not have duplicates. The HDocBook Markdown format supports an INCLUDE directive to facilitate this. As of now, only Markdown text content is supported by this directive. To use it, include the fully qualified URL of a Markdown file in the directive. The INCLUDE statement will then be replaced by the content within that file at build time or runtime in dev preview.

The INCLUDE directive takes the following form:

<code>
[ [INCLUDE https://raw.githubusercontent.com/Hornbill-Docs/hdoc-library/main/hdoc-library/agreements/code-of-conduct.md] ]
</code>

(without the space between the opening and closing square brackets). This will inject the content from the file `code-of-content.md` into your article.

It is also possible to include content from within the same document. This is useful, for example, when you have content you might want to include in your document pages, but also want to include as _inline content for in-app product help. 

The include directive takes the following form:

<code>
  [ [INCLUDE /esp-fundamentals/_inline/roadmap-incoming.md] ]
</code>

(without the space between the opening and closing square brackets). This will inject the content from the file `roadmap-incoming.md` into your article.
