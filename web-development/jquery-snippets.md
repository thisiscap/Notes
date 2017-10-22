# jQuery snippets

**Smooth scroll to top**

```
$('a.backToTop').click(function(){
$(document.body).animate({scrollTop : 0},800);
return false;
});
```
```
<a class="backToTop" href="#">Back to top</a>
```

**Simple animated accordian**

```
// Close all Panels
$('#accordion').find(‘.content').hide();
// Accordion
$('#accordion').find(‘.accordion-header').click(function(){
var next = $(this).next();
next.slideToggle('fast’);
$(‘.content’).not(next).slideUp('fast’);
return false;
});
```
