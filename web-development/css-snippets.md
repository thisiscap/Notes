# Misc CSS snippets

**Better image sharpness with scaling or downsizing** [Source](https://medium.freecodecamp.org/-898b38a6c0e1)

```css
img {
  image-rendering: -webkit-optimize-contrast;
}
```

**Useful for text wrap appearence and missing margins** [Source](https://www.smashingmagazine.com/2017/12/understanding-css-layout-block-formatting-context/)

```css
div {
  // In the future
  display: flow-root;
  // As of now
  overflow: auto;
}
