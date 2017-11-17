# Basic CSS \(Cascading Style Sheets\)

[Read more at MDN Web Docs](https://www.gitbook.com/book/isaklafleur/module-1/edit#)

---

Cascading Style Sheets \(CSS\) is a style sheet language used for describing the presentation of a document written in a markup language. Although most often used to set the visual style of web pages and user interfaces written in HTML and XHTML, the language can be applied to any XML document, including plain XML, SVG and XUL, and is applicable to rendering in speech, or on other media. Along with HTML and JavaScript, CSS is a cornerstone technology used by most websites to create visually engaging webpages, user interfaces for web applications, and user interfaces for many mobile applications.

CSS is designed primarily to enable the separation of presentation and content, including aspects such as the layout, colors, and fonts. This separation can improve content accessibility, provide more flexibility and control in the specification of presentation characteristics, enable multiple HTML pages to share formatting by specifying the relevant CSS in a separate .css file, and reduce complexity and repetition in the structural content.

Separation of formatting and content makes it possible to present the same markup page in different styles for different rendering methods, such as on-screen, in print, by voice \(via speech-based browser or screen reader\), and on Braille-based tactile devices. It can also display the web page differently depending on the screen size or viewing device. Readers can also specify a different style sheet, such as a CSS file stored on their own computer, to override the one the author specified.

Changes to the graphic design of a document \(or hundreds of documents\) can be applied quickly and easily, by editing a few lines in the CSS file they use, rather than by changing markup in the documents.

The CSS specification describes a priority scheme to determine which style rules apply if more than one rule matches against a particular element. In this so-called cascade, priorities \(or weights\) are calculated and assigned to rules, so that the results are predictable.

The CSS specifications are maintained by the World Wide Web Consortium \(W3C\). Internet media type \(MIME type\) text/css is registered for use with CSS by RFC 2318 \(March 1998\). The W3C operates a free CSS validation service for CSS documents.

---

## Anatomy of a CSS ruleset

![](https://mdn.mozillademos.org/files/9461/css-declaration-small.png)

### Example

```css
h1 {
  colour: blue;
  background-color: yellow;
  border: 1px solid black;
}

p {
  color: red;
}

p, li {
  text-decoration: underline;
}
```

## How does CSS actually work? {#How_does_CSS_actually_work}

When a browser displays a document, it must combine the document's content with its style information. It processes the document in two stages:

1. The browser converts [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) and [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) into the [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) \(_Document Object Model_\). The DOM represents the document in the computer's memory. It combines the document's content with its style.
2. The browser displays the contents of the DOM.

![](/assets/Screen Shot 2017-11-17 at 16.36.58.png)

#### You can apply CSS on HTML tags, classes or a id of a HTML tag



