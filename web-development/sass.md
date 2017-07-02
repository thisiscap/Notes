# SASS snippets

**Lists**

List of variables that can be refered to

````
$list: item1 item2;

.class {
  property: nth($list, 2);
}
````

**Maps**

When variables have a common theme/more complex usage

````
$colours: (
  primary: red,
  secondary: green,
  neutral: blue
);

.class {
  property: map-get($colours, primary);
}
````
