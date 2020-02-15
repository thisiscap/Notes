# SASS snippets

**Variable lists**

```
$colours: red green blue;

.class {
  property: nth($colours, 2);
}
```

**Variable maps**

```
$colours: (
  primary: red,
  secondary: green,
  neutral: blue
);

.class {
  property: map-get($colours, primary);
}
```
