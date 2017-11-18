# Introduction to the CSS box model

When laying out a document, the browser's rendering engine represents each element as a rectangular box according to the standard **CSS box model**. CSS determines the size, position, and properties \(color, background, border size, etc.\) of these boxes.

Every box is composed of four parts \(or _areas_\), defined by their respective edges: the _content edge_, _padding edge_, _border edge_, and _margin edge_.

![](https://mdn.mozillademos.org/files/8685/boxmodel-%283%29.png)

The**content area**, bounded by the content edge, contains the "real" content of the element, such as text, an image, or a video player. Its dimensions are the_content width_\(or_content-box width_\) and the_content height_\(or_content-box height_\). It often has a background color or background image.

If the [`box-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing) property is set to `content-box`\(default\), the content area's size can be explicitly defined with the [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width), [`min-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width), [`max-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width), [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height), [`min-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-height), and [`max-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height) properties.

The **padding area**, bounded by the padding edge, extends the content area to include the element's padding. Its dimensions are the _padding-box width _and the _padding-box height_. When the content area has a background, it extends into the padding.

The thickness of the padding is determined by the [`padding-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-top), [`padding-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-right), [`padding-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom), [`padding-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-left), and shorthand [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) properties.

The **border area**, bounded by the border edge, extends the padding area to include the element's borders. Its dimensions are the _border-box width _and the _border-box height_.

The thickness of the borders are determined by the [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width) and shorthand [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) properties. If the [`box-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing) property is set to `border-box`, the border area's size can be explicitly defined with the [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width), [`min-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width), [`max-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width), [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height), [`min-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-height), and [`max-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height) properties.

The **margin area**, bounded by the margin edge, extends the border area to include an empty area used to separate the element from its neighbors. Its dimensions are the _margin-box width _and the _margin-box height_.

The size of the margin area is determined by the [`margin-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top), [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right), [`margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom), [`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left), and shorthand [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) properties. When [margin collapsing](https://developer.mozilla.org/en/CSS/margin_collapsing) occurs, the margin area is not clearly defined since margins are shared between boxes.

Finally, note that for non-replaced inline elements, the amount of space taken up \(the contribution to the height of the line\) is determined by the [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height) property, even though the borders and padding are still displayed around the content.

