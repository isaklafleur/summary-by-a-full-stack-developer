# [Basic CSS \(Cascading Style Sheets\)](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics)

---

Cascading Style Sheets \(CSS\) is a style sheet language used for describing the presentation of a document written in a markup language. Although most often used to set the visual style of web pages and user interfaces written in HTML and XHTML, the language can be applied to any XML document, including plain XML, SVG and XUL, and is applicable to rendering in speech, or on other media. Along with HTML and JavaScript, CSS is a cornerstone technology used by most websites to create visually engaging webpages, user interfaces for web applications, and user interfaces for many mobile applications.

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

## [Basic Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)

#### You can apply CSS on HTML Tags \([type selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors)\), Classes \([class selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors)\) IDs \([id selector](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors)\), ALL elements \(\*, [universal selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors)\) and at last, by a value of the attribute \([attribute selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)\)



