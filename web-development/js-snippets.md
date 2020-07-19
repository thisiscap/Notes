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

```javascript
&&  // and
||  // or
!   // not
```

**Use Dev Tools to log elements that are causing horizontal overflow**

Add the following to Console in Chrome Dev Tools

```javascript
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

**Pause playing video elements when scrolled out of viewport** [Source](https://css-tricks.com/a-few-functional-uses-for-intersection-observer-to-know-when-an-element-is-in-view/?ref=webdesignernews.com)

```html
<video src="my-video.mp4" controls=""></video>
```

```javascript
let video = document.querySelector('video');
let isPaused = false; /* Flag for auto-paused video */
let observer = new IntersectionObserver((entries, observer) => {
    entries.forEach(entry => {
        if(entry.intersectionRatio!=1  && !video.paused){
            video.pause(); isPaused = true;
        }
        else if(isPaused) {video.play(); isPaused=false}
    });
}, {threshold: 1});
observer.observe(video);
```
