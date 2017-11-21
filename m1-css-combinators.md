# CSS Combinators

---

## [Adjacent sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Adjacent_sibling_selectors)

```css
// will match all <p> elements that directly follow an <h2>.
h2 + p {
   color: blue;   
}
```

## [General sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/General_sibling_selectors)

```css
// will match all <span> elements that follow a <p>.
p ~ span {
    background-color: red;
}
```

## [Child combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Child_selectors)

```css
// will match all <li> elements that are nested directly inside a <ul> element.
ul > li {
    font-size: 2em;
}
```

## [Descendant combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_selectors)

```css
// will match all <span> elements that are inside a <div> element.
div span {
    background-color: gray;
}
```



