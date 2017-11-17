# Basic HTML

[More at MDN Web Docs](https://www.gitbook.com/book/isaklafleur/module-1/edit#)

---

Hypertext Markup Language \(HTML\) is the standard markup language for creating web pages and web applications. With Cascading Style Sheets \(CSS\) and JavaScript it forms a triad of cornerstone technologies for the World Wide Web. Web browsers receive HTML documents from a web server or from local storage and render them into multimedia web pages. HTML describes the structure of a web page semantically and originally included cues for the appearance of the document.

HTML elements are the building blocks of HTML pages. With HTML constructs, images and other objects, such as interactive forms, may be embedded into the rendered page. It provides a means to create structured documents by denoting structural semantics for text such as headings, paragraphs, lists, links, quotes and other items. HTML elements are delineated by tags, written using angle brackets. Tags such as `<img />` and `<input />` introduce content into the page directly. Others such as `<p>...</p>` surround and provide information about document text and may include other tags as sub-elements. Browsers do not display the HTML tags, but use them to interpret the content of the page.

HTML can embed programs written in a scripting language such as JavaScript which affect the behavior and content of web pages. Inclusion of CSS defines the look and layout of content. The World Wide Web Consortium \(W3C\), maintainer of both the HTML and the CSS standards, has encouraged the use of CSS over explicit presentational HTML since 1997.

---

## HTML DOM Tree

![](https://www.w3schools.com/js/pic_htmltree.gif)

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <link rel="stylesheet" type="text/css" href="./stylesheets/style.css">
  <link href="https://fonts.googleapis.com/css?family=Lato" rel="stylesheet">
  <script src="https://use.fontawesome.com/1fb0eb3889.js"></script>
  <title>Where work happens | Slack</title>
</head>

<body>
  <h1>Welcome to our page</h1>
</body>

</html>
```

## Anatomy of an HTML element

![](https://mdn.mozillademos.org/files/9347/grumpy-cat-small.png)

#### Elements can also have attributes, which look like this:

![](https://mdn.mozillademos.org/files/9345/grumpy-cat-attribute-small.png)

---

## “Block” Vs “Inline” Elements {#“block”-vs-“inline”}

### HTML block elements

In general, HTML elements can be divided into two categories : block level and inline elements.

1. **HTML block level elements** can appear in the body of an HTML page.

2. It can contain another block level as well as inline elements.

3. By default, block-level elements begin on new lines.

4. block level elements create larger structures \(than inline elements\).

#### List of block level elements

* p
* h1, h2, h3, h4, h5, h6
* ol, ul
* pre
* address
* blockquote
* dl
* div
* fieldset
* form
* hr
* noscript
* table

### HTML inline elements

1.**HTML inline level elements **can appear in the body of an HTML page.

1. It can contain data and other inline elements.

2. By default, inline elements do not begin on new lines.

3. Inline elements create shorter structures \(than block level elements\).

#### List of inline elements

* b, big, i, small, tt
* abbr, acronym, cite, code, dfn, em, kbd, strong, samp, var
* a, bdo, br, img, map, object, q, script, span, sub, sup
* button, input, label, select, textarea

---

## Common HTML Tags

### DOCTYPE: Defining your version of HTML

**Every web page must start with a DOCTYPE declaration.**It has to be the very first item on the very first line of your HTML or XHTML code. This tells browsers what version of HTML the web page was coded in, which helps them to know how to process the code. Prior to HTML5, DOCTYPE declarations were long and complex.

For example, here's the DOCTYPE declaration for XHTML 1.1:

`<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">`

In HTML5, the DOCTYPE declaration is much simpler:

`<!DOCTYPE html>`

### Document Structure

| Opening Tag | Closing Tag | Description |
| :--- | :--- | :--- |
| &lt;html&gt; | &lt;/html&gt; | Opens and closes an HTML document |
| &lt;head&gt; | &lt;/head&gt; | The first of two main sections of an HTML document. The &lt;head&gt; section is used to provide information about the document for use primarily by search engines and browsers. |
| &lt;title&gt; | &lt;/title&gt; | The title of document. This element is nested inside the &lt;head&gt; section.**In HTML5, this is the only required tag other than the DOCTYPE declaration.** |
| &lt;body&gt; | &lt;/body&gt; | The second of two main sections of an HTML document. The &lt;body&gt; section contains all the content of the web page. |

### Content \(Container\) Tags

| Opening Tag | Closing Tag | Description |
| :--- | :--- | :--- |
| &lt;h1&gt; to &lt;h6&gt; | &lt;/h1&gt;to&lt;/h6&gt; | Headings. H1 is the main heading, H2 is secondary, etc. |
| &lt;p&gt; | &lt;/p&gt; | Paragraph |
| &lt;div&gt; | &lt;/div&gt; | A container for a\_block\_of content |
| &lt;span&gt; | &lt;/span&gt; | A container for\_in-line\_content, such as content inside a paragraph. |
| &lt;em&gt; | &lt;/em&gt; | Gives the contained text emphasis \(usually as_italics_\). |
| &lt;strong&gt; | &lt;/strong&gt; | Makes the contained text**bold**. |
| &lt;a href = "document location"&gt; | &lt;/a&gt; | Link |
| &lt;ol&gt; | &lt;/ol&gt; | Ordered \(numbered\) list |
| &lt;ul&gt; | &lt;/ul&gt; | Unordered \(bulleted\) list |
| &lt;li&gt; | &lt;/li&gt; | List item, must be nested inside a list element such as a &lt;ol&gt; or &lt;ul&gt; |
| &lt;!-- | --&gt; | Comment. Anything between these tags is not displayed on the screen. This is useful for making notes to yourself or to others who may view the source code of the web page. |

### HTML5 \_Semantic \_Tags

HTML5 introduced several new tags calledsemantictags. These tags were designed to communicate the function of blocks of content that were common on many web pages. Prior to HTML5, developers just used &lt;div&gt; tags for all blocks.

| Opening Tag | Closing Tag | Description |
| :--- | :--- | :--- |
| &lt;header&gt; | &lt;/header&gt; | Contains introductory content for a page \(e.g., a banner\), or a section of a page. |
| &lt;nav&gt; | &lt;/nav&gt; | Contains navigation content, such as a website navigation menu. |
| &lt;main&gt; | &lt;/main&gt; | Contains the main content of the web page. |
| &lt;aside&gt; | &lt;/aside&gt; | Contains content that istangentiallyrelated to the main content of the page \(often this is presented in a sidebar\). |
| &lt;footer&gt; | &lt;/footer&gt; | Contains the footer of a page, or of a section of a page. Typically the footer contains information\_about\_the content, such as the author and a copyright statement. |

### Empty \(Non-Container\) Tags

| Tag | Description |
| :--- | :--- |
| &lt;br /&gt; | Line break. |
| &lt;img src ="image location" alt="alternate text" /&gt; | Inserts an image into a web page. |

### Tables

| Opening Tag | Closing Tag | Sample Attributes | Description |
| :--- | :--- | :--- | :--- |
| &lt;table&gt; | &lt;/table&gt; |  | Adds a table |
| &lt;tr&gt; | &lt;/tr&gt; |  | Table row \(start & end\). |
| &lt;th&gt; | &lt;/th&gt; | scope="row" scope="col" | When creating a table to display data, use this tag to differentiate the first row or column of cells as heading cells for all the other cells in the same column or row. Browsers typically display this element bold and centered within the table cell. Thescopeattribute defines whether this is a row header or column header. |
| &lt;td&gt; | &lt;/td&gt; |  | Table data cell. |
|  |  | colspan="number" | Use with &lt;th&gt; or &lt;td&gt; elements. Spans cells across multiple columns. |
|  |  | rowspan="number" | Use with &lt;th&gt; or &lt;td&gt; elements. Spans cells across multiple rows. |



