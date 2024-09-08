#js/browser [js.info](https://javascript.info/dom-attributes-and-properties)

- [*] the difference between properties and attributes are that: **attributes refer to the HTML attributes**, while **properties refer to the properties of the DOM object present in js**.
- [*] in general, it is more convenient to use the properties of js instead of the attributes, except for 2 places primarily:
	1. We need a non-standard attribute. But if it starts with `data-`, then we should use the `dataset` inside object.
	2. We want to read the value “as written” in HTML. The value of the DOM property may be different, for instance the `href` property is always a full URL, and we may want to get the “original” value.
# attributes
- in general, you can access the standard attributes in any element by `elem.attr`, and the standard attributes are different for each element.
- if you want to read and write attributes that are non-standard, you could use these methods:
	- `elem.hasAttribute(name)` – checks for existence.
	- `elem.getAttribute(name)` – gets the value.
	- `elem.setAttribute(name, value)` – sets the value.
	- `elem.removeAttribute(name)` – removes the attribute.
- there is one exception though, and that is the attributes that start with data-\*. these attributes can be accessed via `elem.dataset.*`.
	- for example, if a p tag has an attribute named `data-mamad`, we can access it via `document.querySelector('p').dataset.mamad`
	- an attribute like `data-mamad-reza` can be accessed via elem.dataset.mamadReza (**any extra dash will be appended to the name as a camelCase**)
- All attr. of an element can be seen via `elem.attributes` in the form of an array.
- attribute names are case insensitive


