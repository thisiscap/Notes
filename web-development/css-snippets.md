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
  /* In the future */
  display: flow-root;
  
  /* As of now */
  overflow: auto;
}
```

**Position fixed that aligns to container rather than window** [Source](https://medium.com/@peedutuisk/lesser-known-css-quirks-oddities-and-advanced-tips-css-is-awesome-8ee3d16295bb)

```sass
.parent {
  transform: translateZ(0); // Add this
}

.child {
  position: fixed;
}
```
