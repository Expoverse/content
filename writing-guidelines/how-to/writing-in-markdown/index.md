---
title: Writing in Markdown
post_date: 2023-03-10 00:00:00
---

This page outlines how we utilize Markdown to generate documentation on AppCode. We have opted for standard Markdown as the primary format for the documentation, as it provides a consistent and straightforward syntax for creating content. We have customized our Markdown tooling to support the specific needs of our documentation process on AppCode, allowing us to efficiently produce high-quality documentation.

Standard Markdown is a widely-used and consistent syntax. AppCode's Markdown syntax is based on standard Markdown. This means that any specifications not explicitly outlined on this page can be referenced using the standard Markdown specification, CommonMark (<a href="https://spec.commonmark.org/">https://spec.commonmark.org/</a>). Additionally, the Markdown Guide (<a href="https://www.markdownguide.org/">https://www.markdownguide.org/</a>) is a great resource for learning more about Markdown syntax and best practices for using it in your writing.

<!-- wp:heading {"level":1} -->
## Introduction to CommonMark</h2>

CommonMark is a specification for the Markdown syntax. It was created to standardize the Markdown syntax, making it easier to write and interpret Markdown documents. The goal of CommonMark is to provide a consistent and predictable syntax that can be used across different platforms and applications.

Markdown is a lightweight markup language that allows writers to format plain text documents. It was first developed by John Gruber in 2004 and has since become a popular format for writing documentation, notes, and web content. Markdown provides a simple syntax for formatting text, making it easy to learn and use.

However, the syntax of Markdown is not always consistent across different applications and platforms. This can lead to confusion and errors when writing Markdown documents. CommonMark was developed to solve this problem by providing a standard specification for the Markdown syntax.

## CommonMark Specification

The CommonMark specification defines a set of rules for writing and interpreting Markdown documents. These rules provide a consistent and predictable syntax that can be used across different applications and platforms. The CommonMark specification includes several features that are not present in the original Markdown syntax.

## Basic Syntax

The basic syntax of CommonMark is similar to the original Markdown syntax. It includes syntax for headings, paragraphs, lists, and emphasis. Here are some examples of basic syntax in CommonMark:

### Headings

```Markdown
# Heading 1
## Heading 2
### Heading 3
```

### Paragraphs

```Markdown
This is a paragraph.

This is another paragraph.
```

### Lists

```Markdown
- Item 1
- Item 2
  - Item 1
- Item 3
```

### Emphasis

```Markdown
This is *italic* text.
This is **bold** text.
```

## Extended Syntax

CommonMark also includes several extensions to the original Markdown syntax. These extensions provide additional features that are not present in the original syntax. Here are some examples of extended syntax in CommonMark:

### Code Blocks

```Markdown
    This is a code block.
```

### Links

Links in CommonMark are created using square brackets to indicate the text of the link and parentheses to indicate the URL. Here's an example:

```Markdown
[Link Text](https://example.com/)
```

### Images

Images in CommonMark are created using an exclamation mark followed by square brackets to indicate the alt text and parentheses to indicate the URL. Here's an example:

```Markdown
![Alt Text](https://example.com/image.jpg)
```

### Tables

Tables in CommonMark are created using pipe characters to separate columns and hyphens to separate the header row from the content. Here's an example:

```Markdown
| Column 1 | Column 2 |
| -------- | -------- |
| Row 1, Column 1 | Row 1, Column 2 |
| Row 2, Column 1 | Row 2, Column 2 |
```

### Raw HTML

To use raw HTML in CommonMark, simply include the HTML code within the Markdown document. CommonMark will treat the HTML code as-is and render it in the final output. Here's an example of how to include a table using raw HTML:

```Markdown
<table>
  <tr>
    <th>Column 1</th>
    <th>Column 2</th>
  </tr>
  <tr>
    <td>Row 1, Column 1</td>
    <td>Row 1, Column 2</td>
  </tr>
  <tr>
    <td>Row 2, Column 1</td>
    <td>Row 2, Column 2</td>
  </tr>
</table>
```

### Block quotes

Quotes, or blockquotes, are another useful feature of CommonMark that allow for the inclusion of quoted text within a Markdown document. Quotes are created by prefacing the quoted text with a greater than sign (>), followed by a space.

Here's an example of how to create a quote:

```Markdown
> This is a quote.
> It can span multiple lines.
```

When rendered, the output will look something like this:

<blockquote><p>This is a quote.
It can span multiple lines.</p></blockquote>

Quotes can be nested within one another by including additional greater than signs before the quoted text. Here's an example of a nested quote:

```Markdown
> This is a quote.
>
> > This is a nested quote.
> > It can span multiple lines too.
```

When rendered, the output will look something like this:

<blockquote><p>This is a quote.</p><blockquote><p>This is a nested quote.
It can span multiple lines too.</p></blockquote></blockquote>

Quotes can be especially useful when including external content within a Markdown document, such as a quote from a book or article. They can also be used to highlight important or noteworthy text within the document, helping to draw the reader's attention to key points.

### Fenced code blocks

Fenced code blocks are used to include larger blocks of code within the document, and are created by enclosing the code within a pair of triple backticks (```). Optionally, you can also specify the language of the code by including the name of the language immediately after the opening triple backticks.

Here's an example of a fenced code block:

```Markdown
```python
def hello_world():
    print("Hello, world!")
```
```

When rendered, the output will look something like this:

```Markdown
def hello_world():
    print("Hello, world!")
```

### Inline code

Inline code is used to include smaller snippets of code within the text of a Markdown document. Inline code is created by enclosing the code within a pair of backticks (`).

Here's an example of inline code:

```Markdown
You can use the `print()` function to output text in Python.
```

When rendered, the output will look something like this:

You can use the `print()` function to output text in Python.

### Link reference definitions

Link reference definitions, also known as reference links, are another feature of CommonMark that allow for the inclusion of links within a Markdown document. Reference links are created by defining a link reference at the end of the document, and then referencing that link within the text of the document using square brackets ([]) and a label that corresponds to the link reference.

Here's an example of a link reference definition:

```Markdown
[Google]: https://www.google.com
```

This defines the link reference Google to point to https://www.google.com. You can then reference this link within the text of the document using square brackets and the label Google:

```Markdown
Take a look at [Google] to learn more.
```

When rendered, the output will look something like this:

Take a look at [Google] to learn more.

Reference links can also include optional titles, which are displayed as tooltips when the link is hovered over. To add a title to a reference link, simply include the title in quotes immediately after the URL:

```Markdown
[Google]: https://www.google.com "Google's Homepage"
```

When rendered, the output will look something like this:

Take a look at [Google] to learn more.

## Compiling Markdown to HTML

Markdown can be easily converted to HTML using a variety of tools and libraries, ranging from command-line tools to programming libraries. Popular options include Pandoc, Marked, and libraries available in Python, Ruby, PHP, and JavaScript.

The process of converting Markdown to HTML typically involves reading in the Markdown content, parsing it into a syntax tree, and generating HTML code. This process can be customized and optimized to fit the specific needs of a project, making Markdown a versatile tool for creating web content, including blog posts, technical documentation, and even full-fledged web applications.
