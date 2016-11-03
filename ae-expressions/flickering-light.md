#Flickering light

- Add following expression to `Opacity`

```
// HIGHER values for probability make a random opacity LESS likely.
// A value of 1 will always create a random opacity, a value of 2 will
// create a random opacity 50% of the time, value of 4 will be 25%, etc.

probability = 6;
// "opacity_normal" is the value set for opacity when the a random opacity is NOT chosen.
opacity_normal = 100;
x = random(probability);
if (x <= 1) {
   opacity = random(100);
} else {
opacity = opacity_normal;
}
```

[Source](http://www.motion-graphics-exchange.com/after-effects/Flickering-Neon-Light/4b8944565425d)
