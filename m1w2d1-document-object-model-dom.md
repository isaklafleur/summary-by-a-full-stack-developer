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

## [Important Data Types](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction#Important_Data_Types) {#Important_Data_Types}

This reference tries to describe the various objects and types in as simple a way as possible. But there are a number of different data types being passed around the API that you should be aware of. For the sake of simplicity, syntax examples in this API reference typically refer to nodes as `element`s, to arrays of nodes as `nodeList`s \(or simply `element`s\), and to `attribute` nodes simply as `attribute`s.

## Accessing & Modifying DOM objects with JavaScript

* [All Element Methods & Properties](https://developer.mozilla.org/en-US/docs/Web/API/Element)
* [All Document Methods & Properties](https://developer.mozilla.org/en-US/docs/Web/API/Document)
* [All HTMLElement Methods & Properties](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
* [All EventTarget Methods](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
* [All Node Methods & Properties](https://developer.mozilla.org/en-US/docs/Web/API/Node)
* [All ChildNode Methods](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode)
* [All ParentNode Methods & Properties](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode)



| Methods | Description |
| :--- | :--- |
| [element.getElementById\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById) | Returns a reference to the element by its ID; the ID is a string which can be used to uniquely identify the element, found in the HTML id attribute. |
| [element.getElementsByClassName\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName) | Returns an array-like object of all child elements which have all of the given class names. |
| [element.getElementsByTagName\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagName) | Returns an array-like object of all child elements which have all of the given class names. |
| [Element.querySelectorAll\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll) | Returns a NodeList of nodes which match the specified selector string relative to the element. |
| [Element.removeAttribute\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttribute) | Removes a specified attribute from an element |
| [Element.removeAttributeNode\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttributeNode) | Removes a specified attribute node, and returns the removed node |
| [Element.setAttribute\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute) | Sets or changes the specified attribute, to the specified value |
| [Document.createElement\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement) | the Document.createElement\(\) method creates the HTML element specified by tagName |
| [Node.contains\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Node/contains) | The Node.contains\(\) method returns a Boolean value indicating whether a node is a descendant of a given node or not. |
| [Node.removeChild\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild) | Removes a child node from an element |
| [EventTarget.addEventListener\(\)](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) | Registers an event handler to a specific event type on the element. |
| [EventTarget.removeEventListener\(\)](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener) | Removes an event handler that has been attached with the addEventListener\(\) method |
| [ChildNode.remove\(\)](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/remove) | Removes the element from the children list of its parent. |

| Properties | Description |
| :--- | :--- |
| [Element.attributes](https://developer.mozilla.org/en-US/docs/Web/API/Element/attributes) | Returns a NamedNodeMap of an element’s attributes |
| [Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList) | Returns an array with the class name\(s\) of an element |
| [Element.className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className) | Sets or returns the value of the class attribute of an element |
| [Element.id](https://developer.mozilla.org/en-US/docs/Web/API/Element/id) | Sets or returns the value of the id attribute of an element |
| [ParentNode.children](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/children) | The Node.children is a read-only property that returns a live HTMLCollection of the child elements of Node. |
| [Node.childNodes](https://developer.mozilla.org/en-US/docs/Web/API/Node/childNodes) | The Node.childNodes read-only property returns a live collection of child nodes of the given element where the first child node is assigned index 0. |
| [Node.firstChild](https://developer.mozilla.org/en-US/docs/Web/API/Node/firstChild) | Returns the first child node of an element |
| [Node.firstElementChild](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/firstElementChild) | Returns the first child element of an element |
| [HTMLElement.style](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style) | Sets or returns the value of the style attribute of an element |



