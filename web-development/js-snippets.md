# Vanilla JS snippets

**Menu toggle**

````javascript
<script>
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
</script>
````

Different things you can do:

Add and remove multiple classes
````javascript
div.classList.add("foo", "bar", "baz");
div.classList.remove("foo", "bar", "baz");
````

Swap between two classes
````javascript
div.classList.replace("foo", "bar");
````
