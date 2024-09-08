#js/browser [js.info](https://javascript.info/searching-elements-dom)
There are two main ways you can select elements:
1. by their type of HTML element (querySelector*)
2. by their attributes (getElement*)

- document.getElementById: get an element with its ID. this kinda sucks.
- **querySelector\[All\]**: returns the first (or all) of the elements matching the type put into the input.
	- the search for elements are done by [css-selector](https://www.w3schools.com/cssref/css_selectors.php).
- **matches**: checks if an element is what we want or not. it also uses CSS-selector syntax.
```js
<a href="http://example.com/file.zip">...</a>
<a href="http://ya.ru">...</a>

<script>
  // can be any collection instead of document.body.children
  for (let elem of document.body.children) {
    if (elem.matches('a[href$="zip"]')) {
      alert("The archive reference: " + elem.href );
    }
  }
</script>
```
- closest: doesn't matter imo
## getElementsBy*
These methods are not used much anymore, but here they are.
- [*] The elements gathered by getElementsby are live, meaning that they will be updated whenever the page updates.
- `elem.getElementsByTagName(tag)` looks for elements with the given tag and returns the collection of them. The `tag` parameter can also be a star `"*"` for “any tags”.
- `elem.getElementsByClassName(className)` returns elements that have the given CSS class.
- `document.getElementsByName(name)` returns elements with the given `name` attribute, document-wide. Very rarely used.
