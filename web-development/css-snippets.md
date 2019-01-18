# Misc CSS snippets

**Better image sharpness with scaling or downsizing** [Source](https://medium.freecodecamp.org/-898b38a6c0e1)

```sass
img {
  image-rendering: -webkit-optimize-contrast;
}
```

**Useful for text wrap appearence and missing margins** [Source](https://www.smashingmagazine.com/2017/12/understanding-css-layout-block-formatting-context/)

```sass
div {
  // In the future
  display: flow-root;
  
  // As of now
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

**Apply properties to all but last**

```sass
li + li {
 margin-top: 1rem;
}

// VS

li {
 //margin-bottom: 1rem;
}
li:last-of-type {
  //margin-bottom: 0;
}
```

**Truncate text with CSS**

```sass
p {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
```

**Ratio keeping containers (16:9 example)**

```sass
.outer {
  position: relative;
  
  &:before {
    display: block;
    content: "";
    width: 100%;
    padding-top: (9 / 16) * 100%;
  }
  
  > .inner {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
  }
}
```

**Disable CSS animations for users who opt-out of motion**

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation: none !important;
    transition: none !important;
  }
}
```
