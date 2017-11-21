# Responsive Web \(App\) Design \(Flexbox, Media Queries, Mobile First, etc\)

---

Responsive web apps use technologies like media queries and viewport to make sure that their UIs will fit any form factor: desktop, mobile, tablet, or whatever comes next.

## [What is Responsive Web \(App\) Design?](https://developer.mozilla.org/en-US/Apps/Progressive/Responsive/responsive_design_building_blocks)

* Responsive web design makes your web page look good on all devices.
* Responsive web design uses only HTML and CSS.
* Responsive web design is not a program or a JavaScript.

| Concept/Tool | Description |
| :--- | :--- |
| [border-box sizing](https://css-tricks.com/inheriting-box-sizing-probably-slightly-better-best-practice/) |  |
| [Media Queries](https://css-tricks.com/snippets/css/media-queries-for-standard-devices/) | Media queries can be used to check many things, such as: width and height of the viewport, width and height of the device, orientation \(is the tablet/phone in landscape or portrait mode?\) and resolution. Using media queries are a popular technique for delivering a tailored style sheet to tablets, iPhone, and Androids. |
| [Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) | The CSS3 Flexible Box, or Flexbox, is a layout mode intended to accommodate different screen sizes and different display devices. For many applications, the flexible box model is easier than the block model since it does not use floats, nor do the flex container's margins collapse with the margins of its contents. |
| [Viewport](https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag) | Mobile browsers render pages in a virtual "window" \(the viewport\), usually wider than the screen, so they don't need to squeeze every page layout into a tiny window \(which would break many non-mobile-optimized sites\). Users can pan and zoom to see different areas of the page. |
| [Mobile First](https://zurb.com/word/mobile-first) | Mobile first, a form of progressive enhancement, is a web-development and web-design approach that focuses on prioritizing design and development for mobile screen sizes over design and development for desktop screen sizes |

```css
// viewport meta tag - boilerplate code
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
```

```css
// border-box sizing - boilerplate code

html {
  box-sizing: border-box;
}
*, *:before, *:after {
  box-sizing: inherit;
}
```

```css
// Media Queries - example:

// This applies from 0px to 767px
body {
  background-color: red;
}

/* ----------- Tablet Screens ----------- */
@media screen and (min-device-width: 768px) {
  body {
    background-color: pink;
  }
}
/* ----------- Desktop/Laptop Screens ----------- */
@media screen and (min-device-width: 1024px) {
  body {
    background-color: blue;
  }
}
```

[Here you can play around with Flex Froggy to learn Flexbox](http://flexboxfroggy.com)

