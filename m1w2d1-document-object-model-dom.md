# [Document Object Model \(DOM\)](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)

---

When a web page is loaded, the browser creates a **D**ocument **O**bject **M**odel of the page. The **HTML DOM **model is constructed as a tree of **Objects.**

![](https://www.w3schools.com/js/pic_htmltree.gif)

## What is the HTML DOM?

The HTML DOM is a standard **object **model and **programming interface **for HTML. It defines:

* The HTML elements as **objects**
* The **properties **of all HTML elements
* The **methods **to access all HTML elements
* The **events **for all HTML elements

In other words: **The HTML DOM is a standard for how to get, change, add, or delete HTML elements.**

## Important Data Types {#Important_Data_Types}

This reference tries to describe the various objects and types in as simple a way as possible. But there are a number of different data types being passed around the API that you should be aware of. For the sake of simplicity, syntax examples in this API reference typically refer to nodes as `element`s, to arrays of nodes as `nodeList`s \(or simply `element`s\), and to `attribute` nodes simply as `attribute`s.

The following table briefly describes these data types.

| Important Data Types |
| :--- |


| `document` | When a member returns an object of type `document`\(e.g., the **`ownerDocument `**property of an element returns the `document` to which it belongs\), this object is the  root` document` object itself. The [DOM `document`Reference](https://developer.mozilla.org/en-US/docs/DOM/document) chapter describes the `document` object. |
| :--- | :--- |
| `element` | `element` refers to an element or a node of type `element` returned by a member of the DOM API. Rather than saying, for example, that the [document.createElement\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement) method returns an object reference to a`node`, we just say that this method returns the`element`that has just been created in the DOM.`element`objects implement the DOM`Element`interface and also the more basic`Node`interface, both of which are included together in this reference. |
| `nodeList` | A`nodeList`is an array of elements, like the kind that is returned by the method [document.getElementsByTagName\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagName). Items in a`nodeList` are accessed by index in either of two ways: list.item\(1\) or list\[1\]. These two are equivalent. In the first,**`item()`**is the single method on the `nodeList `object. The latter uses the typical array syntax to fetch the second item in the list. |
| `attribute` | When an `attribute` is returned by a member \(e.g., by the **`createAttribute()`**method\), it is an object reference that exposes a special \(albeit small\) interface for attributes. Attributes are nodes in the DOM just like elements are, though you may rarely use them as such. |
| `namedNodeMap` | A `namedNodeMap` is like an array, but the items are accessed by name or index, though this latter case is merely a convenience for enumeration, as they are in no particular order in the list. A `namedNodeMap` has an item\(\) method for this purpose, and you can also add and remove items from a `namedNodeMap`. |

## Accessing DOM objects with JavaScript

##### A list of common used Properties and Methods

| Methods | **Description** |
| :--- | :--- |
| [element.getElementById\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById) | Returns a reference to the element by its ID; the ID is a string which can be used to uniquely identify the element, found in the HTML id attribute. |
| [element.getElementsByClassName\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName) | Returns an array-like object of all child elements which have all of the given class names. |
| [element.getElementsByTagName\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagName) | Returns an array-like object of all child elements which have all of the given class names. |
| [`EventTarget.addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) | Registers an event handler to a specific event type on the element. |
| [`ChildNode.remove()`](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/remove) | Removes the element from the children list of its parent. |
|  |  |

|  |
| :--- |


| **Property / Method** | **Description** |
| :--- | :--- |
| `element.attributes` | Returns a NamedNodeMap of an element’s attributes |
| `element.childNodes` | Returns a collection of an element’s child nodes \(including text and comment nodes\) |
| `element.children` | Returns a collection of an element’s child element \(excluding text and comment nodes\) |
| `element.classList` | Returns an array with the class name\(s\) of an element |
| `element.className` | Sets or returns the value of the class attribute of an element |
|  |  |
|  |  |
|  |  |
|  |  |
| `element.contains()` | Returns true if a node is a descendant of a node, othwerwise false |
|  |  |
| `element.firstChild` | Returns the first child node of an element |
| `element.firstElementChild` | Returns the first child element of an element |
|  |  |
| `element.getAttribute()` | Returns the specified attribute value of an element node |
| `element.getAttributeNode()` | Returns the specified attribute node |
|  |  |
|  |  |
|  |  |
| `element.hasAttribute()` | Returns true if an element has the specified attribute, otherwise false |
| `element.hasAttributes()` | Returns true if an element has any attributes, otherwise false |
| `element.hasChildNodes()` | Returns true if an element has any child nodes, otherwise false |
|  |  |
|  |  |
|  |  |
| `element.lastChild` | Returns the last child node of an element |
| `element.lastElementChild` | Returns the last child element of an element |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
| `element.parentNode` | Returns the parent node of an element |
| `element.parentElement` | Returns the parent element node of an element |
|  |  |
|  |  |
| `element.querySelector()` | Returns the first child element that matches a specified CSS selector\(s\) of an element |
| `element.querySelectorAll()` | Returns all child elements that matches a specified CSS selector\(s\) of an element |
| `element.removeAttribute()` | Removes a specified attribute from an element |
| `element.removeAttributeNode()` | Removes a specified attribute node, and returns the removed node |
| `element.removeChild()` | Removes a child node from an element |
|  |  |
| `element.removeEventListener()` | Removes an event handler that has been attached with the addEventListener\(\) method |
|  |  |
|  |  |
|  |  |
|  |  |
| `element.setAttribute()` | Sets or changes the specified attribute, to the specified value |
| `element.setAttributeNode()` | Sets or changes the specified attribute node |
| `element.style` | Sets or returns the value of the style attribute of an element |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |



