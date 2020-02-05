# Objects and DOM

The Document Object Model is a mean through which we
can interact with web pages.

Indeed, it is called Document Object Model, since
we can interact with a web page as we were using an object.

An example:
```javascript
function showMsg(msg) {
    document.getElementById('message').textContent = msg;
}
// here we take the html tags with id equal to 'message' and
// modify it
```

Some of the most common simple things done with DOM are:
- Styling DOM Elements
```javascript
element.style.cssProp = 'value'
```
- Detecting Events (e.g., button clicks)
```javascript
element.addEventListener(event, fn)
```
- Showing and Hiding DOM elements (by changing class)
```javascript
element.classList.add(className)
element.classList.remove(className)
element.classList.contains(className)
```

Notice that one of the most commonly used option to select DOM elements
is by `id`.
