# JS snippets

**Menu toggle**

```javascript
  // Define the elements
  var toggle = document.querySelector('#nav-toggle');
  var overlay = document.querySelector('#nav-overlay');
  var body = document.querySelector('body');

  // Trigger the classes on click
  toggle.onclick = function() {
    toggle.classList.toggle('active');
    overlay.classList.toggle('open');
    body.classList.toggle('noScroll');
  }
```

**Add and remove multiple classes**

```javascript
div.classList.add('foo', 'bar', 'baz');
div.classList.remove('foo', 'bar', 'baz');
```

**Swap between two classes**

```javascript
div.classList.replace('foo', 'bar');
```

**Conditionals**

```js
&&  // and
||  // or
!   // not
```

**Use Dev Tools to log elements that are causing horizontal overflow**

Add the following to Console in Chrome Dev Tools

```js
var docWidth = document.documentElement.offsetWidth;

[].forEach.call(
  document.querySelectorAll('*'),
  function(el) {
    if (el.offsetWidth > docWidth) {
      console.log(el);
    }
  }
);
```
