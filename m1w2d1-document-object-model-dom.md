# [Document Object Model \(DOM\)](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)

---

When a web page is loaded, the browser creates a **D**ocument **O**bject **M**odel of the page. The **HTML DOM **model is constructed as a tree of **Objects.**

![](https://www.w3schools.com/js/pic_htmltree.gif)

## Accessing DOM objects with JavaScript

| Method | Description |
| :--- | :--- |
| [document.getElementById\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById) | Returns a reference to the element by its ID; the ID is a string which can be used to uniquely identify the element, found in the HTML id attribute. |
| [document.getElementsByClassName\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName) | Returns an array-like object of all child elements which have all of the given class names. |
| [document.getElementsByTagName](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagName) | Returns an array-like object of all child elements which have all of the given class names. |



|  |
| :--- |


| **Property / Method** | **Description** |
| :--- | :--- |
| `element.attributes` | Returns a NamedNodeMap of an element’s attributes |
| `element.childNodes` | Returns a collection of an element’s child nodes \(including text and comment nodes\) |
| `element.children` | Returns a collection of an element’s child element \(excluding text and comment nodes\) |
| `element.classList` | Returns an array with the class name\(s\) of an element |
| `element.className` | Sets or returns the value of the class attribute of an element |
| `element.clientHeight` | Returns the height of an element, including padding |
| `element.clientLeft` | Returns the width of the left border of an element |
| `element.clientTop` | Returns the width of the top border of an element |
| `element.clientWidth` | Returns the width of an element, including padding |
| `element.contains()` | Returns true if a node is a descendant of a node, othwerwise false |
| `element.contentEditable` | Sets or returns whether the content of an element is editable or not |
| `element.firstChild` | Returns the first child node of an element |
| `element.firstElementChild` | Returns the first child element of an element |
| `element.focus()` | Gives focus to an element |
| `element.getAttribute()` | Returns the specified attribute value of an element node |
| `element.getAttributeNode()` | Returns the specified attribute node |
| `element.getElementsByClassName()` | Returns a collection of all child elements with the specified class name |
| `element.getElementsByTagName()` | Returns a collection of all child elements with the specified tag name |
| `element.getFeature()` | Returns an object which implements the APIs of a specified feature |
| `element.hasAttribute()` | Returns true if an element has the specified attribute, otherwise false |
| `element.hasAttributes()` | Returns true if an element has any attributes, otherwise false |
| `element.hasChildNodes()` | Returns true if an element has any child nodes, otherwise false |
| `element.id` | Sets or returns the value of the id attribute of an element |
| `element.isEqualNode()` | Checks if two elements are equal |
| `element.isSameNode()` | Checks if two elements are the same node |
| `element.lastChild` | Returns the last child node of an element |
| `element.lastElementChild` | Returns the last child element of an element |
| `element.nextSibling` | Returns the next node at the same node tree level |
| `element.nextElementSibling` | Returns the next element at the same node tree level |
| `element.nodeName` | Returns the name of a node |
| `element.nodeValue` | Sets or returns the value of a node |
| `element.offsetHeight` | Returns the height of an element, including padding, border and scrollbar |
| `element.offsetWidth` | Returns the width of an element, including padding, border and scrollbar |
| `element.offsetLeft` | Returns the horizontal offset position of an element |
| `element.offsetParent` | Returns the offset container of an element |
| `element.offsetTop` | Returns the vertical offset position of an element |
| `element.parentNode` | Returns the parent node of an element |
| `element.parentElement` | Returns the parent element node of an element |
| `element.previousSibling` | Returns the previous node at the same node tree level |
| `element.previousElementSibling` | Returns the previous element at the same node tree level |
| `element.querySelector()` | Returns the first child element that matches a specified CSS selector\(s\) of an element |
| `element.querySelectorAll()` | Returns all child elements that matches a specified CSS selector\(s\) of an element |
| `element.removeAttribute()` | Removes a specified attribute from an element |
| `element.removeAttributeNode()` | Removes a specified attribute node, and returns the removed node |
| `element.removeChild()` | Removes a child node from an element |
| `element.replaceChild()` | Replaces a child node in an element |
| `element.removeEventListener()` | Removes an event handler that has been attached with the addEventListener\(\) method |
| `element.scrollHeight` | Returns the entire height of an element, including padding |
| `element.scrollLeft` | Sets or returns the number of pixels an element’s content is scrolled horizontally |
| `element.scrollTop` | Sets or returns the number of pixels an element’s content is scrolled vertically |
| `element.scrollWidth` | Returns the entire width of an element, including padding |
| `element.setAttribute()` | Sets or changes the specified attribute, to the specified value |
| `element.setAttributeNode()` | Sets or changes the specified attribute node |
| `element.style` | Sets or returns the value of the style attribute of an element |
| `element.tabIndex` | Sets or returns the value of the tabindex attribute of an |
| `element.tagName` | Returns the tag name of an element |
| `element.textContent` | Sets or returns the textual content of a node and its |
| `element.title` | Sets or returns the value of the title attribute of an element |
| `element.toString()` | Converts an element to a string |
| `nodelist.item()` | Returns the node at the specified index in a NodeList |
| `nodelist.length` | Returns the number of nodes in a NodeList |



