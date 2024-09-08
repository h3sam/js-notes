#js/browser 

## creating elements to add
- to create an element, you can use `document.createElement(tag)` to create a DOM object.
- you can also use `document.createTextNode(text)` to create an element with text content inside.

## [[Editing Elements]] and Their [[Element Properties and attr.#list of most used element properties|properties]] 
This section is (going to be) thoroughly explained in this page.

## adding elements to the DOM
Inserting elements in HTML can be done two ways:
1. Using the following methods on any element:
	- `node.append(...nodes or strings)`: append nodes or strings _at the end_ of `node`
	- `node.prepend(...nodes or strings)`: insert nodes or strings _at the beginning_ of `node`
	- `node.before(...nodes or strings)`: insert nodes or strings _before_ `node`
	- `node.after(...nodes or strings)`: insert nodes or strings _after_ `node`
	- `node.replaceWith(...nodes or strings)`: replaces `node` with the given nodes or strings.
- [!] note that you can't put HTML tags inside strings, as they will be safely transferred using encoding.
2. Using insertAdjacentHTML/Text/Element on any element:
	 **insertAdjacentHTML(where, html)**:
	- the `where` attribute can have 4 positions:
		- `"beforebegin"`: insert `html` immediately before `elem`
		- `"afterbegin"`: insert `html` into `elem`, at the beginning
		- `"beforeend"`: insert `html` into `elem`, at the end
		- `"afterend"`: insert `html` immediately after `elem`