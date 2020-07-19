# Misc CSS snippets

**Better image sharpness with scaling or downsizing** [Source](https://medium.freecodecamp.org/-898b38a6c0e1)

```scss
img {
  image-rendering: -webkit-optimize-contrast;
}
```

**Useful for text wrap appearence and missing margins** [Source](https://www.smashingmagazine.com/2017/12/understanding-css-layout-block-formatting-context/)

```scss
div {
  // In the future
  display: flow-root;

  // As of now
  overflow: auto;
}
```

**Position fixed that aligns to container rather than window** [Source](https://medium.com/@peedutuisk/lesser-known-css-quirks-oddities-and-advanced-tips-css-is-awesome-8ee3d16295bb)

```scss
.parent {
  // Add this
  transform: translateZ(0);
}

.child {
  position: fixed;
}
```

**Apply properties to all but last**

```scss
li + li {
 margin-top: 1rem;
}

// VS

li {
 // margin-bottom: 1rem;
}
li:last-of-type {
  // margin-bottom: 0;
}
```

**Truncate text with CSS**

```scss
p {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
```

**Ratio keeping containers (16:9 example)**

```scss
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

```scss
@media (prefers-reduced-motion: reduce) {
  * {
    animation: none !important;
    transition: none !important;
  }
}
```

**Show search button when the search has content**

```scss
button {
  display: none;
}

input:not(:placeholder-shown) + button {
  display: block;
}
```

**Class to break content out of containers to full width**

```scss
.breakout {
  width: 100vw;
  margin-left: 50%;
  transform: translateX(-50%);
}
```

**Animate the closing of a modal** [Source](https://codepen.io/lonekorean/pen/vYLNdBY)

```scss
.modal {
    animation: dismiss 1s forwards;
}

@keyframes dismiss {
    to {
        opacity: 0;
        visibility: hidden;
    }
}
```

**Style bullets on bulleted list** [Source](https://www.ishadeed.com/article/uncommon-css/)

```scss
ul {
    li {
    color: blue;

    &::marker {
        color: orange;
    }
```

**Prevent repeating backgrounds from being clipped** [Source](https://www.ishadeed.com/article/uncommon-css/)

```scss
.repeating-background {
    background-size: contain;
    background-repeat: round;
}
```
